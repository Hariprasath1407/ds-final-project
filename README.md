<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Stack Implementation</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            padding: 20px;
        }
        input, button {
            margin: 5px 0;
            padding: 5px 10px;
        }
        #stackDisplay {
            margin-top: 20px;
            padding: 10px;
            border: 1px solid #333;
            min-height: 50px;
        }
    </style>
</head>
<body>
    <h2>Stack Implementation </h2>

    <input type="number" id="value" placeholder="Enter value">
    <button onclick="push()">Push</button>
    <button onclick="pop()">Pop</button>
    <button onclick="peek()">Peek</button>
        <div id="stackDisplay">Stack is empty</div>
        <script>
        let stack = [];
        const maxSize = 5; // stack size limit
        function updateDisplay(message) {
        const display = document.getElementById("stackDisplay");
        display.innerHTML = message + "<br>Stack: [" + stack.join(", ") + "]";
        }
        function push() {
            const value = document.getElementById("value").value;
            if (stack.length >= maxSize) {
                alert("Stack Overflow!");
                return;
            }
            if (value === "") {
                alert("Enter a value to push!");
                return;
            }
            stack.push(Number(value));
            updateDisplay("Pushed " + value);
            document.getElementById("value").value = "";
        }
        function pop() {
            if (stack.length === 0) {
                alert("Stack Underflow!");
                return;
            }
            const popped = stack.pop();
            updateDisplay("Popped " + popped);
        }
        function peek() {
            if (stack.length === 0) {
                alert("Stack is empty!");
                return;
            }
            alert("Top element is " + stack[stack.length - 1]);
        }
        updateDisplay("Stack is empty");
    </script>
</body>
</html>
