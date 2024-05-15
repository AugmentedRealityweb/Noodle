<html lang="ro">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Chatbot</title>
    <style>
        #chatbox {
            width: 300px;
            height: 400px;
            border: 1px solid #ccc;
            padding: 10px;
            overflow-y: scroll;
        }
        #userInput {
            width: 100%;
            padding: 10px;
        }
    </style>
</head>
<body>
    <div id="chatbox"></div>
    <input type="text" id="userInput" placeholder="Type your message here..." />
    <button onclick="sendMessage()">Send</button>

    <script>
        async function sendMessage() {
            const userInput = document.getElementById('userInput').value;
            const response = await fetch('https://7a33e74f-aec9-4287-b712-b754d5384964-00-2qz0sbny3vwzg.kirk.replit.dev/webhook', {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify({ message: userInput })
            });
            const data = await response.json();
            document.getElementById('chatbox').innerHTML += `<p><strong>You:</strong> ${userInput}</p>`;
            document.getElementById('chatbox').innerHTML += `<p><strong>Bot:</strong> ${data.response}</p>`;
            document.getElementById('userInput').value = '';
        }
    </script>
</body>
</html>
