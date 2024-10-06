
<html lang="fa">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>تبدیل لینک گوگل درایو به لینک مستقیم</title>
    <script>
        function convertLink() {
            var inputLink = document.getElementById("driveLink").value;
            var fileId = inputLink.match(/[-\w]{25,}/);
            if (fileId) {
                var directLink = "https://drive.google.com/uc?export=download&id=" + fileId[0];
                document.getElementById("directLink").value = directLink;
            } else {
                document.getElementById("directLink").value = "لینک معتبر نیست!";
            }
        }

        function copyToClipboard() {
            var copyText = document.getElementById("directLink");
            copyText.select();
            copyText.setSelectionRange(0, 99999); // برای مرورگرهای موبایل
            document.execCommand("copy");
            alert("لینک کپی شد: " + copyText.value);
        }
    </script>
</head>
<body>
    <h2>تبدیل لینک گوگل درایو به لینک مستقیم</h2>
    <label for="driveLink">لینک اشتراک‌گذاری گوگل درایو را وارد کنید:</label>
    <input type="text" id="driveLink" placeholder="https://drive.google.com/file/d/FILE_ID/view?usp=sharing">
    <button onclick="convertLink()">تبدیل</button>
    <br><br>
    <label for="directLink">لینک مستقیم:</label>
    <input type="text" id="directLink" readonly>
    <button onclick="copyToClipboard()">کپی</button>
</body>
</html>
