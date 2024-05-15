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

   <script defer src="https://openai-widget.web.app/ChatComponent.bundle.js"></script>
<script>
  document.addEventListener('DOMContentLoaded', function() {
    // Check if the chat container exists
    var chatContainer = document.getElementById('chat-container');
    // If the chat container doesn't exist, create it
    if (!chatContainer) {
      chatContainer = document.createElement('div');
      chatContainer.id = 'chat-container';
      document.body.appendChild(chatContainer);
    }
    // Initialize the Chat component
    if (window.ChatComponent) {
      ChatComponent.init('2mcfi6tJjQtthDmjXRUL','#chat-container');
    } else {
      console.error('ChatComponent is not available');
    }
  });
</script>
</body>
</html>
