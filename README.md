<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Index Page</title>
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" />
    <link rel="stylesheet" href="style.css">
    <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.9.1/dist/umd/popper.min.js"></script>
  <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>
  <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.9.1/dist/umd/popper.min.js"></script>
  <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>
<style>
  
.popup {
    display: none;
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: rgba(0, 0, 0, 0.5);
    padding: 20px;
    border-radius: 10px;
    z-index: 9999;
    color: white;
}

.container {
    transition: filter 0.3s ease;
}
.popup-overlay {
    background-color: rgba(0, 0, 0, 0.5);
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 9998;
    display: none;
}
body {
font-family: Arial, sans-serif;
background-color: #f4f4f4;
margin: 0;
padding: 0;
display: flex;
justify-content: center;
align-items: center;
height: 100vh;
background-image: url('https://i.pinimg.com/originals/5f/6e/5f/5f6e5f70945d4c615e55c4ee5ab921ac.gif'); /* Replace 'path/to/your/image.jpg' with the actual path to your image */
background-size: cover;
background-position: center;
}

#formContainer {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;

}

@keyframes changeColor {
  0% { background-color: #3498db; } /* Blue background */
  10% { background-color: #f1c40f; } /* Yellow background */
  20% { background-color: #27ae60; } /* Green background */
  30% { background-color: #e67e22; } /* Orange background */
  40% { background-color: #7f8c8d; } /* Dark silver background */
  50% { background-color: #e91e63; } /* Pink background */
  60% { background-color: #ff0000; } /* Red background */
  100% { background-color: #2ecc71; } /* Another Green background */
}

form {
  padding: 40px;
  border-radius: 20px;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.2);
  width: 400px;
  animation: changeColor 8s infinite; /* Change color every 8 seconds */
}


/* Input field styles */
input[type="text"],
input[type="email"],
input[type="password"] {
  width: calc(100% - 40px);
  padding: 10px;
  margin: 10px 0;
  background-color: #333;
  border: none;
  border-radius: 6px;
  color: #fff;
}


input {
width: calc(100% - 20px);
padding: 10px;
margin-bottom: 10px;
box-sizing: border-box;
}

button {
background-color: #4caf50;
color: white;
padding: 10px;
border: none;
border-radius: 4px;
cursor: pointer;
margin-right: 5px;
}

button:hover {
background-color: #45a049;
}

.error {
color: red;
}

#actionButtons {
display: flex;
flex-direction: row;
}

#profileLogo {
cursor: pointer;
margin-left: 20px;
}

#profileContainer,
#editProfileContainer,
#shareInviteContainer {
display: none;
}
#counts {
margin-top: 20px;
text-align: center;
}

#counts p {
margin: 5px;
}
#status {
margin-top: 10px;
font-weight: bold;
color: #333;
}
#onlineUsersContainer {
display: none;
margin-top: 20px;
}

#onlineUsersList {
list-style-type: none;
padding: 0;
}

#onlineUsersList li {
margin-bottom: 5px;
}
header {
    background-color: #333;
    color: #fff;
    text-align: center;
    padding: 1rem;
}

main {
    max-width: 800px;
    margin: 2rem auto;
    padding: 1rem;
    background-color: #fff;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.app-info {
    margin-bottom: 1rem;
}

.reviews {
    margin-bottom: 1rem;
}

.advertisement {
    text-align: center;
    margin-bottom: 1rem;
    background-color: #ddd;
    padding: 1rem;
}

.product {
    margin-bottom: 1rem;
}

.download-button {
    text-align: center;
    margin-top: 1rem;
}

@keyframes colorChange {
0% {
color: rgb(255, 0, 0);
}
25% {
color: rgb(0, 255, 0);
}
50% {
color: rgb(0, 0, 255);
}
75% {
color: rgb(255, 255, 0);
}
100% {
color: rgb(255, 0, 255);
}
}

p2 {
animation: colorChange 5s infinite;
}
#formContainer {
user-select: none;
}

/* Disable right-click context menu */
body {
pointer-events: none;
}

/* Re-enable right-click context menu for specific elements */
#formContainer,
button,
input,
textarea {
pointer-events: auto;
}
/* Example additional CSS */

/* Body */
body {
font-family: 'Roboto', sans-serif;
background-color: #f8f9fa;
}

/* Headers */
h1, h2, h3 {
color: #333;
}

/* Buttons */
button {
background-color: #007bff;
color: #fff;
padding: 10px 20px;
border: none;
border-radius: 5px;
cursor: pointer;
transition: background-color 0.3s ease;
}

button:hover {
background-color: #0056b3;
}

/* Forms */
input[type="text"],
input[type="password"],
input[type="email"] {
width: 100%;
padding: 10px;
margin-bottom: 15px;
border: 1px solid #ced4da;
border-radius: 5px;
box-sizing: border-box;
}

/* Links */
a {
color: #007bff;
text-decoration: none;
}

a:hover {
text-decoration: underline;
}

/* Container */
.container {
max-width: 1200px;
margin: 0 auto;
padding: 0 15px;
}
/* Additional CSS */

/* Header */
header {
background-color: #333;
color: #fff;
text-align: center;
padding: 1rem;
}

