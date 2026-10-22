# BIC21203 Lab 4b: Client-Side Scripting (JSON and jQuery)

**Name:** Muhammad Akmal Asri Bin Kamal
**Student ID:** CI250026
**Course:** BIC21203 Web Development
**Faculty:** Faculty of Computer Science and Information Technology, UTHM

## About

This lab creates a JSON dataset, loads and displays selected data with the native `fetch()` API, and compares native DOM operations with jQuery 4.0.0. Text is displayed with `textContent` and `createElement()` (no `innerHTML`).

## Project Structure

| File | Description |
| --- | --- |
| `index.html` | Home page with links to Q1, Q2 and Q3 |
| `books.json` | Question 1: book data in JSON |
| `books.html` | Question 2: loads `books.json` with `fetch()` and displays the data |
| `jquery-dom.html` | Question 3: jQuery DOM and event operations |

`books.html` and `jquery-dom.html` have a Back button that returns to `index.html`.

## Setup Instructions

`books.html` must run on a local server, because `fetch()` cannot read local files opened with `file://`.

1. Install [Visual Studio Code](https://code.visualstudio.com/).
2. Open the Extensions panel (`Ctrl+Shift+X`), search for **Live Server** (by Ritwick Dey) and click **Install**.
3. Download or clone this repository, then open the project folder with **File → Open Folder**.
4. Right-click `index.html` and choose **Open with Live Server** (or click **Go Live** at the bottom right).
5. The browser opens at an address like `http://127.0.0.1:5500/`. Choose a question from the home page.

`jquery-dom.html` loads jQuery from the official CDN (`https://code.jquery.com/jquery-4.0.0.min.js`), so it needs an internet connection.

## Question 1: Create and Structure JSON Data

`books.json` has a top-level `"books"` array with two book objects. Each book contains:

- `title` (string)
- `author` (string)
- `publicationYear` (number)
- `genres` (array of strings)

The file uses double-quoted property names and has no trailing commas. It opens from `index.html` in a new tab, and VS Code shows no problems for it.

### Screenshots
![books.json file](screenshots/q1-json.png)
![No problems in VS Code](screenshots/q1-no-problems.png)

## Question 2: Retrieve and Display JSON Data

`books.html` reads `books.json` with `fetch()` and `async/await`, then shows the following in the page:

- (a) Title of the first book: The Great Gatsby
- (b) Author of the second book: Harper Lee
- (c) Genres of both books, grouped by title:
  - The Great Gatsby — Fiction, Classics
  - To Kill a Mockingbird — Fiction, Coming-of-Age

If the file cannot be loaded or the JSON is invalid, a user-friendly error message is shown instead.

### Screenshots
![Q2 output on a local server](screenshots/q2-output.png)
![Q2 error message](screenshots/q2-error.png)

## Question 3: Compare Native JavaScript and jQuery

`jquery-dom.html` uses the jQuery equivalents of the three native operations:

| Native JavaScript | jQuery |
| --- | --- |
| `document.getElementById("myElement").textContent = "Modified Text";` | `$("#myElement").text("Modified Text");` |
| `document.querySelector("#myDIV").classList.add("myStyle");` | `$("#myDIV").addClass("myStyle");` |
| `document.getElementById("myButton").addEventListener("click", ...)` | `$("#myButton").on("click", ...)` |

When the page loads, the text of `#myElement` becomes "Modified Text" and `#myDIV` gets the `myStyle` class (coral background). Clicking **Click me** shows the alert "Button clicked!".

### Screenshots
![Q3 page after loading](screenshots/q3-page.png)
![Q3 alert after clicking the button](screenshots/q3-alert.png)
