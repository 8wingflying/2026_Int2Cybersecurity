# PHP
## example: FORM ===> Welcome.php

#### form.html
```html
<!DOCTYPE html>
<html>
<body>
<h1>My Form:A888168</h1>

<form action="welcome.php" method="POST">    
Username：<input type="text" name="username">    
Email：<input type="email" name="email">    
<button type="submit">Submit</button>
</form>

</body>
</html>
```
- `<form action="welcome.php" method="POST"> `  
#### welcome.php
```php
<?php
// 檢查是否有資料傳入
if ( $_SERVER["REQUEST_METHOD"] == "POST") {
// if ( $_SERVER["REQUEST_METHOD"] == "GET") {
// 獲取資料    
$name = $_POST['username'];    
$email = $_POST['email'];    
echo "How Are YOU?  " . htmlspecialchars($name) . "！YOUR Email is " . htmlspecialchars($email);}
?>
```
