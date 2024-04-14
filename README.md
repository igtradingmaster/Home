
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Stock Market Website</title>
  <!-- Chart.js -->
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css" rel="stylesheet">

  <style>
    body {
      background-color: #f2f2f2;
      font-family: Arial, sans-serif;
    }

    .modal {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-color: rgba(0, 0, 0, 0.5);
      display: none;
      justify-content: center;
      align-items: center;
    }

    .modal-content {
      background-color: #ffffff;
      border-radius: 10px;
      padding: 20px;
      box-shadow: 0 0 20px rgba(0, 0, 0, 0.3);
    }

    .modal-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      border-bottom: 1px solid #cccccc;
      padding-bottom: 10px;
      margin-bottom: 10px;
    }

    .modal-header h5 {
      margin: 0;
    }

    .modal-footer {
      display: flex;
      justify-content: flex-end;
      border-top: 1px solid #cccccc;
      padding-top: 10px;
      margin-top: 10px;
    }

    .close {
      cursor: pointer;
    }

    .popup {
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      background-color: #ffffff;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 0 20px rgba(0, 0, 0, 0.3);
    }

    .btn {
      padding: 10px 20px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }

    .btn-primary {
      background-color: rgb(65, 105, 225); /* Royal Blue */
      color: #ffffff;
    }

    .btn-secondary {
      background-color: rgb(255, 69, 0); /* Red Orange */
      color: #ffffff;
    }

    .btn-success {
      background-color: rgb(0, 128, 0); /* Green */
      color: #ffffff;
    }

    .btn-warning {
      background-color: rgb(255, 165, 0); /* Orange */
      color: #ffffff;
    }

    .btn-info {
      background-color: rgb(30, 144, 255); /* Dodger Blue */
      color: #ffffff;
    }

    .btn-danger {
      background-color: rgb(220, 20, 60); /* Crimson */
      color: #ffffff;
    }

    .btn-light {
      background-color: rgb(245, 245, 245); /* Silver */
      color: #000000;
    }

    .btn-dark {
      background-color: rgb(47, 79, 79); /* Dark Slate Gray */
      color: #ffffff;
    }
    /* Additional CSS for styling user details in the user profile modal */
#userDetailsModal {
  max-width: 400px;
  margin: 0 auto;
}

#userDetailsContent {
  padding: 20px;
}

#userDetailsContent p {
  margin: 10px 0;
}

#editForm {
  margin-top: 20px;
}

#editForm label {
  display: block;
  margin-bottom: 5px;
}

#editForm input[type="text"] {
  width: 100%;
  padding: 8px;
  margin-bottom: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

#editForm button {
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

#editForm button[type="submit"] {
  background-color: #007bff; /* Bootstrap Primary Color */
  color: #ffffff;
}

#editForm button[type="submit"]:hover {
  background-color: #0056b3; /* Darker shade of Bootstrap Primary Color */
}

.modal-footer button {
  margin-left: 10px;
}
.input-group {
  margin-bottom: 15px; /* Adjust margin between input groups */
}

.input-group label {
  display: block;
}

.input-group input {
  width: 100%;
  padding: 8px;
  margin-top: 5px; /* Adjust margin between label and input */
}
.custom-notification {
      position: fixed;
      bottom: 50px;
      left: 50%;
      transform: translateX(-50%);
      z-index: 1000;
      width: 300px;
      border-radius: 10px;
      background-color: rgba(0, 0, 0, 0.8);
      color: #ffffff;
      padding: 10px 20px;
      text-align: center;
      box-shadow: 0 2px 5px rgba(0, 0, 0, 0.5);
      opacity: 0;
      transition: opacity 0.5s ease;
    }
    
    .custom-notification.show {
      opacity: 1;
    }
   img{
    width: 90px;
    height: 90px;
   }
  </style>
</head>

<body>
<img id="aiRobot" src="pngtree-future-intelligent-technology-robot-ai-png-image_2588803-removebg-preview.png" AI ROBOT security alt="AI Robot">