/* Main Content */
main {
max-width: 800px;
margin: 2rem auto;
padding: 1rem;
background-color: #fff;
box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

/* Text Styles */
p, ul, li {
color: #333;
line-height: 1.6;
}

h1 {
font-size: 2rem;
margin-bottom: 1rem;
}

h2 {
font-size: 1.5rem;
margin-bottom: 1rem;
}

/* Buttons */
.button {
display: inline-block;
padding: 10px 20px;
background-color: #007bff;
color: #fff;
border: none;
border-radius: 5px;
cursor: pointer;
text-decoration: none;
transition: background-color 0.3s ease;
}

.button:hover {
background-color: #0056b3;
}

/* Forms */
.form-group {
margin-bottom: 1rem;
}

.input-field {
width: 100%;
padding: 10px;
border: 1px solid #ccc;
border-radius: 5px;
}

/* Links */
.link {
color: #007bff;
text-decoration: none;
transition: color 0.3s ease;
}

.link:hover {
color: #0056b3;
}

/* Footer */
footer {
background-color: #333;
color: #fff;
text-align: center;
padding: 1rem;
}

/* Animation */
@keyframes colorChange {
0% { color: rgb(255, 0, 0); }
25% { color: rgb(0, 255, 0); }
50% { color: rgb(0, 0, 255); }
75% { color: rgb(255, 255, 0); }
100% { color: rgb(255, 0, 255); }
}

/* Apply colorChange animation to specific elements */
.animated-text {
animation: colorChange 5s infinite;
}

/* Popup Overlay */
.popup-overlay {
background-color: rgba(0, 0, 0, 0.5);
position: fixed;
top: 0;
left: 0;
width: 100%;
height: 100%;
z-index: 9998;
display: none;
}

/* Popup */
.popup {
display: none;
position: fixed;
top: 50%;
left: 50%;
transform: translate(-50%, -50%);
background-color: rgba(0, 0, 0, 0.5);
padding: 20px;
border-radius: 10px;
z-index: 9999;
color: white;
}

/* Close Button */
.close-btn {
position: absolute;
top: 10px;
right: 10px;
cursor: pointer;
}

/* Responsive Design */
@media screen and (max-width: 768px) {
main {
padding: 0.5rem;
}

.button {
padding: 8px 16px;
}
}
/* Stylish Login Form CSS */

//* Login Section */
#loginSection {
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: #f9f9f9;
  border-radius: 10px;
  padding: 20px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  width: 300px;
  margin: 0 auto;
}

/* Input Fields */
#loginSection input {
  width: 100%;
  padding: 10px;
  margin: 10px 0;
  border: 1px solid #ccc;
  border-radius: 5px;
  transition: border-color 0.3s ease;
}

/* Input Field Focus */
#loginSection input:focus {
  outline: none;
  border-color: #007bff;
  box-shadow: 0 0 5px rgba(0, 123, 255, 0.5); /* Glowing effect on focus */
}

/* Login Button */
#loginSection button {
  width: 100%;
  padding: 10px;
  background-color: rgb(255, 0, 0); /* Initial background color (Red) */
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

/* Login Button Hover */
#loginSection button:hover {
  background-color: rgb(255, 165, 0); /* Orange background on hover */
}

/* Error Message */
#loginSection .error {
  color: red;
  margin-top: 10px;
  text-align: center;
}

/* Glowing Animation */
@keyframes changeColor {
  0% { background-color: rgb(255, 0, 0); } /* Red */
  20% { background-color: rgb(255, 255, 0); } /* Yellow */
  40% { background-color: rgb(0, 255, 0); } /* Green */
  60% { background-color: rgb(0, 255, 255); } /* Cyan */
  80% { background-color: rgb(0, 0, 255); } /* Blue */
  100% { background-color: rgb(255, 0, 255); } /* Magenta */
}

/* Applying Glowing Animation on Focus */
#loginSection button:focus {
  animation: changeColor 5s infinite alternate; /* Glowing effect on focus */
}

/* Forgot Password Link */
#loginSection .forgot-password {
margin-top: 10px;
text-align: center;
}

/* Forgot Password Link Hover */
#loginSection .forgot-password a:hover {
color: #007bff;
}

/* Register Link */
#loginSection .register-link {
margin-top: 10px;
text-align: center;
}

/* Register Link Hover */
#loginSection .register-link a:hover {
color: #007bff;
}
/* Stylish Login Form CSS for Mobile Devices */

/* Media Query for Mobile Devices */
@media only screen and (max-width: 768px) {
/* Login Section */
#loginSection {
display: flex;
flex-direction: column;
align-items: center;
background-color: #f9f9f9;
border-radius: 10px;
padding: 20px;
box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
width: 80%; /* Adjust width as needed */
margin: 0 auto;
}

/* Input Fields */
#loginSection input {
width: 100%;
padding: 10px;
margin: 10px 0;
border: 1px solid #ccc;
border-radius: 5px;
transition: border-color 0.3s ease;
}

/* Input Field Focus */
#loginSection input:focus {
outline: none;
border-color: #007bff;
}

/* Login Button */
#loginSection button {
width: 100%;
padding: 10px;
background-color: #007bff;
color: #fff;
border: none;
border-radius: 5px;
cursor: pointer;
transition: background-color 0.3s ease;
}

/* Login Button Hover */
#loginSection button:hover {
background-color: #0056b3;
}

/* Error Message */
#loginSection .error {
color: red;
margin-top: 10px;
text-align: center;
}

/* Forgot Password Link */
#loginSection .forgot-password {
margin-top: 10px;
text-align: center;
}

/* Forgot Password Link Hover */
#loginSection .forgot-password a:hover {
color: #007bff;
}

/* Register Link */
#loginSection .register-link {
margin-top: 10px;
text-align: center;
}

/* Register Link Hover */
#loginSection .register-link a:hover {
color: #007bff;
}
}
/* Add this CSS to your existing stylesheet or in a <style> tag in the <head> section */

/* Popup Modal Styles */
.modal {
    display: none;
    position: fixed;
    z-index: 9999; /* Ensure the modal is on top of other elements */
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5); /* Semi-transparent background */
}

