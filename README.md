# CSS3 Transitions, Animations, and Advanced JavaScript Functions

## Objectives

Create smooth CSS transitions and animations.
Use JavaScript functions for dynamic behavior.
Implement local storage for data persistence.

## Instructions
Add CSS animations to elements like buttons or images.

>[!NOTE]
> - Write a JavaScript function that:
> - Stores and retrieves user preferences using localStorage.
> - Implements an animation triggered by user actions.

## Tasks

Create a CSS animation.
Store data in localStorage.
Apply JavaScript to trigger animations.

Happy Coding! 💻✨



/* styles.css */
button {
  transition: background-color 0.3s ease, transform 0.3s ease;
}

button:hover {
  background-color: #4caf50;
  transform: scale(1.1);
}

@keyframes example {
  from {opacity: 0;}
  to {opacity: 1;}
}

img {
  animation: example 2s;
}


Add Javascript
// script.js
function saveUserPreferences(preferences) {
  localStorage.setItem('userPreferences', JSON.stringify(preferences));
}


JavaScript functions 
// script.js
function getUserPreferences() {
  const preferences = localStorage.getItem('userPreferences');
  return preferences ? JSON.parse(preferences) : {};
}


JavaScript implementation 
// script.js
document.addEventListener('DOMContentLoaded', () => {
  const button = document.querySelector('button');
  
  // Apply saved preferences
  const preferences = getUserPreferences();
  if (preferences.buttonColor) {
    button.style.backgroundColor = preferences.buttonColor;
  }

  // Detect button click and change color
  button.addEventListener('click', () => {
    button.style.backgroundColor = '#4caf50';
    
    // Save user preference
    saveUserPreferences({ buttonColor: '#4caf50' });
  });
});



Implementation test 
<!-- index.html -->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="styles.css">
  <title>CSS Animations and Local Storage</title>
</head>
<body>
  <button>Click Me!</button>
  <img src="image.jpg" alt="Example Image">
  <script src="script.js"></script>
</body>
</html>
