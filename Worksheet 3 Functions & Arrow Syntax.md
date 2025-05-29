# **Worksheet 3: Functions & Arrow Syntax**

**Objective:**
* Understand how to declare and invoke traditional functions.
* Learn arrow function syntax and when to use it.
* Practice passing parameters, returning values, and using callbacks.

### 1. Traditional Function Declaration
1. Open your index.html and ensure you have a `<script>` block before `</body>`.
2. Inside `<script>` add:

```js
function greet(name) {
	console.log('Hello, ' + name + '!');
}

greet('Bob');
```


3. Save and refresh. Check the Console for the greeting.

⠀**Exercise:**
* Call greet with your own name.
* Modify the function to log the greeting in uppercase using .toUpperCase().

### 2. Arrow Function Syntax
1. Rewrite greet as an arrow function:

```js
const greetArrow = name => {
	console.log(`Hi, ${name}! (from arrow)`);
};

greetArrow('Bob');
```

2. Refresh and compare outputs.

⠀**Exercise:**
* Create a one-line arrow function square that takes a number and returns its square.
* Log `square(5)` to verify it returns 25.

### 3. Parameters & Return Values
1. Add this function:

```js
function add(a, b) {
	return a + b;
}

const sum = add(7, 3);
console.log('Sum is:', sum);
```

2. Rewrite add as a concise arrow function:

```js
const addArrow = (a, b) => a + b;
console.log('Arrow sum is:', addArrow(7, 3));
```

**Exercise:**
* Write a function isEven (traditional or arrow) that returns true if a number is even.
* Test it with several values and log results.

### 4. Higher-Order Functions & Callbacks
1. Create an array in your script:

```js
const numbers = [1, 2, 3, 4, 5];
```

2. Use forEach with a callback to log each number:

```js
numbers.forEach( function(num) {
	console.log('Number:', num);
});
```

3. Then rewrite using an arrow callback:

```js
numbers.forEach(num => console.log('Arrow number:', num));
```

**Exercise:**
* Use map with a callback to create a new array of squares.
* Log the resulting array.

### 5. DOM & Callback Example
1. In your HTML, add a button:

```js
<button id="random-btn" class="mt-6 px-4 py-2 bg-blue-500 text-white rounded">
	Show Random Number
</button>
<p id="rand-display" class="mt-4 text-xl font-medium"></p>
```

2. In your `<script>` add:

```js
const btn = document.getElementById('random-btn');
const display = document.getElementById('rand-display');

btn.addEventListener('click', () => {
	const rand = Math.floor(Math.random() * 100) + 1;
	display.textContent = `Random: ${rand}`;
});
```

3. Save, refresh, and click the button to see a new random number.

⠀**Exercise:**
* Change the range to 1–1000.
* Add a callback function reference instead of inline arrow function:

```js
function showRandom() {
 	// ... generate and display
}
btn.addEventListener('click', showRandom);
```


#jsfundamentals