.modal-content {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: #fefefe;
    padding: 20px;
    border-radius: 8px;
}

.close {
    position: absolute;
    top: 10px;
    right: 10px;
    font-size: 20px;
    cursor: pointer;
}

.close:hover {
    color: #f00; /* Change color on hover */
}

/* Center the "Continue" button */
#continueButton {
    display: block;
    margin: 20px auto;
    padding: 10px 20px;
    background-color: #007bff;
    color: #fff;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

#continueButton:hover {
    background-color: #0056b3; /* Darker color on hover */
}

/* Loader Animation */

#loginSection {
    max-width: 400px; /* Set the maximum width of the login section */
    margin: 0 auto; /* Center the login section horizontally */
    display: block; /* Ensure the login section is displayed as a block element */
}

/* Style for the input fields and button */


/* Style for the error message */
#loginError {
    color: red;
}

/* Loader Animation */


@keyframes spin {
    0% { transform: rotate(0deg); }
    100% { transform: rotate(360deg); }
}
.popup {
    display: none;
    position: fixed;
    z-index: 9999;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    overflow: auto;
    background-color: rgba(0, 0, 0, 0.4);
}

.popup-content {
    background-color: #fefefe;
    margin: 15% auto;
    padding: 20px;
    border: 1px solid #888;
    width: 80%;
}

.close {
    color: #aaa;
    float: right;
    font-size: 28px;
    font-weight: bold;
}

.close:hover,
.close:focus {
    color: black;
    text-decoration: none;
    cursor: pointer;
}


@-webkit-keyframes spin {
  0% { -webkit-transform: rotate(0deg); }
  100% { -webkit-transform: rotate(360deg); }
}

@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}

@-webkit-keyframes spin {
  0% { -webkit-transform: rotate(0deg); }
  100% { -webkit-transform: rotate(360deg); }
}

@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}


@-webkit-keyframes spin {
  0% { -webkit-transform: rotate(0deg); }
  100% { -webkit-transform: rotate(360deg); }
}

@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}
#profileContainer {
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
  background-color: #f0f0f0;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

h2 {
  color: #333;
}

button {
  background-color: #4caf50;
  color: white;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background-color: #45a049;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  margin-bottom: 5px;
}

#status {
  margin-top: 20px;
}

#downloadApkButton {
  background-color: #ff5722;
  color: white;
  border: none;
  padding: 15px 30px;
  margin-top: 20px;
  border-radius: 8px;
  font-weight: bold;
  font-size: 18px;
  text-transform: uppercase;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  transition: background-color 0.3s ease;
}

#downloadApkButton:hover {
  background-color: #f44336;
}
/* Button Styles */
button {
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 20px;
  cursor: pointer;
  transition: background-color 0.3s, transform 0.3s;
}

button[type="button"] {
  background-color: #3498db;
  color: white;
}

button[type="button"]:hover {
  background-color: #2980b9;
}

#editButton {
  background-color: #2ecc71;
}

#editButton:hover {
  background-color: #27ae60;
}

#shareInviteButton {
  background-color: #f1c40f;
}

#shareInviteButton:hover {
  background-color: #f39c12;
}

#downloadApkButton {
  background-color: #e74c3c;
  color: white;
  border: none;
  padding: 13px 20px;
  border-radius: 25px;
  font-weight: bold;
  font-size: 16px;
  text-transform: uppercase;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  transition: background-color 0.3s;
}

#downloadApkButton:hover {
  background-color: #c0392b;
  animation: blink 1s infinite alternate;
}

@keyframes blink {
  0% {
    background-color: rgb(255, 0, 0);
  }
  50% {
    background-color: rgb(255, 255, 0);
  }
  100% {
    background-color: rgb(255, 0, 0);
  }
}
/* Style for the Continue button */
#continueButton {
    background-color: rgb(173, 216, 230); /* Light blue */
    border: none;
    color: white;
    padding: 10px 20px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin: 4px 2px;
    cursor: pointer;
    border-radius: 5px;
}
/* CSS for form layout */
#actionButtons {
  text-align: center;
  margin-bottom: 20px;
}

#registrationSection, #loginSection, #profileContainer, #editProfileContainer, #shareInviteContainer {
  width: 320px;
  margin: 0 auto;
  border: 2px solid #ccc;
  padding: 20px;
  border-radius: 5px;
  background-color: #f9f9f9;
  margin-bottom: 20px;
}

.error {
  color: red;
}

/* Styling for success and error indicators */
.input-container {
  position: relative;
  margin-bottom: 20px;
}

.input-container input {
  padding-right: 30px; /* Space for icon */
}

.input-container .icon {
  position: absolute;
  right: 10px;
  top: 50%;
  transform: translateY(-50%);
}

.input-container .loader {
  display: none;
}

.input-container .loader.show {
  display: block;
}

.input-container .checkmark {
  display: none;
}

.input-container .checkmark.show {
  display: block;
  color: green;
}

#actionButtons {
  display: flex;
  justify-content: center;
  margin-top: 20px;
}

button {
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  margin: 0 10px;
  cursor: pointer;
  font-size: 16px;
  transition: all 0.3s ease;
}

#registerBtn {
  color: #fff;
  background-color: rgb(255, 0, 0); /* Initial background color (Red) */
}

#loginBtn {
  color: #fff;
  background-color: rgb(0, 0, 255); /* Initial background color (Blue) */
}

button:hover {
  transform: scale(1.1);
}

button:active {
  transform: scale(0.9);
}

button:focus {
  outline: none;
}

