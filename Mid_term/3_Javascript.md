##

```javascript
<!DOCTYPE html>
<html>
<body>
<h1>My First JavaScript</h1>

<button type="button" onclick="document.getElementById('demo').innerHTML = Date()">
Click me to display Date and Time.</button>

<p id="demo"></p>

</body>
</html> 
```
- HTML Document Object Model(DOM)
  - https://www.w3schools.com/js/js_htmldom_methods.asp 
- HTML DOM API
- https://www.w3schools.com/js/js_htmldom_methods.asp
```javascript

```

#### 使用javascript 顯示fib 序列 由web介面輸入 n值 在網頁輸出結果
- 這是一個實作 Fibonacci (費波那契) 數列 的完整網頁範例。我將使用 HTML 提供輸入介面，並用 JavaScript 處理計算邏輯。
- 為了讓網頁更具互動性，我會同時包含一個輸入框、一個執行按鈕，以及一個清楚顯示結果的區域。
```javascript
<!DOCTYPE html>
<html lang="zh-Hant">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fibonacci 序列產生器</title>
    <style>
        body { font-family: sans-serif; margin: 40px; line-height: 1.6; }
        .container { max-width: 500px; border: 1px solid #ddd; padding: 20px; border-radius: 8px; }
        input { padding: 8px; width: 100px; }
        button { padding: 8px 15px; cursor: pointer; background-color: #007bff; color: white; border: none; border-radius: 4px; }
        button:hover { background-color: #0056b3; }
        #result { margin-top: 20px; word-wrap: break-word; background: #f8f9fa; padding: 10px; border-radius: 4px; }
    </style>
</head>
<body>

<div class="container">
    <h2>Fibonacci 序列產生器</h2>
    <p>請輸入要顯示的項數 (n):</p>
    <input type="number" id="inputN" min="1" value="10">
    <button onclick="displayFib()">產生序列</button>

    <div id="result">
        <strong>結果：</strong> <span id="output">等待輸入...</span>
    </div>
</div>

<script>
    function generateFibonacci(n) {
        if (n <= 0) return [];
        if (n === 1) return [0];
        
        let fib = [0, 1];
        for (let i = 2; i < n; i++) {
            // 下一個數等於前兩個數之和
            fib[i] = fib[i - 1] + fib[i - 2];
        }
        return fib;
    }

    function displayFib() {
        const n = parseInt(document.getElementById('inputN').value);
        const outputElement = document.getElementById('output');

        if (isNaN(n) || n <= 0) {
            outputElement.innerHTML = "<span style='color:red;'>請輸入大於 0 的有效數字。</span>";
            return;
        }

        const sequence = generateFibonacci(n);
        outputElement.innerText = sequence.join(', ');
    }
</script>

</body>
</html>
```
#### Changing HTML Style

```javascript
<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <title>JS 功能整合範例</title>
    <style>body { font-family: sans-serif; padding: 20px; transition: 0.3s; }</style>
</head>
<body>
    <h2>1. 顯示時間</h2>
    <button onclick="showTime()">顯示時間</button> <span id="time"></span>

    <h2>2. 計算 Fibonacci (前10個)</h2>
    <button onclick="calcFib()">點我計算並看控制台(Console)</button>
    <p id="fib-result"></p>

    <h2>3. 更換背景顏色</h2>
    <button onclick="changeBg()">隨機換色</button>

    <h2>4. (不安全) 表單驗證</h2>
    <input type="text" id="user" placeholder="請輸入姓名">
    <button onclick="validate()">提交</button>

    <script>
        // 1. 顯示時間
        function showTime() {
            document.getElementById('time').innerText = new Date().toLocaleTimeString();
        }
        // 2. Fibonacci 遞迴計算
        function fib(n) { return n <= 1 ? n : fib(n-1) + fib(n-2); }
        function calcFib() {
            let res = "";
            for(let i=0; i<10; i++) res += fib(i) + " ";
            document.getElementById('fib-result').innerText = "結果: " + res;
            console.log("Fibonacci:", res);
        }
        // 3. 更換背景
        function changeBg() {
            const color = '#' + Math.floor(Math.random()*16777215).toString(16);
          // 藏青色 ==> #000080
            document.body.style.backgroundColor = color;
        }
        // 4. 不安全驗證 (僅前端檢查)
        function validate() {
            const val = document.getElementById('user').value;
            alert(val === "" ? "錯誤：欄位不能為空！" : "驗證通過！(但後端仍需檢查)");
        }
    </script>
</body>
</html>
```


```javascript

```
