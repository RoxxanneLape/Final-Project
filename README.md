<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Palindrome Checker</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 50px;
        }
        input {
            padding: 10px;
            font-size: 16px;
        }
        button {
            padding: 10px 15px;
            font-size: 16px;
            cursor: pointer;
        }
        #result {
            margin-top: 20px;
            font-size: 18px;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <h1>Palindrome Checker</h1>
    <input type="text" id="text-input" placeholder="Enter text here">
    <button id="check-btn">Check</button>
    <p id="result"></p>

    <script>
        document.getElementById("check-btn").addEventListener("click", function() {
            const inputElement = document.getElementById("text-input");
            const resultElement = document.getElementById("result");
            const text = inputElement.value.trim();
            
            if (text === "") {
                alert("Please input a value.");
                return;
            }
            
            const cleanText = text.toLowerCase().replace(/[^a-z0-9]/g, "");
            const reversedText = cleanText.split("").reverse().join("");
            
            if (cleanText === reversedText) {
                resultElement.textContent = `${text} is a palindrome.`;
            } else {
                resultElement.textContent = `${text} is not a palindrome.`;
            }
        });
    </script>
</body>
</html>
