# **Worksheet 5: Objects & Arrays**

**Objective:**
* Define and manipulate JavaScript object literals.
* Create and work with arrays and common array methods.
* Iterate over arrays to render content into the DOM.

### 1. Defining & Accessing Objects
1. In your index.html, inside the `<script>` tag, add: 
```js
const person = {
	firstName: 'Alice',
	lastName: 'Smith',
	age: 23
};

console.log(person);
console.log('Name:', person.firstName, person.lastName);
console.log(`Age: ${person.age}`);
```

2. Refresh and view the person object and its properties in the Console.

⠀**Exercise:**
* Add a new property occupation (e.g., 'Student') to person and log it.
⠀
### 2. Modifying & Destructuring Objects
1. Below your existing code, update a property: 
```js
person.age = 24;
console.log('Updated age:', person.age);
```

2. Use object destructuring to extract firstName and age:

```js
const { firstName, age } = person;
console.log(`${firstName} is now ${age}.`);
```

⠀**Exercise:**
* Rename `lastName` to `surname` via destructuring in a new variable and log it.

⠀
### 3. Creating & Manipulating Arrays
1. Define an array of strings:

```js
const fruits = ['Apple', 'Banana', 'Cherry'];
console.log(fruits);
console.log('First fruit:', fruits[0]);
console.log('Count:', fruits.length);
```

2. Add and remove elements:

```js
fruits.push('Date');
console.log('After push:', fruits);
fruits.shift();
console.log('After shift:', fruits);
```

⠀**Exercise:**
* Use `pop()` to remove the last fruit and log the removed item.
* Insert a new fruit at index 1 using `splice()`.

### 4. Iterating & Rendering Lists
1. In your HTML, add below your button:

```html
<ul id="fruit-list" class="mt-4 list-disc list-inside text-gray-800"></ul>
```

2. In your `<script>`, select the list and append items:

```js
const listEl = document.getElementById('fruit-list');
fruits.forEach(fruit => {
	const li = document.createElement('li');
	li.textContent = fruit;
	listEl.appendChild(li);
});
```

⠀**Exercise:**
* Use `map()` to create a new array of uppercase fruit names and render that instead.

### 5. Array of Objects
1. Define an array of objects: 
```js
const todos = [
	{ id: 1, task: 'Study JavaScript', done: true },
	{ id: 2, task: 'Complete worksheet', done: true },
	{ id: 3, task: 'Review notes', done: false }
];
```

2. Render the tasks with their status:

```js
const todoList = document.createElement('ul');
todos.forEach(item => {
	const li = document.createElement('li');
	li.textContent = `${item.task} — ${item.done ? '✅' : '❌'}`;
	document.body.appendChild(li);
});
```

⠀**Exercise:**
* Use `filter()` to create an array of only undone tasks and log it
* Toggle the done status of the first todo and re-render


#jsfundamentals