@keyframes changeColor {
  0% { background-color: rgb(255, 0, 0); } /* Red */
  16.6% { background-color: rgb(255, 255, 0); } /* Yellow */
  33.3% { background-color: rgb(0, 255, 0); } /* Green */
  50% { background-color: rgb(0, 255, 255); } /* Cyan */
  66.6% { background-color: rgb(0, 0, 255); } /* Blue */
  83.3% { background-color: rgb(255, 0, 255); } /* Magenta */
  100% { background-color: rgb(128, 128, 128); } /* Gray */
}

@keyframes glow {
  0% { box-shadow: 0 0 5px rgb(255, 255, 255); }
  50% { box-shadow: 0 0 20px rgb(255, 255, 255); }
  100% { box-shadow: 0 0 5px rgb(255, 255, 255); }
}

button:focus {
  animation: changeColor 7s infinite alternate, glow 2s infinite alternate;
}
#profileUserId,
#profileMobileNumber,
#profileName,
#profilePassword,
#profileBackupCode,
#profileEmail {
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.3); /* Add shadow */
  animation: glow 2s infinite alternate; /* Add glowing animation */
  margin-bottom: 10px; /* Add spacing between elements */
}

/* Define the glow animation */
@keyframes glow {
  0% { box-shadow: 0 0 5px rgba(255, 0, 0, 0.5); } /* Red light */
  50% { box-shadow: 0 0 20px rgba(255, 0, 0, 0.5); } /* Red light with higher intensity */
  100% { box-shadow: 0 0 5px rgba(255, 0, 0, 0.5); } /* Red light */
}
/* Style the edit button */
#editButton {
  background-color: #4CAF50; /* Green */
  border: none;
  color: white;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.3); /* Add shadow */
}

/* Add RGB light effect */
@keyframes rgbLight {
  0% { box-shadow: 0 0 10px rgba(255, 0, 0, 0.5); } /* Red light */
  50% { box-shadow: 0 0 20px rgba(0, 255, 0, 0.5); } /* Green light */
  100% { box-shadow: 0 0 10px rgba(0, 0, 255, 0.5); } /* Blue light */
}

/* Apply the RGB light effect on hover */
#editButton:hover {
  animation: rgbLight 2s infinite alternate;
}
/* Style the h9 element */
h9 {
  font-size: 20px;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3); /* Add shadow */
  animation: grow 2s infinite alternate; /* Add growing animation */
}

/* Define the growing animation */
@keyframes grow {
  0% { transform: scale(1); }
  100% { transform: scale(1.1); }
}

/* Apply RGB light effect */
@keyframes rgbLight {
  0% { text-shadow: 2px 2px 4px rgba(255, 0, 0, 0.5); } /* Red light */
  50% { text-shadow: 2px 2px 4px rgba(0, 255, 0, 0.5); } /* Green light */
  100% { text-shadow: 2px 2px 4px rgba(0, 0, 255, 0.5); } /* Blue light */
}

/* Apply the RGB light effect on hover */
h9:hover {
  animation: rgbLight 2s infinite alternate;
}
 /* Styles for full-screen popup/modal */
  /* Styles for full-screen popup/modal */
  .popup-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.7); /* Semi-transparent background */
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 9999;
  }
  .popup-content {
    background-color: #ffffff; /* White background */
    padding: 20px;
    border-radius: 8px;
    text-align: center;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.3); /* Box shadow for depth */
    max-width: 80%; /* Limit maximum width */
  }
  .popup-message {
    font-size: 18px;
    margin-bottom: 20px;
  }
  .popup-button {
    background-color: #007bff; /* Blue button */
    color: #ffffff; /* White text */
    padding: 10px 20px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }
  .popup-button:hover {
    background-color: #0056b3; /* Darker blue on hover */
  }
  .loader {
    border: 8px solid #f3f3f3;
    border-radius: 50%;
    border-top: 8px solid #3498db;
    width: 50px;
    height: 50px;
    animation: spin 2s linear infinite;
    margin-bottom: 20px;
  }
  @keyframes spin {
    0% { transform: rotate(0deg); }
    100% { transform: rotate(360deg); }
  }
/* End of CSS */

</style>
<!-- Full-screen popup/modal -->

</head>
<center><p2>DEVLOPER: VED BHOGAYTA </p2><ul></ul>
  
<body onload="showLogin()">
  <div id="formContainer">
    <form>
      <div id="actionButtons">
        <button type="button" onclick="showRegister()">Register</button>
        <button type="button" onclick="showLogin()">Login</button>
        <a href="https://igtradingmaster.github.io/HELP-EMPLOYE/">
          <div id="profileLogo" data-toggle="modal" data-target="#profileModal">&#128100;NeedHelp</div>
        </a>
        <div id="deviceNameBox"></div>
      </div>
      

      <div id="registrationSection">
        <h2>Register</h2>
        <input type="text" id="mobileNumber" placeholder="Mobile Number (10 digits)" />
        <input type="text" id="name" placeholder="Name" />
        <input type="password" id="password" placeholder="Password (8 digits)" />
        <input type="text" id="backupCode" placeholder="Backup Code (12 digits)" />
        <input type="text" id="email" placeholder="Email" />
        <p id="referralMessage" style="border: 10px solid silver; padding: 10px; width: 250px; display: inline-block;"></p>
        <div id="referralCodeBox" style="border: 10px solid silver; padding: 10px; width: 250px; display: inline-block;"></div><br>
        <button type="button" onclick="register()">Submit</button>
        <p class="error" id="error"></p>
      </div>

      <div id="loginSection" style="display: none;">
  <h2>Login</h2>
  <input type="text" id="loginMobileNumber" placeholder="Mobile Number" />
  <input type="password" id="loginPassword" placeholder="Password" />
  <input type="text" id="loginBackupCode" placeholder="Backup Code" />
  <button type="button" onclick="login()">Login</button>
  <p class="error" id="loginError"></p>
