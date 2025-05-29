# **Worksheet 4: Callbacks & Event Listeners**

**Objective:**
* Understand what callbacks are and how they work in JavaScript.
* Learn to attach event listeners to DOM elements.
* Explore common event types and the Event object.
* Practice using callbacks to update the UI in response to events.

### 1. What Is a Callback?
1. In your index.html, verify you have a `<script>` block before `</body>`.
2. Inside the `<script>`, add:

```js
function sayHello() {
	console.log('Hello from callback!');
}

// Call sayHello directly:
sayHello();

// Use as a callback:
setTimeout(sayHello, 1000); // executes after 1 second
```

3. Save and refresh. Observe one message immediately and one after a second.

⠀**Exercise:**
* Change the timeout to 3000 (3 seconds) and observe the delay.
* Write an anonymous callback via setInterval to log the current time every 2 seconds:

```js
setInterval(() => console.log(new Date().toLocaleTimeString()), 2000);
```

### 2. Click Event Listener
1. In your HTML, add a button inside the container `<div>`

```html
<button id="alert-btn" class="mt-6 px-4 py-2 bg-red-500 text-white rounded hover:bg-red-600">Show Alert</button>
```

2. In `<script>`, select the button and attach a click listener:

```js
const alertBtn = document.getElementById('alert-btn');

alertBtn.addEventListener('click', function() {
	alert('Button clicked!');
});
```

3. Save, refresh, and click the button to see the alert.

⠀**Exercise:**
* Rewrite the listener using an arrow function.
* Change the alert message to include the button’s text: this.textContent (or use event.target.textContent).

### 3. Other Common Events
1. Below the button, add an `<input>` field:

```html
<input id="name-input" type="text" placeholder="Type your name" class="mt-4 px-2 py-1 border rounded">
<p id="greet-output" class="mt-2 text-lg font-medium"></p>
```

2. In your script, select the input and output elements. Attach an input event listener:

```js
const nameInput = document.getElementById('name-input');
const greetOutput = document.getElementById('greet-output');

nameInput.addEventListener('input', function(event) {
	greetOutput.textContent = `Hello, ${event.target.value}!`;
});
```

3. Type into the field and see the paragraph update in real time.

⠀**Exercise:**
* Add a focus listener to change nameInput’s border color via classList.add.
* Add a blur listener to revert the border color.

### 4. The Event Object
1. Modify your click listener on alert-btn to log the event object:

```js
alertBtn.addEventListener('click', (event) => {
	console.log('Event:', event);
});
```

2. In the Console, inspect properties like event.type, `event.target`, and `event.clientX/Y`.

⠀**Exercise:**
* Log the mouse coordinates when clicking on the page 

```js
document.body.addEventListener('click', …)
```

### 5. Using Callbacks to Update UI
1. Create a simple counter: In your HTML container `<div>`, add:

```html
<div class="mt-6 flex items-center">
 	<button id="dec-btn" class="px-3 py-1 bg-gray-300 rounded">-</button>
 	<span id="counter" class="mx-4 text-xl">0</span>
 	<button id="inc-btn" class="px-3 py-1 bg-gray-300 rounded">+</button>
</div>
```

2. In your script, implement the logic:

```js
let value = 0;
const counterEl = document.getElementById('counter');
const incBtn = document.getElementById('inc-btn');
const decBtn = document.getElementById('dec-btn');

function updateCounter(newVal) {
	value = newVal;
	counterEl.textContent = value;
}

incBtn.addEventListener('click', () => updateCounter(value + 1));
decBtn.addEventListener('click', () => updateCounter(value - 1));
```

3. Save, refresh, and use the buttons to change the counter value.

⠀**Exercise:**
* Prevent the counter from going below zero.
* Disable the “-” button when value is 0.


#jsfundamentals