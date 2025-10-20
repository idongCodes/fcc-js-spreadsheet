# **✨ Welcome to My JavaScript Spreadsheet Engine\! ✨**

Hey there\! Welcome to the code behind my fully functional, web-based spreadsheet application, built from scratch with pure JavaScript. This wasn't just about making a grid of inputs; this was a deep dive into the world of functional programming, data parsing, and dynamic UI manipulation. I'm thrilled to walk you through how I brought this to life and what I learned along the way\!

## **🚀 What I Built & How It Works**

I created a powerful formula evaluation engine that can handle mathematical operations, cell references, ranges, and a whole library of custom spreadsheet functions. It all starts the moment you type \= into a cell\!

Here’s a peek into the magic behind the curtain:

1. **The Core Evaluator (`evalFormula`):** This is the heart of the operation\! When you enter a formula like `=SUM(A1:A5) + C2`, this function kicks off a recursive journey. I learned to use **recursion** here to continuously evaluate a formula until it resolves into a final value. It was a fantastic lesson in creating functions that call themselves to solve complex, nested problems.  
2. **Unpacking the Formula:**  
   * **Range Expansion:** My first challenge was turning a range like `A1:C3` into an actual list of values. I mastered **Regular Expressions** to find these patterns and wrote helper functions (`range`, `charRange`) to expand them. I learned so much about manipulating character codes (`charCodeAt`) and using `Array.fill()` with `.map()` to generate dynamic arrays.  
   * **Cell References:** Next, I used another regex to find individual cell references (like `B4`) and replace them with their corresponding values. This taught me the power of the `.find()` method to search through my `cells` array and pull out the data I needed.  
3. **The Function Engine (`applyFunction`):** This is where functional programming truly shines\!  
   * I built a "dictionary" of functions as a JavaScript object (`spreadsheetFunctions`). This taught me how to use objects to map strings to actual functions, making the code incredibly organized and extensible.  
   * I learned to parse function calls like `SUM(...)` or `AVERAGE(...)` and apply them to the list of numbers. This solidified my understanding of **higher-order functions** like `.map()`, `.reduce()` (for `sum`), and `.filter()` (for my `even` function). I even implemented `median`, `nodupes` (using the modern `Set` object\!), and fun array methods like `.slice()` for `firsttwo` and `lasttwo`.  
4. **Solving Math with Style (`infixEval`):** I couldn't just evaluate math from left to right\! I learned how to handle the **order of operations** (PEMDAS/BODMAS). I did this by recursively applying a high-precedence function for multiplication and division first, before moving on to addition and subtraction. Using the `.replace()` method with a callback function was a huge "aha\!" moment for me.

## **💻 Building the Interactive Grid**

The logic is only half the story\! I dynamically created the entire 99x10 grid using the `window.onload` event. This was a masterclass in **DOM Manipulation**. I learned how to create elements (`document.createElement`), assign properties, and append them to the container entirely with code.

The `update` function ties it all together, listening for any `onchange` event. This taught me about **event-driven programming**, where the application sits and waits for the user to act before kicking off the entire evaluation engine.

## **🎓 Key Skills & Concepts I Mastered**

This project was an incredible learning experience. I didn't just write code; I built a system. Here are the key concepts I now understand deeply:

* **Functional Programming:** I learned to think in terms of pure functions, composition, and immutability. Using higher-order functions like `map`, `filter`, and `reduce` is now second nature\!  
* **Recursion:** I tackled complex, nested problems by writing functions that elegantly call themselves until a base case is met.  
* **Advanced Regular Expressions:** I went beyond simple matches and used regex with callback functions to find, capture, and transform strings in powerful ways.  
* **DOM Manipulation & Events:** I can now build a dynamic, interactive UI from a blank HTML page and make it respond to user input.  
* **Algorithmic Thinking:** I designed a multi-step process for parsing and evaluating a complex string, from expanding ranges to calculating the final mathematical result.

Thanks for stopping by to check out my project\! It was a challenging but incredibly rewarding build.

## **📝 How to Use the Spreadsheet**

Getting started is easy\! The application functions like a classic spreadsheet but with a powerful custom engine under the hood.

1. **Enter Data:** Click on any cell and type in numbers or text.  
2. **Write a Formula:** To start a calculation, you must begin your entry with an equals sign (`=`).  
   * **Simple Math:** `=10 * 5`  
   * **Cell References:** `=A1 + B2`  
   * **Ranges:** Use a colon (`:`) to select a range of cells, like `A1:A10`.  
3. **Use Built-in Functions:** I've included a rich library of functions. They are **not** case-sensitive, so sum works just like `SUM`.  
   * `=SUM(A1:A10)` \- Adds all numbers in the range.  
   * `=AVERAGE(B1:B5)` \- Calculates the average.  
   * `=MEDIAN(1, 5, 2, 8, 7)` \- Finds the middle value.  
   * `=NODUPES(C1:C5)` \- Returns only the unique values from a range.

Just type your formula and press Enter to see the magic happen\!
