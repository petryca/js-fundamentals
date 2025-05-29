# Worksheet 1:  HTML & Tailwind Refresher

**Objective:**
* Revisit basic HTML structure and familiarize yourself with Tailwind utility classes for styling.

### 1. Boilerplate Setup
1. Create a new file named index.html.
2. Add the standard HTML5 boilerplate:

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>Tailwind Refresher</title>
	<!-- Tailwind CSS CDN -->
	<script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100 min-h-screen flex items-center justify-center">
	<!-- Content will go here -->
	<div class="bg-white p-8 rounded-lg shadow-md">
    	<h1 class="text-2xl font-bold text-blue-600 mb-4">Hello, Tailwind!</h1>
    	<p class="text-gray-700">This is a basic HTML & Tailwind setup.</p>
  	</div>
</body>
</html>
```

**Tip:** Save the file and open it in your browser to see the styled page.

### 2. Inspecting the Page
1. Right-click on the heading (Hello, Tailwind!) and select **Inspect** (or press F12).
2. In the **Elements** panel, observe the <h1> element and note the Tailwind classes applied.
3. Experiment by toggling or editing classes directly in DevTools—e.g., change text-blue-600 to text-red-500.

⠀**Exercise:**
* Change the heading color to red by editing the class in DevTools.
* Add underline to the <p> element and observe the effect.

### 3. Playing with Utility Classes
1. In your code editor, modify the <div> container:
   - Add max-w-md to limit its width.
   - Add mx-auto to center it horizontally if needed.
2. Adjust padding and margin:
   - Change p-8 to p-4 and notice the smaller padding.
   - Add mt-6 to the <h1> for extra top margin.

⠀**Exercise:**
* Set the container’s background to a light purple using bg-purple-100.
* Increase the paragraph’s font size with text-lg.

### 4. Adding New Elements
1. Below the existing <p>, insert a button:

```html
<button id="change-text" class="mt-6 px-4 py-2 bg-green-500 text-white rounded hover:bg-green-600">Click Me</button>
```

2. Save and refresh. Notice the styled button.

⠀**Exercise:**
* Change the button’s text to “Press Here” in your code editor.
* Add `focus:outline-none focus:ring-2 focus:ring-green-300` to the button.

⠀
#jsfundamentals