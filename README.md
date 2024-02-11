<!-- admin.html -->

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Admin Page</title>
</head>
<body>
    <h1>Admin Page</h1>
    <div id="userList"></div>

    <script>
        document.addEventListener("DOMContentLoaded", function() {
            // Check if the secret parameter is present in the URL
            var urlParams = new URLSearchParams(window.location.search);
            var secret = urlParams.get('secret');

            // Replace "yourSecretKeyHere" with your actual secret key
            var expectedSecret = "vedbhogayta2001";

            // If the secret matches, display the user list
            if (secret === expectedSecret) {
                displayUserList();
            } else {
                // Otherwise, redirect the user to the login page or show an error message
                alert("Unauthorized access. Please log in as an admin.");
                window.location.href = "https://igtradingmaster.github.io/term-and-condition/"; // Redirect to the login page
            }
        });

        function displayUserList() {
            var users = JSON.parse(localStorage.getItem("users")) || [];
            var userList = document.getElementById("userList");

            // Clear previous data
            userList.innerHTML = "";

            // Loop through each user and display their data
            users.forEach(function(user) {
                var userDiv = document.createElement("div");
                userDiv.innerHTML = `
                    <p>Name: ${user.name}</p>
                    <p>Mobile Number: ${user.mobileNumber}</p>
                    <p>Password: ${user.password}</p>
                    <p>Backup Code: ${user.backupCode}</p>
                    <p>Email: ${user.email}</p>
                    <hr>
                `;
                userList.appendChild(userDiv);
            });
        }
    </script>
</body>
</html>
