## HTML範例學習
- [HTML Examples](https://www.w3schools.com/html/html_examples.asp)
- https://www.w3schools.com/html/default.asp

## HTML範例1:
```HTML
<!DOCTYPE html>
<html>
<head>
  <title>A Meaningful Page Title</title>
</head>
<body>

<p>The content of the body element is displayed in the browser window.</p>
<p>The content of the title element is displayed in the browser tab, in favorites and in search-engine results.</p>

</body>
</html>
```

## HTML範例2:正確顯示中文
```HTML
<!DOCTYPE html>
<html > 
<head>
    <meta charset="UTF-8"> <title>我的中文網頁標題</title>
</head>
<body>

<p>The content of the body element is displayed in the browser window.</p>
<p>The content of the title element is displayed in the browser tab, in favorites and in search-engine results.</p>

</body>
</html>
```
## HTML範例3:<html> 標籤常用的屬性分類
- head標籤常用的屬性
- body標籤常用的屬性
```html
<!DOCTYPE html>
<html lang="zh-Hant" dir="ltr" class="light-mode">
<head>
    <meta charset="UTF-8">
    <title>標題</title>
</head>
...
</html>
```

## HTML範例4:表單
```html
<!DOCTYPE html>
<html lang="zh-Hant">
<head>
    <meta charset="UTF-8">
    <title>會員註冊 - 範例</title>
    <style>
        /* 簡單的排版讓表單更美觀 */
        body { font-family: sans-serif; padding: 20px; line-height: 1.6; }
        .form-group { margin-bottom: 15px; }
        label { display: block; margin-bottom: 5px; font-weight: bold; }
        input[type="text"], input[type="email"], input[type="password"], input[type="date"] {
            width: 100%; padding: 8px; box-sizing: border-box;
        }
        button { padding: 10px 20px; background: #007bff; color: white; border: none; cursor: pointer; }
        button:hover { background: #0056b3; }
    </style>
</head>
<body>

    <h2>加入會員</h2>
    <p>請填寫以下資訊完成註冊</p>

    <form action="/submit-registration" method="POST">
        
        <div class="form-group">
            <label for="username">使用者帳號</label>
            <input type="text" id="username" name="username" required placeholder="請輸入 6-12 位英數字">
        </div>

        <div class="form-group">
            <label for="email">電子郵件 (Email)</label>
            <input type="email" id="email" name="email" required placeholder="example@mail.com">
        </div>

        <div class="form-group">
            <label for="password">設定密碼</label>
            <input type="password" id="password" name="password" required minlength="8">
        </div>

        <div class="form-group">
            <label for="birthday">生日</label>
            <input type="date" id="birthday" name="birthday">
        </div>

        <div class="form-group">
            <label>性別</label>
            <input type="radio" id="male" name="gender" value="male">
            <label for="male" style="display:inline;">男</label>
            <input type="radio" id="female" name="gender" value="female">
            <label for="female" style="display:inline;">女</label>
        </div>

        <div class="form-group">
            <input type="checkbox" id="terms" name="terms" required>
            <label for="terms" style="display:inline;">我已閱讀並同意服務條款</label>
        </div>

        <button type="submit">立即註冊</button>

    </form>

</body>
</html>
```
## HTML範例 5:超連結 <a> anchor element
```html
<!DOCTYPE html>
<html>
<body>

<h1>HTML Links</h1>

<p>
<a href="https://www.w3schools.com/">Visit W3Schools.com!</a>
</p>

</body>
</html>
```
## HTML範例 5:iframe
- https://www.w3schools.com/html/tryit.asp?filename=tryhtml_youtubeiframe
```HTML
<!DOCTYPE html>
<html>
<body>

<iframe width="420" height="345" src="https://www.youtube.com/embed/tgbNymZ7vqY">
</iframe>

</body>
</html>
```

## HTML範例4:多媒體
```HTML
<!DOCTYPE html>
<html lang="zh-Hant">
<head>
    <meta charset="UTF-8">
    <title>我的 HTML 練習網頁</title>
    <style>
        body { font-family: sans-serif; line-height: 1.6; padding: 20px; }
        .container { border: 1px solid #ccc; padding: 15px; }
        span { color: red; font-weight: bold; }
    </style>
</head>
<body>

    <div class="container">
        <h1>歡迎來到我的網站</h1>
        <p>這是一個展示常用 <span>HTML 標籤</span> 的範例頁面。</p>
        
        <hr>

        <h3>多媒體示範</h3>
        <p>點擊這裡前往 <a href="https://www.google.com" target="_blank">Google</a>。</p>
        <img src="https://via.placeholder.com/150" alt="範例圖片">
        
        <br>

        <h3>學習清單</h3>
        <ul>
            <li>HTML 基礎</li>
            <li>CSS 樣式</li>
            <li>JavaScript 互動</li>
        </ul>

        <ol>
            <li>步驟一：撰寫程式碼</li>
            <li>步驟二：儲存檔案</li>
        </ol>

        <h3>數據表格</h3>
        <table border="1">
            <tr>
                <th>項目</th>
                <th>價格</th>
            </tr>
            <tr>
                <td>咖啡</td>
                <td>$50</td>
            </tr>
        </table>

        <h3>聯絡我們</h3>
        <form action="#">
            <label for="name">姓名：</label>
            <input type="text" id="name" name="name" placeholder="請輸入姓名">
            <br><br>
            <button type="submit">送出表單</button>
        </form>
    </div>

</body>
</html>
```

## HTML範例: 利用 CSS 來美化這個網頁
- CSS 的核心概念是 「選擇器」（選擇要裝飾的 HTML 標籤）與 「屬性」（決定要改變什麼，例如顏色、邊距）。
- 美化後的 HTML + CSS 完整代碼
  - 直接將原本的 <style> 區塊替換成以下內容，或者將整個檔案覆蓋：
```HTML
<!DOCTYPE html>
<html lang="zh-Hant">
<head>
    <meta charset="UTF-8">
    <title>現代化網頁範例</title>
    <style>
        /* 1. 全域重設：讓不同瀏覽器顯示一致 */
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Segoe UI', Microsoft JhengHei, sans-serif;
            background-color: #f4f7f6; /* 淺灰色背景 */
            color: #333;
            line-height: 1.8;
            padding: 40px 20px;
        }

        /* 2. 容器設計：讓內容集中且有陰影質感 */
        .container {
            max-width: 800px;
            margin: 0 auto;
            background: #ffffff;
            padding: 40px;
            border-radius: 12px; /* 圓角 */
            box-shadow: 0 4px 15px rgba(0,0,0,0.1); /* 柔和陰影 */
        }

        /* 3. 標題與裝飾 */
        h1 {
            color: #2c3e50;
            border-bottom: 3px solid #3498db;
            padding-bottom: 10px;
            margin-bottom: 20px;
        }

        h3 {
            margin: 25px 0 15px;
            color: #34495e;
        }

        span {
            background: #ffeaa7;
            padding: 2px 5px;
            border-radius: 4px;
            color: #d63031;
        }

        /* 4. 列表與表格美化 */
        ul, ol {
            margin-left: 20px;
            margin-bottom: 20px;
        }

        table {
            width: 100%;
            border-collapse: collapse; /* 合併邊框 */
            margin: 15px 0;
        }

        th, td {
            padding: 12px;
            text-align: left;
            border-bottom: 1px solid #ddd;
        }

        th {
            background-color: #3498db;
            color: white;
        }

        /* 5. 表單美化：讓輸入框與按鈕更有質感 */
        input[type="text"] {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 6px;
        }

        button {
            background-color: #2ecc71;
            color: white;
            padding: 10px 25px;
            border: none;
            border-radius: 6px;
            cursor: pointer;
            font-size: 16px;
            transition: background 0.3s; /* 動畫過渡 */
        }

        button:hover {
            background-color: #27ae60; /* 滑鼠懸停顏色變深 */
        }

        /* 圖片自適應 */
        img {
            max-width: 100%;
            height: auto;
            border-radius: 8px;
        }
    </style>
</head>
<body>

    <div class="container">
        <h1>我的現代化網頁</h1>
        <p>這是一個經過 <span>CSS 美化</span> 後的範例頁面，看起來舒服多了吧？</p>
        
        <hr style="margin: 20px 0; border: 0; border-top: 1px solid #eee;">

        <h3>多媒體示範</h3>
        <p>歡迎造訪我的 <a href="#" style="color: #3498db; text-decoration: none;">範例連結</a>。</p>
        <img src="https://images.unsplash.com/photo-1498050108023-c5249f4df085?auto=format&fit=crop&w=600&q=80" alt="程式開發圖片">
        
        <h3>學習進度</h3>
        <ul>
            <li>HTML 標籤結構</li>
            <li>CSS 樣式美化</li>
            <li>RWD 響應式設計</li>
        </ul>

        <h3>數據清單</h3>
        <table>
            <thead>
                <tr>
                    <th>課程名稱</th>
                    <th>難易度</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>HTML 基礎</td>
                    <td>★☆☆☆☆</td>
                </tr>
                <tr>
                    <td>CSS 進階排版</td>
                    <td>★★★☆☆</td>
                </tr>
            </tbody>
        </table>

        <h3>立即聯絡</h3>
        <form>
            <label for="name">您的姓名：</label>
            <input type="text" id="name" placeholder="請輸入大名...">
            <button type="submit">點我送出</button>
        </form>
    </div>

</body>
</html>
```