<!-- Display AI Status -->
<div id="aiStatus" style="text-align: center;">Stable</div>

<div id="profileLogo" style="position: fixed; top: 10px; right: 10px; cursor: pointer;">
    <img src="https://e7.pngegg.com/pngimages/178/595/png-clipart-user-profile-computer-icons-login-user-avatars-monochrome-black-thumbnail.png" alt="Profile" width="50" height="50" onclick="openUserProfileModal()">
</div>
<!-- Login Modal -->
<div id="loginModal" class="modal">
  <div class="modal-content">
    <div class="modal-header">
      <h5 class="modal-title">Login</h5>
      <button type="button" class="close" onclick="closeLoginModal()">&times;</button>
    </div>
    <div class="modal-body">
      <form id="loginForm" onsubmit="return loginUser()">
        <div class="input-group">
          <label for="mobile">Mobile Number:</label>
          <input type="text" id="mobile" required>
        </div>
        <div class="input-group">
          <label for="name">Name:</label>
          <input type="text" id="name" required>
        </div>
        <div class="input-group">
          <label for="password">Password (8 characters, no digits):</label>
          <input type="password" id="password" pattern="[a-zA-Z]{8}" required>
        </div>
        <button type="submit" class="btn btn-primary">Login</button>
      </form>
    </div>
  </div>
</div>

<!-- User Details Modal -->
<div id="userDetailsModal" class="modal">
  <div class="modal-content">
    <div class="modal-header">
      <h5 class="modal-title">User Details</h5>
      <button type="button" class="close" onclick="closeUserDetailsModal()">&times;</button>
    </div>
    <div class="modal-body" id="userDetailsContent">
      <!-- User details will be displayed here -->
      <p><strong>Name:</strong> <span id="userName"></span></p>
      <p><strong>Mobile Number:</strong> <span id="userMobile"></span></p>
      <div id="editForm" style="display: none;">
        <form id="editUserForm" onsubmit="return saveEditedUserDetails()">
          <div>
            <label for="editName">Name:</label>
            <input type="text" id="editName" value="">
          </div>
          <div>
            <label for="editMobile">Mobile Number:</label>
            <input type="text" id="editMobile" value="">
          </div>
          <button type="submit" class="btn btn-primary">Save</button>
          <ul></ul>
          <div id="barcodeContainer"></div>
        </form>
      </div>
    </div>
    <div class="modal-footer">
      <button type="button" class="btn btn-info" onclick="showEditForm()">Edit</button>
      <!-- Logout Button -->
      <button type="button" class="btn btn-danger" onclick="showLogoutConfirmation()">Logout</button>
    </div>
  </div>
</div>

<!-- Popup -->
<div id="popup" class="popup">
  <p id="popupMessage">Hey Welcome Friends...!!</p>
  <button class="btn btn-secondary" onclick="closePopup()">Close</button>
</div>

<div id="notification" class="custom-notification"></div>

<script>
    // Variable to hold AI status
  let aiStatus = 'stable';

// Update AI status function
function updateAIStatus(newStatus) {
  aiStatus = newStatus;
  document.getElementById('aiStatus').textContent = newStatus.charAt(0).toUpperCase() + newStatus.slice(1);
  updateAIRotation(); // Update AI rotation based on status
}

// Update AI rotation function
function updateAIRotation() {
  const aiRobot = document.getElementById('aiRobot');
  if (aiStatus === 'turningLeft') {
    aiRobot.style.transform = 'rotate(-15deg)';
  } else if (aiStatus === 'turningRight') {
    aiRobot.style.transform = 'rotate(15deg)';
  } else {
    aiRobot.style.transform = 'rotate(0deg)'; // Default rotation (stable)
  }
}

// Function to toggle AI turning direction
function toggleAITurning() {
  if (aiStatus === 'turningLeft') {
    updateAIStatus('turningRight');
  } else {
    updateAIStatus('turningLeft');
  }
}

