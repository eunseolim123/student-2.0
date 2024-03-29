<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login Page</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        form {
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            color: #000; 
        }
        label {
            display: block;
            margin-bottom: 8px;
        }
        input {
            width: 100%;
            padding: 8px;
            margin-bottom: 16px;
            box-sizing: border-box;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
        button {
            background-color: #4caf50;
            color: #fff;
            padding: 10px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        #messageContainer {
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <form id="loginForm">
        <label for="username">Username:</label>
        <input type="text" id="username" name="username" required>
        <label for="password">Password:</label>
        <input type="password" id="password" name="password" required>
        <button type="submit">Login</button>
    </form>
    <div id="messageContainer"></div>
    <form id="signupForm">
        <label for="newUsername">New Username:</label>
        <input type="text" id="newUsername" name="newUsername" required>
        <label for="newPassword">New Password:</label>
        <input type="password" id="newPassword" name="newPassword" required>
        <button type="submit">Sign Up</button>
    </form>
    <script>
        const apiUrl = 'http://127.0.0.1:8086/api/Login/';
        document.getElementById('loginForm').addEventListener('submit', function(event) {
            event.preventDefault();
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;
            // Make an API request for login
            fetch(apiUrl, {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json',
                },
                body: JSON.stringify({ username, password }),
            })
            .then(response => {
                if (!response.ok) {
                    throw new Error('Login failed');
                }
                return response.json();
            })
            .then(data => {
                // Handle successful login
                console.log('Login response:', data);
                showLoginMessage('Login successful', 'green');
                // Redirect to a different page
                window.location.href = 'http://127.0.0.1:4100/student-2.0/';
            })
            .catch(error => {
                // Handle login failure
                console.error('Login error:', error);
                showLoginMessage('Login failed. Incorrect username or password.', 'red');
            });
        });
        function showLoginMessage(message, color) {
            const loginMessage = document.createElement('p');
            loginMessage.textContent = message;
            loginMessage.style.color = color;
            const messageContainer = document.getElementById('messageContainer');
            messageContainer.innerHTML = ''; // Clear previous messages
            messageContainer.appendChild(loginMessage);
        }
    </script>
</body>
</html>