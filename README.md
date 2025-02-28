<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Chat Page</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }

        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f0f2f5;
        }

        .chat-container {
            width: 100%;
            max-width: 400px;
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            overflow: hidden;
        }

        .chat-header {
            background-color: #075e54;
            color: #fff;
            padding: 15px;
            text-align: center;
            font-size: 18px;
            font-weight: bold;
        }

        .chat-messages {
            height: 400px;
            overflow-y: auto;
            padding: 15px;
        }

        .message {
            margin-bottom: 10px;
            padding: 8px 12px;
            border-radius: 18px;
            max-width: 70%;
            word-wrap: break-word;
        }

        .message.received {
            background-color: #f1f0f0;
            align-self: flex-start;
        }

        .message.sent {
            background-color: #dcf8c6;
            align-self: flex-end;
            margin-left: auto;
        }

        .chat-input {
            display: flex;
            padding: 10px;
            background-color: #f0f0f0;
        }

        .chat-input input {
            flex-grow: 1;
            padding: 8px 12px;
            border: none;
            border-radius: 20px;
            font-size: 14px;
        }

        .chat-input button {
            background-color: #075e54;
            color: #fff;
            border: none;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            margin-left: 10px;
            cursor: pointer;
            font-size: 18px;
        }
    </style>
</head>
<body>
    <div class="chat-container">
        <div class="chat-header">
            Chat Room
        </div>
        <div class="chat-messages" id="chatMessages">
            <!-- Messages will be added here dynamically -->
        </div>
        <div class="chat-input">
            <input type="text" id="messageInput" placeholder="Type a message...">
            <button onclick="sendMessage()">➤</button>
        </div>
    </div>

    <script>
        const chatMessages = document.getElementById('chatMessages');
        const messageInput = document.getElementById('messageInput');

        function addMessage(message, isSent) {
            const messageElement = document.createElement('div');
            messageElement.classList.add('message');
            messageElement.classList.add(isSent ? 'sent' : 'received');
            messageElement.textContent = message;
            chatMessages.appendChild(messageElement);
            chatMessages.scrollTop = chatMessages.scrollHeight;
        }

        function sendMessage() {
            const message = messageInput.value.trim();
            if (message) {
                addMessage(message, true);
                messageInput.value = '';
                
                // Simulate a received message after a short delay
                setTimeout(() => {
                    addMessage("Thanks for your message!", false);
                }, 1000);
            }
        }

        // Allow sending messages with the Enter key
        messageInput.addEventListener('keypress', function(event) {
            if (event.key === 'Enter') {
                sendMessage();
            }
        });

        // Add some initial messages
        addMessage("Welcome to the chat!", false);
        addMessage("How can I help you today?", false);
    </script>
</body>
</html>
