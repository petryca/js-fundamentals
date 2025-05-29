# **Worksheet 6: Fetch API & Promises**

**Objective:**
* Learn how to make HTTP requests with the Fetch API.
* Work with Promises (.then() and .catch()).
* Use async/await for cleaner asynchronous code.
* Handle errors and display fetched data in the DOM.

### 1. Introduction to Fetch
1. In your index.html <script> block, add:

```js
console.log('Fetching data...');
fetch('https://jsonplaceholder.typicode.com/users/1')
.then(response => response.json())
.then(user => console.log('User:', user));
```

2. Save and refresh. In the Console, you’ll see “Fetching data...” then the user object.

⠀**Exercise:**
* Change the URL to /posts/1 and log the post object.

### 2. Checking Response Status & Error Handling
1. Improve your fetch call with a status check:

```js
fetch('https://jsonplaceholder.typicode.com/users/999')
.then(response => {
	if (!response.ok) {
		throw new Error(`HTTP error! status: ${response.status}`);
    }
    return response.json();
})
.then(data => console.log(data))
.catch(error => console.error('Fetch error:', error));
```

2. Fetching user 999 should trigger the catch block.

⠀**Exercise:**
* Modify the URL to an invalid endpoint (e.g., /foo) and observe the error.

### 3. Rendering Data to the DOM
1. In your HTML, add a container:

```html
<div id="user-container" class="mt-6 p-4 bg-white rounded shadow max-w-md mx-auto">
</div>
```

2. In <script>, fetch a list of users and render their names:

```js
const container = document.getElementById('user-container');

fetch('https://jsonplaceholder.typicode.com/users')
.then(res => res.json())
.then(users => {
    users.forEach(user => {
		const p = document.createElement('p');
		p.textContent = user.name;
		p.classList.add('text-gray-800', 'py-1', 'border-b');
		container.appendChild(p);
 	});
 })
.catch(err => console.error(err));
```

3. Save, refresh, and see the list of user names styled with Tailwind.

⠀**Exercise:**
* Display each user’s email in italic below the name.

### 4. async/await Syntax
1. Refactor the list-fetching code:

```js
async function loadUsers() {
	try {
    const res = await fetch('https://jsonplaceholder.typicode.com/users');
    	if (!res.ok) throw new Error(res.statusText);
    	const users = await res.json();
    	container.innerHTML = '';

    	users.forEach(u => {
      	 const div = document.createElement('div');
      	 div.innerHTML = `<h3 class="font-semibold">${u.name}</h3><p>${u.email}</p>`;
     	 div.classList.add('mb-4');
     	 container.appendChild(div);
    	});

	} catch (e) {
    	console.error('Error loading users:', e);
    	container.textContent = 'Failed to load users.';
	}
}

loadUsers();
```

2. Save and refresh. Observe the same list rendered via async/await.

⠀**Exercise:**
* Add a “Reload” button that clears the container and calls loadUsers() again.

### 5. Loading State & Fetching Indicators
1. Above the container, add a placeholder:

```html
<div id="loading" class="text-center text-gray-500">Loading users...</div>
```

2. In loadUsers(), show and hide it:

```js
const loading = document.getElementById('loading');

async function loadUsers() {
	loading.style.display = 'block';
	container.textContent = '';

	try {
    	const res = await fetch(...);
    	// as before
  	} catch (e) {
    	// as before
  	} finally {
		loading.style.display = 'none';
  	}
}
```

3. Save, refresh, and see “Loading users...” briefly before the list appears.

⠀**Exercise:**
* Style the loading text to be italic and gray (`italic text-gray-600`)


#jsfundamentals