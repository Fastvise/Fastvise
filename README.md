<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Регистрация</title>
<style>
  .error {
    color: red;
  }
  .success {
    color: green;
  }

  body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

form {
  width: 600px;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

label {
  display: block;
  margin-bottom: 5px;
}

input,
select {
  width: 100%;
  padding: 5px;
  margin-bottom: 10px;
}

button {
  width: 100%;
  padding: 10px;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background-color: #0056b3;
}

p {
  margin-top: 10px;
}
.error {
  color: red;
}
.success {
  color: green;
}

</style>
</head>
<body>

<form id="registrationForm">
  <label for="username">Имя пользователя:</label>
  <input type="text" id="username" required><br>
  
  <label for="role">Должность:</label>
  <select id="role" required>
    <option value="1">Должность 1</option>
    <option value="2">Должность 2</option>
    <option value="3">Должность 3</option>
  </select><br>
  
  <label for="email">Email:</label>
  <input type="email" id="email" required><br>
  
  <label for="password">Пароль:</label>
  <input type="password" id="password" required><br>
  
  <label for="passwordRepeat">Повторите пароль:</label>
  <input type="password" id="passwordRepeat" required><br>
  
  <input type="checkbox" id="agreement" checked> Согласие на обработку персональных данных<br>
  
  <button type="submit">Отправить</button>
</form>

<p id="errorMessage" class="error" style="display:none"></p>
<p id="successMessage" class="success" style="display:none">Регистрация успешно завершена</p>

<script>
document.getElementById('registrationForm').addEventListener('submit', function(event) {
  event.preventDefault();
  
  const username = document.getElementById('username').value;
  const role = document.getElementById('role').value;
  const email = document.getElementById('email').value;
  const password = document.getElementById('password').value;
  const passwordRepeat = document.getElementById('passwordRepeat').value;
  const agreement = document.getElementById('agreement').checked;
  
  if (!agreement) {
    document.getElementById('errorMessage').innerText = 'Необходимо согласиться на обработку персональных данных';
    document.getElementById('errorMessage').style.display = 'block';
    return;
  }
  
  // Моковый POST запрос
  if (username && role && email && password && passwordRepeat) {
    // Здесь можно добавить логику для отправки данных на сервер
    document.getElementById('registrationForm').style.display = 'none';
    document.getElementById('successMessage').style.display = 'block';
  } else {
    document.getElementById('errorMessage').innerText = 'Необходимо заполнить все поля';
    document.getElementById('errorMessage').style.display = 'block';
  }
});
</script>

</body>
</html>
