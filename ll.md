<!DOCTYPE html>
<html lang="fa">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ذخیره لینک‌های متنی به فایل txt</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f9;
            color: #333;
            text-align: center;
            padding: 20px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            height: 100vh;
        }
        h2 {
            color: #4CAF50;
        }
        input[type="text"] {
            width: 70%;
            padding: 10px;
            margin: 10px 0;
            font-size: 1em;
            border: 1px solid #ccc;
            border-radius: 5px;
            box-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
        }
        button {
            color: white;
            border: none;
            padding: 10px 20px;
            font-size: 1em;
            cursor: pointer;
            border-radius: 5px;
            margin-top: 10px;
            background-color: #2196F3;
            transition: background-color 0.3s ease;
        }
        button:hover {
            background-color: #1976D2;
        }
        #saveButton {
            width: 150px;
            margin: 10px auto;
        }
    </style>
</head>
<body>
    <div>
        <h2>ذخیره لینک‌های متنی به فایل txt</h2>
        
        <!-- پنج ورودی برای لینک‌ها بدون متن راهنما -->
        <input type="text" id="textInput1" placeholder="لینک 1">
        <input type="text" id="textInput2" placeholder="لینک 2">
        <input type="text" id="textInput3" placeholder="لینک 3">
        <input type="text" id="textInput4" placeholder="لینک 4">
        <input type="text" id="textInput5" placeholder="لینک 5">
    </div>

    <div id="saveButton">
        <button onclick="downloadFile()">ذخیره به عنوان فایل txt</button>
    </div>

    <script>
        function downloadFile() {
            // جمع آوری لینک‌ها از ورودی‌ها
            const text1 = document.getElementById('textInput1').value;
            const text2 = document.getElementById('textInput2').value;
            const text3 = document.getElementById('textInput3').value;
            const text4 = document.getElementById('textInput4').value;
            const text5 = document.getElementById('textInput5').value;

            // ساخت متن برای فایل (هر لینک در یک خط)
            const combinedText = `${text1}\n${text2}\n${text3}\n${text4}\n${text5}`;
            
            // پرسیدن نام فایل از کاربر
            const fileName = prompt("لطفاً نام فایل را وارد کنید:", "links.txt");

            // بررسی اینکه آیا کاربر نام فایل را وارد کرده است یا خیر
            if (fileName) {
                const blob = new Blob([combinedText], { type: 'text/plain' });
                const url = URL.createObjectURL(blob);
                const a = document.createElement('a');
                a.href = url;
                a.download = fileName.endsWith('.txt') ? fileName : fileName + '.txt'; // اطمینان از اینکه فایل با پسوند .txt ذخیره شود
                document.body.appendChild(a);
                a.click();
                document.body.removeChild(a);
                URL.revokeObjectURL(url);

                alert('فایل لینک‌های متنی ایجاد شد.');
            } else {
                alert("ذخیره لغو شد. شما نام فایل را وارد نکردید.");
            }
        }
    </script>
</body>
</html>
