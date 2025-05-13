#HTML
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Interactive Assignment</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <button id="changeTextBtn">Click Me!</button>
  <div id="hoverBox">Hover over me!</div>
  <input type="text" id="keypressInput" placeholder="Type something...">
  <div id="imageGallery">
    <img src="https://via.placeholder.com/150" alt="Image 1">
    <img src="https://via.placeholder.com/150" alt="Image 2">
  </div>

  <script src="script.js"></script>
</body>
</html>
# style.css
#hoverBox {
  width: 200px;
  height: 100px;
  background-color: lightblue;
  text-align: center;
  line-height: 100px;
  margin: 20px;
  cursor: pointer;
}

#imageGallery img {
  width: 100px;
  height: 100px;
  margin: 10px;
  transition: transform 0.2s;
}

#imageGallery img:hover {
  transform: scale(1.2);
}
# script.js
// Button click changes text
document.getElementById('changeTextBtn').addEventListener('click', function() {
  this.innerHTML = 'You clicked me!';
});

// Hover effect on a box
document.getElementById('hoverBox').addEventListener('mouseover', function() {
  this.style.backgroundColor = 'lightgreen';
});
document.getElementById('hoverBox').addEventListener('mouseout', function() {
  this.style.backgroundColor = 'lightblue';
});

// Keypress detection
document.getElementById('keypressInput').addEventListener('keyup', function(event) {
  console.log('You typed: ' + event.key);
});

// Bonus: Double-click or long press action
let lastClickTime = 0;
document.getElementById('changeTextBtn').addEventListener('dblclick', function() {
  alert('Double clicked!');
});

// Long press detection
let longPressTimer;
document.getElementById('hoverBox').addEventListener('mousedown', function() {
  longPressTimer = setTimeout(() => {
    alert('Long press detected!');
  }, 1000); // Trigger after 1 second
});
document.getElementById('hoverBox').addEventListener('mouseup', function() {
  clearTimeout(longPressTimer); // Cancel if the user releases the mouse before 1 second
});

#FORM VALIDATION
<form id="myForm">
  <input type="email" id="email" placeholder="Enter email" required>
  <input type="password" id="password" placeholder="Enter password" required minlength="8">
  <button type="submit">Submit</button>
</form>

<script>
// Validate email function
function validateEmail(email) {
  const emailPattern = /^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,4}$/;
  return emailPattern.test(email);
}

// Validate password function
function validatePassword(password) {
  return password.length >= 8;
}

// Form submission handler
document.getElementById('myForm').addEventListener('submit', function(event) {
  const email = document.getElementById('email').value;
  const password = document.getElementById('password').value;

  if (!validateEmail(email)) {
    event.preventDefault();
    alert('Please enter a valid email address!');
  } else if (!validatePassword(password)) {
    event.preventDefault();
    alert('Password must be at least 8 characters long!');
  } else {
    alert('Form submitted successfully!');
  }
});
</script>
#ANIMATION ON HOVER
#hoverBox {
  width: 200px;
  height: 100px;
  background-color: lightblue;
  text-align: center;
  line-height: 100px;
  margin: 20px;
  cursor: pointer;
  transition: transform 0.3s ease;
}

#hoverBox:hover {
  transform: scale(1.1);
}
