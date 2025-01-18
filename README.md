# ReferenceError: Cannot read properties of null (reading 'style') in HTML

This repository demonstrates a common yet often overlooked error in HTML: attempting to access a DOM element before it has been fully loaded by the browser.  The error manifests as a `ReferenceError: Cannot read properties of null (reading 'style')`.

## The Problem

The bug.html file contains a script that tries to modify the style of a div element.  However, if the script executes *before* the div is fully parsed by the browser, `document.getElementById('myDiv')` will return `null`, leading to the error.

## The Solution

The bugSolution.html file provides a solution using the DOMContentLoaded event listener. This ensures that the script only executes after the entire HTML document has been parsed, thereby preventing the `ReferenceError`.

This demonstrates the importance of carefully considering the order of script execution and DOM element availability when writing JavaScript that interacts with the HTML Document Object Model (DOM).