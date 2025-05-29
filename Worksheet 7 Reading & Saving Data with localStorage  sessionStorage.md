# **Worksheet 7: Reading & Saving Data with localStorage / sessionStorage**

**Objective:**
* Understand the difference between localStorage and sessionStorage.
* Learn how to read, write, and remove simple values.
* Store and retrieve structured data (arrays/objects) using JSON.
* Practice persisting UI state across page reloads.

### 1. Introduction to Web Storage
1. Both localStorage and sessionStorage let you store key/value pairs in the browser.
   * localStorage: persists until explicitly cleared (even across browser restarts).
   * sessionStorage: persists for the lifetime of the tab/session.
2. Open your index.html and ensure you have a <script> section.

⠀**Exercise:**
1. In DevTools Console, run `localStorage.setItem('test', '123');` 
2. Then `localStorage.getItem('test');`
3. Observe the value 
4. Then `localStorage.removeItem('test');` and check it’s gone

### 2. Saving Simple Values
1. In <script>, add:

```js
// Save a value
localStorage.setItem('bgColor', 'lightblue');
// Retrieve it
const stored = localStorage.getItem('bgColor');
console.log('Stored bgColor:', stored);
```

2. Refresh—check the Console log.

⠀**Exercise:**
* Change `'lightblue'` to your favorite color and re-run the code. Verify it persists after refresh.

### 3. Persisting Input Text

1. In your HTML container <div>, add:

```html
<input id="note-input" type="text" placeholder="Write a note" class="mt-4 p-2 border rounded w-full">

<button id="save-note" class="mt-2 px-4 py-2 bg-green-500 text-white rounded">Save Note</button>

<p id="show-note" class="mt-4 text-gray-800"></p>
```

2. In <script>, write:

```js
const input = document.getElementById('note-input');
const saveBtn = document.getElementById('save-note');
const display = document.getElementById('show-note');

// Load on page load
const savedNote = localStorage.getItem('myNote');
if (savedNote) display.textContent = savedNote;

// Save on button click
saveBtn.addEventListener('click', () => {
	const note = input.value;
	localStorage.setItem('myNote', note);
	display.textContent = note;
	input.value = '';
});
```

3. Save, refresh, type a note, and click **Save Note**. The note should persist and display.

⠀**Exercise:**
* Instead of localStorage, switch to sessionStorage and observe behavior across reloads vs. new tabs.

### 4. Storing Structured Data (JSON)

1. Define and save an array of objects:

```js
const todos = [
	{ id: 1, task: 'Learn JS', done: false },
 	{ id: 2, task: 'Build app', done: false }
];

localStorage.setItem('todos', JSON.stringify(todos));
```

2. Retrieve and parse:

```js
const storedTodos = JSON.parse(localStorage.getItem('todos')) || [];
console.log('Todos:', storedTodos);
```

**Exercise:**
* Add a new todo object to storedTodos, save it back with setItem, and confirm the updated list persists.

### 5. Rendering & Updating List with Persistence
1. In your HTML div, add an unordered list:

```html
<ul id="todo-list" class="mt-4 list-disc list-inside"></ul>
```

2. In <script>, render storedTodos:

```js
const listEl = document.getElementById('todo-list');
storedTodos.forEach(item => {
	const li = document.createElement('li');
	li.textContent = `${item.task} [${item.done ? '✓' : '']}`;
	listEl.appendChild(li);
});
```

**Exercise:**
- Add a button to each <li> that toggles done status in storedTodos, re-saves to storage, and updates the UI.

### 6. Clearing Storage
1. To clear all data:

```js
localStorage.clear();
sessionStorage.clear();
```

**Exercise:**
- Add a “Clear All” button that removes only your app’s keys (e.g., myNote, todos) without clearing unrelated storage.


#jsfundamentals
