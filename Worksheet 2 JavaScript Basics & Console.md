# **Worksheet 2: JavaScript Basics & Console**

**Objective:**
* Introduce JavaScript placement and syntax.
* Use console.log to debug, declare variables with let/const, and modify simple DOM elements.

### 1. Adding Your Script
1. Open index.html from Worksheet 1 (or create a new index.html).
2. Just before the closing `</body>` tag, insert:

```html
<script>
	// Your JavaScript goes here
</script>
```

3. Save and refresh the page—nothing visible changes yet.

⠀**Exercise:**
* Open DevTools (F12) and check the **Console** for any errors. Ensure your script tag loaded correctly.

### 2. console.log and Variables
1. Inside your `<script>` tags, write:

```js
console.log('Hello from JavaScript!');
```
⠀
2. Refresh and observe the message in the DevTools Console.
3. Declare variables:

```js
const greeting = 'Hi there';
let count = 5;
console.log(greeting, count);
```

4. Update the variable and log again:

```js
count = count + 3;
console.log('Updated count:', count);
```

**Exercise:**
* Add a new let variable named `userName` with your name.
* Log a personalized greeting: 

```js
console.log(Hello, ${userName}!);
```

### 3. Simple DOM Selection & Modification
1. In the `<body>`, add this paragraph:

```js
<p id="message" class="mt-4 text-gray-800">Original message.</p>
```

2. In your `<script>`, select the element and change its text:

```js
const messageEl = document.getElementById('message');
messageEl.textContent = 'This text was changed by JavaScript!';
```

3. Save and refresh; observe the updated text.

⠀**Exercise:**
* Add CSS classes via JavaScript:

```js
messageEl.classList.add('text-green-600', 'font-semibold');
```

* Change the message to something else of your choice.

### 4. Page Styling via JS
1. Still in your `<script>`, write:

```js
const response = prompt('What is your favorite color?');
alert(`You chose: ${response}`);
// Modify the body background
if (response) {
	document.body.style.backgroundColor = response;
}
```

2. Refresh, enter a color in the prompt, and see the alert. Then watch the background color update.

⠀**Exercise:**
* Instead of changing background, try modifying the `<div>` container’s class list (e.g., toggle `bg-white` to `bg-yellow-100`).

⠀
#jsfundamentals