// Set interval to toggle AI turning direction every second
setInterval(toggleAITurning, 1000);

   // Function to periodically check login status and show notification if not logged in
  function checkLoginStatus() {
    const loggedIn = localStorage.getItem('loggedIn');
    const username = localStorage.getItem('userData') ? JSON.parse(localStorage.getItem('userData')).name : '';
    if (!loggedIn) {
      showNotification(`Hello ${username}, you are not logged in. Please login first.`);
    } else {
      stopNotifications(); // Stop notifications once user is logged in
    }
  }

  // Function to display notification
  function showNotification(message) {
    const notificationDiv = document.getElementById('notification');
    notificationDiv.textContent = message;
    notificationDiv.classList.add('show');

    // Hide notification after 5 seconds
    setTimeout(() => {
      notificationDiv.classList.remove('show');
    }, 5000);
  }

  // Function to stop notifications
  function stopNotifications() {
    clearInterval(notificationInterval);
  }

  // Run the checkLoginStatus function every 2 seconds
  const notificationInterval = setInterval(checkLoginStatus, 2000);
 
  // Variables for user data
  let userData = {};

  // Function to check if user is logged in
  function checkLoggedIn() {
    const loggedIn = localStorage.getItem('loggedIn');
    if (!loggedIn) {
      showLoginPrompt(); // Show login prompt if user is not logged in
    } else {
      loadUserData();
    }
  }

  // Function to show login prompt
  function showLoginPrompt() {
    const body = document.querySelector('body');
    const loginPrompt = document.createElement('div');
    loginPrompt.classList.add('login-prompt');
    loginPrompt.textContent = "";
    body.appendChild(loginPrompt);
    showLoginModal(); // Show login modal when not logged in
  }

  // Function to show login modal
  function showLoginModal() {
    document.getElementById('loginModal').style.display = 'block';
  }

  // Function to populate user details modal
  function populateUserDetailsModal() {
    // Load user data from localStorage
    const savedUserData = JSON.parse(localStorage.getItem('userData'));
    if (savedUserData) {
      userData = savedUserData;
      document.getElementById('userName').textContent = userData.name;
      document.getElementById('userMobile').textContent = userData.mobile;
    }
  }

  // Function to save user data to localStorage
  function saveUserData() {
    localStorage.setItem('userData', JSON.stringify(userData));
  }

  // Function to load user data from localStorage
  function loadUserData() {
    const savedUserData = JSON.parse(localStorage.getItem('userData'));
    if (savedUserData) {
      userData = savedUserData;
      showLoggedInState();
    }
  }

  // Function to show logged-in state
  function showLoggedInState() {
    populateUserDetailsModal();
  }

  // Function to show edit form
  function showEditForm() {
    const editForm = document.getElementById('editForm');
    const userName = document.getElementById('userName');
    const userMobile = document.getElementById('userMobile');
    
    // Hide user details, show edit form
    editForm.style.display = 'block';
    userName.style.display = 'none';
    userMobile.style.display = 'none';
    
    // Populate edit form fields with current user details
    document.getElementById('editName').value = userData.name;
    document.getElementById('editMobile').value = userData.mobile;
  }

  // Function to save edited user details
  function saveEditedUserDetails() {
    const newName = document.getElementById('editName').value;
    const newMobile = document.getElementById('editMobile').value;

    // Update userData with edited details
    userData.name = newName;
    userData.mobile = newMobile;

    // Save updated user data to localStorage
    saveUserData();

    // Update displayed user details
    document.getElementById('userName').textContent = newName;
    document.getElementById('userMobile').textContent = newMobile;

    // Hide edit form, show user details
    document.getElementById('editForm').style.display = 'none';
    document.getElementById('userName').style.display = 'block';
    document.getElementById('userMobile').style.display = 'block';

    // Show success message
    alert('User details updated successfully.');

    return false; // Prevent form submission
  }

  // Open user profile modal and populate user details
  function openUserProfileModal() {
    document.getElementById('userDetailsModal').style.display = 'block';
    populateUserDetailsModal();
  }

  // Login user
  function loginUser() {
    const mobile = document.getElementById('mobile').value;
    const name = document.getElementById('name').value;
    const password = document.getElementById('password').value;
    
    // Saving user data to localStorage
    userData = { mobile, name, password };
    saveUserData();
    localStorage.setItem('loggedIn', true);
    closeLoginModal();
    openUserProfileModal(); // Open user profile modal on successful login
    
    // Change login button to submit with animation
    const loginButton = document.querySelector('#profileLogo img');
    loginButton.setAttribute('src', 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQwNow8bAOVbRGkGx1Ofg9A85ArK_s6yiVx0v9ul2PuLQ&s'); // Change src attribute to submit button image
    loginButton.setAttribute('onclick', ''); // Remove onclick attribute
    loginButton.style.width = '100px'; // Adjust button width for animation
    loginButton.style.transition = 'width 0.5s ease'; // Add transition effect
    loginButton.addEventListener('transitionend', function() {
      loginButton.style.width = '50px'; // Reset button width after animation
      loginButton.setAttribute('src', 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQwNow8bAOVbRGkGx1Ofg9A85ArK_s6yiVx0v9ul2PuLQ&s'); // Change src attribute back to login button image
      loginButton.setAttribute('onclick', 'openUserProfileModal()'); // Restore onclick attribute
    });
    
    // Show success popup
    showPopup('Login Successful!');
    
    return false; // Prevent form submission
  }

  // Show popup
  function showPopup(message) {
    const popup = document.getElementById('popup');
    const popupMessage = document.getElementById('popupMessage');
    popupMessage.textContent = message;
    popup.style.display = 'block';
    setTimeout(function() {
      popup.style.display = 'none';
    }, 3000); // Hide popup after 3 seconds
  }

  // Show confirmation popup for logout
  function showLogoutConfirmation() {
    const confirmLogout = confirm('Are you sure you want to log out?');
    if (confirmLogout) {
      logout();
    }
  }

  // Logout function
  // Logout function
function logout() {
  // Clear user data
  localStorage.removeItem('userData');
  localStorage.removeItem('loggedIn');
  // Show success popup for logout
  showPopup('Your data has been successfully deleted. Please login again.');

  // Wait for the user to close the logout popup, then show the login modal
  const logoutPopup = document.getElementById('popup');
  logoutPopup.addEventListener('transitionend', function() {
    // Automatically show login modal after the logout popup closes
    showLoginModal();
  }, { once: true });
  
  // Restore login button functionality
  const loginButton = document.querySelector('#profileLogo img');
  loginButton.setAttribute('src', 'https://static.vecteezy.com/system/resources/thumbnails/002/318/271/small/user-profile-icon-free-vector.jpg');
  loginButton.setAttribute('onclick', 'openUserProfileModal()');
}


  // Placeholder function for closing login modal
  function closeLoginModal() {
    document.getElementById('loginModal').style.display = 'none';
  }

  // Placeholder function for closing user details modal
  function closeUserDetailsModal() {
    document.getElementById('userDetailsModal').style.display = 'none';
  }

  // Placeholder function for closing popup
  function closePopup() {
    document.getElementById('popup').style.display = 'none';
  }

  // Run functions when the page loads
  window.onload = function() {
    checkLoggedIn();
  };
   // Function to reload the page in the background
   // Function to reload page content
   function refreshBackgroundContent() {
            $.ajax({
                url: 'login2.php', // Replace with your server script to fetch updated content
                cache: false,
                success: function(response){
                    // Update only specific parts of the page
                    $('#contentToUpdate').html(response);
                }
            });
        }

        // Set interval to refresh every second
        setInterval(refreshBackgroundContent, 1000); // 1000 milliseconds = 1 second
</script>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