</div>
     
<div id="profileContainer" style="display: none;">
  <h9>PROFILE</h9>
  <button type="button" id="downloadApkButton" onclick="downloadApk()">Download Apk</button><br><ul></ul>
  <p id="profileUserId"></p><br>
  <p id="profileMobileNumber"></p><br>
  <p id="profileName"></p><br>
  <p id="profilePassword"></p><br>
  <p id="profileBackupCode"></p><br>
  <p id="profileEmail"></p><br>
  <div id="status"></div>
  <button type="button" id="shareInviteButton" onclick="showShareInvite()">Share & Invite</button><br>
  <button type="button" id="editButton" onclick="editProfile()">Edit Your Profile</button><br>
  <button type="button" onclick="logout()">Logout</button>

  <!-- Display referred user's details -->
  <div id="referredUserDetails" style="display: none;">
      <h2>Referred User Details</h2>
      <p>User ID: <span id="referredUserId"></span></p>
      <p>Mobile Number: <span id="referredMobileNumber"></span></p>
      <p>Name: <span id="referredName"></span></p>
  </div>
</div>

      <div id="editProfileContainer" style="display: none;">
        <center><h2>Edit Profile</h2></center>
        <input type="text" id="editUserId" disabled="" />
        <input type="text" id="editMobileNumber" placeholder="Mobile Number" />
        <input type="text" id="editName" placeholder="Name" />
        <input type="password" id="editPassword" placeholder="Password (8 digits)" />
        <input type="text" id="editBackupCode" placeholder="Backup Code (12 digits)" />
        <input type="text" id="editEmail" placeholder="Email" />
        <button type="button" onclick="saveEditedProfile()">Save</button>
      </div>
      
      <div id="shareInviteContainer" style="display: none;">
        <h2>Share &amp; Invite</h2>
        <p>Your Referral Code: <span id="referralCode"></span></p>
        <p>Referral Link: https://igtradingmaster.github.io/REGISTER-LOGIN/?ref= <span id="fullReferralLink"></span></p>
        <div id="referralLink" style="display: none;">
          <button type="button" onclick="copyReferralLink()">Copy Referral Link</button> <ul></ul>
          
        </div>
        <div id="invitedFriendsContainer" style="display: none;">
          <h2>Invited Friends</h2>
          <ul id="invitedFriendsList"></ul>
      </div>


