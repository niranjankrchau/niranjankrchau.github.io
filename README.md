<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Login - Family Tree</title>
<style>
  body { font-family: Arial, sans-serif; max-width: 400px; margin: 50px auto; }
  label, select, input { display: block; margin: 15px 0; width: 100%; padding: 8px; }
  button { padding: 10px; width: 100%; }
</style>
</head>
<body>
  <h2>Login</h2>
  <label for="role">Login as:</label>
  <select id="role">
    <option value="student">Student</option>
    <option value="teacher">Teacher</option>
  </select>

  <label for="username">Name:</label>
  <input type="text" id="username" placeholder="Enter your name" />

  <button onclick="login()">Login</button>

  <script>
    function login() {
      const role = document.getElementById('role').value;
      const username = document.getElementById('username').value.trim();

      if(!username) {
        alert('Please enter your name.');
        return;
      }

      if(role === 'student') {
        // Save student name temporarily, redirect to student page
        localStorage.setItem('currentUser', username);
        window.location.href = 'student.html';
      } else {
        // For teacher, no username check needed (for simplicity)
        localStorage.setItem('currentUser', 'teacher');
        window.location.href = 'teacher.html';
      }
    }
  </script>
</body>
</html>
