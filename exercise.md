# Vanilla JavaScript Exercise Sheet

## **Objective**
Create a small “Personal Notes” web page that allows the user to:
- Enter their name
- View a greeting
- Write and save notes
- Display the current time
- Fetch and display a user profile from an external API
- Persist data across sessions using localStorage


## Part 1: HTML & Tailwind Setup

1. Create a new file called `dashboard.html`.
2. Add the HTML5 boilerplate and include Tailwind CSS using the CDN.
3. Inside the `<body>`, create the following:
   - A heading `<h1>` styled with `text-2xl font-bold text-blue-700`
   - An input to enter a name and a greeting placeholder (`<p id="greeting">`)
   - A textarea to write notes, and a button labeled "Save Note"
   - A div to show the saved note
   - A button labeled "Show Current Time"
   - A button labeled "Load Profile"
   - A div with id `profile` to show the fetched user profile


## Part 2: JavaScript Interactions

Add the following logic in a `<script>` tag before `</body>`:

### 1. Greeting the User
- When the user types into the name input field, update `#greeting` in real time:  
  _“Hello, David!”_
- Save the name to `localStorage` so it is restored after reload.

### 2. Saving Notes
- When the "Save Note" button is clicked, store the textarea content in `localStorage` under key `"myNote"`.
- Display the note in the `div` under the button, even after refresh.

### 3. Show Current Time
- When "Show Current Time" is clicked, display the current time in a styled `<p>`. Use `toLocaleTimeString()`.
- Use a reusable function named `getCurrentTime()`.

### 4. Fetch Profile
- When the user clicks "Load Profile", fetch user data from:  
  `https://jsonplaceholder.typicode.com/users/1`
- Display their name and email in the `#profile` div.
- Use `async/await` syntax and show a loading message during the fetch.


## Bonus Challenges

- Disable the "Save Note" button when the textarea is empty.
- Add a "Clear All" button to remove both the saved name and note from `localStorage`.