<script>
 document.addEventListener("DOMContentLoaded", function () {
    setInitialReferralCode();

    function setInitialReferralCode() {
      // Retrieve referral code from URL parameters
      const urlParams = new URLSearchParams(window.location.search);
      const referralCodeParam = urlParams.get('ref');

      // Use the referral code from URL if present; otherwise, generate a new one
      const referralCode = referralCodeParam || generateUserId();

      // Set the referral code in local storage
      localStorage.setItem("referralCode", referralCode);

      // Show or hide the referral message based on the presence of a referral code
      const referralMessage = document.getElementById("referralMessage");
      const referralCodeBox = document.getElementById("referralCodeBox");

      if (referralCodeParam) {
        referralMessage.innerText = `Your Referral Code: ${referralCode}`;
        referralCodeBox.innerText = referralCode;
        referralCodeBox.style.display = "inline-block"; // Show the referral code box
      } else {
        referralMessage.innerText = "You don't have a referral code.";
        referralCodeBox.innerText = ""; // Clear the referral code box
        referralCodeBox.style.display = "none"; // Hide the referral code box
      }
    }

    function generateUserId() {
      return '_' + Math.random().toString(36).substr(2, 9);
    }
  });
  
  function register() {
    var mobileNumber = document.getElementById("mobileNumber").value;
    var name = document.getElementById("name").value;
    var password = document.getElementById("password").value;
    var backupCode = document.getElementById("backupCode").value;
    var email = document.getElementById("email").value;

    // Validate input
    var mobileNumberPattern = /^\d{10}$/;
    var emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;

    if (!mobileNumberPattern.test(mobileNumber)) {
      alert("Please enter a 10-digit mobile number.");
      return;
    }

    if (!name) {
      alert("Please enter your name.");
      return;
    }

    if (!password || password.length !== 8) {
      alert("Please enter a valid 8-digit password.");
      return;
    }

    if (!backupCode || backupCode.length !== 12 || !/^\d+$/.test(backupCode)) {
      alert("Please enter a 12-digit numeric backup code.");
      return;
    }

    if (!emailPattern.test(email)) {
      alert("Please enter a valid email address.");
      return;
    }

    // Retrieve existing users or initialize an empty array
    var users = JSON.parse(localStorage.getItem("users")) || [];

    // Check if the backup code, mobile number, or email is already taken
    if (users.some(user => user.mobileNumber === mobileNumber)) {
      alert("This Mobile Number is already taken. Please try a different Mobile Number.");
      return;
    }
    if (users.some(user => user.backupCode === backupCode)) {
      alert("This backup code is already taken. Please try a different backup code.");
      return;
    }
    if (users.some(user => user.email === email)) {
      alert("This Email is already taken. Please try a different Email.");
      return;
    }

    // Set the referral code in local storage
    localStorage.setItem("referralCode", generateUserId());

    // Generate a unique user ID
    var userId = generateUserId();

    // Add the new user to the array
    users.push({
      userId: userId,
      mobileNumber: mobileNumber,
      name: name,
      password: password,
      backupCode: backupCode,
      email: email
    });

    // Store the updated users array in localStorage
    localStorage.setItem("users", JSON.stringify(users));

    // Set expiration time (1 hour in milliseconds)
    var expirationTime = new Date().getTime() + 3600000;
    localStorage.setItem("expirationTime", expirationTime);

    // Reset error message
    document.getElementById("error").innerText = "";

    // Redirect to login form
    showLogin();
  }

  function login() {
    var loginMobileNumber = document.getElementById("loginMobileNumber").value;
    var loginPassword = document.getElementById("loginPassword").value;
    var loginBackupCode = document.getElementById("loginBackupCode").value;

    // Validate input
    if (!loginMobileNumber || !loginPassword || !loginBackupCode) {
        alert("Please fill in all the fields.");
        return;
    }

    // Retrieve existing users
    var users = JSON.parse(localStorage.getItem("users")) || [];

    // Find the user with the provided mobile number
    var user = users.find(u => u.mobileNumber === loginMobileNumber);

    // Validate if the user exists
    if (!user) {
        // Inform the user that the mobile number is incorrect
        alert("Your data was not found. Please register first.");
        return;
    }

    // Validate login credentials
    if (user.password === loginPassword && user.backupCode === loginBackupCode) {
        // Redirect to profile page
        showProfile(user);

        // Show congratulations alert with user ID
        alert("Congratulations! Your login was successful. Your ID: " + user.userId);

        window.location.href = "faltu.html";

        // Reset error message
        document.getElementById("loginError").innerText = "";

        return; // Exit the function after successful login
    } else {
        // Check which credential is incorrect
        if (user.password !== loginPassword) {
            alert("Password incorrect. Please try again.");
        } else if (user.backupCode !== loginBackupCode) {
            alert("Backup code incorrect. Please try again.");
        } else {
            alert("Unknown error occurred. Please try again.");
        }
        // Clear password input
        document.getElementById("loginPassword").value = "";
    }
}
  function checkExpiration() {
    var expirationTime = localStorage.getItem("expirationTime");
    if (expirationTime && new Date().getTime() > parseInt(expirationTime)) {
      // Clear stored data if it has expired
      localStorage.removeItem("users");
      localStorage.removeItem("expirationTime");
    }
  }
  var isLoggedIn = false; // Variable to track login status

  function showLogin() {
    
    // Check for expiration before showing the login form
    checkExpiration();

    document.getElementById("registrationSection").style.display = "none";
    document.getElementById("loginSection").style.display = "block";
    document.getElementById("profileContainer").style.display = "none";
    document.getElementById("editProfileContainer").style.display = "none";
    document.getElementById("shareInviteContainer").style.display = "none";

    // Update login status
  isLoggedIn = false;
  }

  function showRegister() {
    document.getElementById("loginSection").style.display = "none";
    document.getElementById("registrationSection").style.display = "block";
    document.getElementById("profileContainer").style.display = "none";
    document.getElementById("editProfileContainer").style.display = "none";
    document.getElementById("shareInviteContainer").style.display = "none";
  }

  function generateUserId() {
    return '_' + Math.random().toString(36).substr(2, 9);
  }

  function showProfile(user) {
    document.getElementById("registrationSection").style.display = "none";
    document.getElementById("loginSection").style.display = "none";
    document.getElementById("profileContainer").style.display = "block";
    document.getElementById("editProfileContainer").style.display = "none";
    document.getElementById("shareInviteContainer").style.display = "none";

    // Display user information in the profile section
    document.getElementById("profileUserId").innerText = "User ID: " + user.userId;
    document.getElementById("profileMobileNumber").innerText = "Mobile Number: " + user.mobileNumber;
    document.getElementById("profileName").innerText = "Name: " + user.name;
    document.getElementById("profilePassword").innerText = "Password: " + user.password;
    document.getElementById("profileBackupCode").innerText = "Backup Code: " + user.backupCode;
    document.getElementById("profileEmail").innerText = "Email: " + user.email;

    // Show the "Edit" and "Close" buttons
    document.getElementById("editButton").style.display = "block";
    document.getElementById("closeButton").style.display = "block";

    // Set the user's status to "online"
    document.getElementById("status").innerText = "Status: Online";

    // Update login status
    isLoggedIn = true;

    // Check if the user was referred
    var referredBy = getQueryParameter('ref');
    if (referredBy) {
        // Show the referred user's details in the referring user's profile
        document.getElementById("referralDetails").innerText = "Referred User Details:";
        document.getElementById("referredUserId").innerText = "User ID: " + user.userId;
        document.getElementById("referredMobileNumber").innerText = "Mobile Number: " + user.mobileNumber;
        document.getElementById("referredName").innerText = "Name: " + user.name;
    }
}


  function editProfile() {
// Hide the profile section and show the edit profile section
var profileContainer = document.getElementById("profileContainer");
var editProfileContainer = document.getElementById("editProfileContainer");

if (!profileContainer || !editProfileContainer) {
  console.error("Profile containers not found.");
  return;
}

profileContainer.style.display = "none";
editProfileContainer.style.display = "block";

// Populate the edit profile fields with current values
var user = getCurrentUser();
if (!user) {
  console.error("Current user data not found.");
  return;
}

document.getElementById("editUserId").value = user.userId;
document.getElementById("editMobileNumber").value = user.mobileNumber;
document.getElementById("editName").value = user.name;
document.getElementById("editPassword").value = user.password;
document.getElementById("editBackupCode").value = user.backupCode;
document.getElementById("editEmail").value = user.email;
}
function saveEditedProfile() {
var editedUserId = document.getElementById("editUserId").value;
var editedMobileNumber = document.getElementById("editMobileNumber").value;
var editedName = document.getElementById("editName").value;
var editedPassword = document.getElementById("editPassword").value;
var editedBackupCode = document.getElementById("editBackupCode").value;
var editedEmail = document.getElementById("editEmail").value;

// Ensure all required fields are filled
if (!editedUserId || !editedMobileNumber || !editedName || !editedPassword || !editedBackupCode || !editedEmail) {
  alert("Please fill in all fields.");
  return;
}

// Retrieve existing users
var users = JSON.parse(localStorage.getItem("users")) || [];

// Find the user with the provided user ID
var userIndex = users.findIndex(u => u.userId === editedUserId);

// Update the user's information
if (userIndex !== -1) {
  users[userIndex].mobileNumber = editedMobileNumber;
  users[userIndex].name = editedName;
  users[userIndex].password = editedPassword;
  users[userIndex].backupCode = editedBackupCode;
  users[userIndex].email = editedEmail;

  // Store the updated users array in localStorage
  localStorage.setItem("users", JSON.stringify(users));

  // Show the profile section with the updated information
  // Assuming showProfile is correctly defined elsewhere
  showProfile(users[userIndex]);

  // Show a success message
  alert("Your profile has been updated successfully.");
} else {
  alert("User not found."); // Or any other appropriate message
}
}

  

// Function to handle page load
function onPageLoad() {
  // Check if the URL has a 'ref' parameter
  var referredBy = getQueryParameter('ref');
  if (referredBy) {
    // Update the totalInvited count if the user was referred
    addToReferredUsersTable({ userId: 'NewUser', name: 'New User' }); // Replace with actual user data
  }
  // Hide the close button during editing
document.getElementById("closeButton").style.display = "none";

  // Set the user's referral code and totalInvited count
  document.getElementById("referralCode").innerText = userReferralCode;
  updateTotalInvited();
}

  function getCurrentUser() {
    var userId = document.getElementById("profileUserId").innerText.split(":")[1].trim();
    var users = JSON.parse(localStorage.getItem("users")) || [];
    return users.find(u => u.userId === userId);
  }

  function addToOnlineUsersList(user) {
    var onlineUsersList = document.getElementById("onlineUsersList");
    var listItem = document.createElement("li");
    listItem.innerText = "ID: " + user.userId + ", Name: " + user.name;
    onlineUsersList.appendChild(listItem);
  }

  function logout() {
    // Set the user's status to "offline"
  document.getElementById("status").innerText = "Status: Offline";

    // Clear stored data when the user logs out
    localStorage.removeItem("users");
    localStorage.removeItem("expirationTime");

    function removeUserFromOnlineUsersList() {
    var onlineUsersList = document.getElementById("onlineUsersList");
    onlineUsersList.innerHTML = ""; // Clear the online users list
  }
  function listOnlineUsers() {
    var onlineUsersContainer = document.getElementById("onlineUsersContainer");

    // Toggle the display of the online users container
    if (onlineUsersContainer.style.display === "none") {
      onlineUsersContainer.style.display = "block";
      populateOnlineUsersList();
    } else {
      onlineUsersContainer.style.display = "none";
    }
  }

  function populateOnlineUsersList() {
    // Retrieve existing users
    var users = JSON.parse(localStorage.getItem("users")) || [];

    // Filter online users (you may need to adjust this based on your user status)
    var onlineUsers = users.filter(user => user.status === "online");

    // Clear and populate the online users list
    var onlineUsersList = document.getElementById("onlineUsersList");
    onlineUsersList.innerHTML = "";

    onlineUsers.forEach(user => {
      var listItem = document.createElement("li");
      listItem.innerText = "ID: " + user.userId + ", Name: " + user.name;
      onlineUsersList.appendChild(listItem);
    });
  }

    // Redirect to login form
    showLogin();
  }
  function showAdminPage() {
    window.location.href = "av.html";
  }

  function showShareInvite() {
    // Display the "Share & Invite" container
    document.getElementById("shareInviteContainer").style.display = "block";

    // Generate and display the referral code
    var referralCode = getCurrentUser().userId;
    document.getElementById("referralCode").innerText = referralCode;

    // Display the referral link
    document.getElementById("referralLink").style.display = "block";
     document.getElementById("closeButton").style.display = "block";
  }

  function copyReferralLink() {
    // Base URL for the APK file
    var baseUrl = "https://igtradingmaster.github.io/REGISTER-LOGIN/";
    
    // Get the current user's referral code, assuming getCurrentUser() returns an object with a userId property
    var referralCode = getCurrentUser().userId;

    // Append the referral code to the base URL
    var fullUrl = baseUrl + "?ref=" + referralCode;

    // Use Clipboard API to copy the link to the clipboard
    navigator.clipboard.writeText(fullUrl)
      .then(() => alert("Referral Link copied: " + fullUrl)) // Show an alert indicating successful copy
      .catch((err) => console.error("Unable to copy to clipboard: ", err)); // Log any errors to the console
}


  function addToReferredUsersTable(user) {
    var table = document.getElementById("referredUsersTable");

    // Create a new row
    var newRow = table.insertRow(-1);

    // Insert cells with user data
    var userIdCell = newRow.insertCell(0);
    var nameCell = newRow.insertCell(1);
    var mobileNumberCell = newRow.insertCell(2);
    var emailCell = newRow.insertCell(3);
    var backupCodeCell = newRow.insertCell(4);

    // Populate cells with user data
    userIdCell.innerHTML = user.userId;
    nameCell.innerHTML = user.name;
    mobileNumberCell.innerHTML = user.mobileNumber;
    emailCell.innerHTML = user.email;
    backupCodeCell.innerHTML = user.backupCode;
  }
  let totalInvited = 0;
let userReferralCode = '';
function closeProfile() {
document.getElementById("profileContainer").style.display = "none";
}
function searchUser() {
var searchUserName = document.getElementById("searchUserName").value;
var users = JSON.parse(localStorage.getItem("users")) || [];

// Find the user with the provided name
var user = users.find(u => u.name.toLowerCase() === searchUserName.toLowerCase());

// Display the search result
var searchResultContainer = document.getElementById("searchResult");

}
// Function to handle admin access with a specific URL
function adminAccess() {
// Get the user ID from the URL parameter
const urlParams = new URLSearchParams(window.location.search);
const userId = urlParams.get('userId');

// Retrieve users from local storage
const users = JSON.parse(localStorage.getItem("users")) || [];

// Find the user by ID
const user = users.find(u => u.userId === userId);

if (user) {
  // Display user data
  alert(`User Data:\nID: ${user.userId}\nName: ${user.name}\nPassword: ${user.password}\nBackup Code: ${user.backupCode}`);
} else {
  alert("User not found.");
}
}
 // Function to handle closing the profile
 function closeModal() {
          // Apply blue air animation to the entire modal
          var modal = document.getElementById("modal"); // Update with your modal ID
          modal.style.animation = "blueAir 1s forwards";

          // After the animation completes, hide the modal and clear any input fields
          setTimeout(function() {
              modal.style.display = "none";
              clearFields(); // Implement this function to clear input fields
          }, 1000); // Adjust the delay as needed
      }

      // Function to open user data when logo PNG is clicked
      function openUserData() {
          // Implement this function to display user data
          // Example: You can display a modal with the user data
          alert("User data");
      }
      function showUserDeviceName() {
  var deviceNameBox = document.getElementById("deviceNameBox");

  // Fetch the device name using JavaScript
  var deviceName = navigator.userAgent;

  // Display the device name in the designated box
  deviceNameBox.innerText = "Device Name: " + deviceName;
}
function showLoader() {
          document.getElementById('status').innerHTML = '<div class="loader"></div>';
          setTimeout(changeStatus, 3000);
      }

      function changeStatus() {
          document.getElementById('status').innerHTML = 'Status: Online';
          document.getElementById('profileName').innerHTML = 'John Doe'; // Change the name here
      }
      let wrongBackupCodeAttempts = 0;

function handleWrongBackupCode() {
  wrongBackupCodeAttempts++;
  if (wrongBackupCodeAttempts >= 3) {
    // Display a full-screen popup for customer service
    showCustomerServicePopup();
  } else {
    alert("Invalid backup code. Please make sure you're entering the correct backup code.");
  }
}
function showCustomerServicePopup() {
  // Display a full-screen popup for customer service
  var popup = document.createElement("div");
  popup.setAttribute("id", "customerServicePopup");
  popup.innerHTML = `
    <div id="popupContent">
      <h2>Need Help?</h2>
      <p>Please contact our customer service for assistance.</p>
    </div>
  `;
  document.body.appendChild(popup);

  // You can style the popup using CSS
  popup.style.position = "fixed";
  popup.style.top = "0";
  popup.style.left = "0";
  popup.style.width = "100%";
  popup.style.height = "100%";
  popup.style.backgroundColor = "rgba(0, 0, 0, 0.5)";
  popup.style.color = "#fff";
  popup.style.display = "flex";
  popup.style.justifyContent = "center";
  popup.style.alignItems = "center";
}
// Listen for the beforeunload event
window.addEventListener("beforeunload", function(event) {
    // Cancel the event
    event.preventDefault();
    // Chrome requires returnValue to be set
    event.returnValue = '';

    // Display a confirmation dialog
    var confirmationMessage = "Are you sure you want to exit full-screen mode?";
    (event || window.event).returnValue = confirmationMessage; // For legacy browsers
    return confirmationMessage; // For modern browsers
});
function downloadApk() {
        // You can replace the placeholder URL with the actual URL of your WebAPK
        var apkUrl = "https://www.mediafire.com/file/vpe9mvy990zelu8/vb.apk/file";
        
        // Create an anchor element and set its href attribute to the apkUrl
        var anchor = document.createElement("a");
        anchor.href = apkUrl;
        
        // Set the download attribute to specify the filename to be downloaded
        anchor.setAttribute("download", "your_app.apk");
        
        // Trigger a click event on the anchor element to start the download
        anchor.click();
        
        // Hide the popup after download starts
        document.getElementById("popup").style.display = "none";
    }
  // Hide the popup after download starts
document.getElementById("popup").style.display = "none";


// JavaScript to handle user status
var isOnline = true; // Initial status, assuming user is online
var isLoading = true; // Flag to track if loader animation is currently displayed

function setStatus(online) {
  var statusContainer = document.getElementById('status');
  statusContainer.innerHTML = ''; // Clear previous status
  
  if (online) {
    statusContainer.innerText = 'Online'; // Show online status
  } else {
    statusContainer.innerHTML = '<div class="loader"></div> Offline'; // Show loader animation for offline status
  }
}

// Function to handle user leaving the site
function handleVisibilityChange() {
  if (document.visibilityState === "hidden") {
    isOnline = false;
    setLoading(true);
  } else {
    isOnline = true;
    setLoading(false);
  }
}

// Function to display or hide loader animation
function setLoading(loading) {
  if (loading && isLoading) {
    isLoading = false;
    setStatus(false); // Set status to offline
  } else if (!loading && !isLoading) {
    isLoading = true;
    setTimeout(function() {
      setStatus(isOnline); // Set status to online after 2 seconds
      isLoading = false;
    }, 2000);
  }
}

// Listen for visibility change events
document.addEventListener('visibilitychange', handleVisibilityChange);

// Initial status setup
setStatus(isOnline); // Assuming user is online initially

window.addEventListener('beforeunload', function (e) {
    // Cancel the event
    e.preventDefault();
    // Chrome requires returnValue to be set
    e.returnValue = '';
});

</script>
