<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>AI Health Chatbot</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #e6f2ff;
      margin: 0;
      padding: 0;
    }
    .chat-container {
      width: 100%;
      max-width: 500px;
      margin: 50px auto;
      background: #fff;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      overflow: hidden;
    }
    .chat-header {
      background: #007acc;
      color: white;
      padding: 15px;
      text-align: center;
      font-size: 1.2em;
    }
    .chat-box {
      height: 400px;
      overflow-y: auto;
      padding: 15px;
      border-bottom: 1px solid #ccc;
    }
    .chat-message {
      margin-bottom: 15px;
    }
    .bot {
      color: #007acc;
    }
    .user {
      text-align: right;
      color: #333;
    }
    .chat-input {
      display: flex;
    }
    .chat-input input {
      flex: 1;
      padding: 10px;
      border: none;
      border-top: 1px solid #ccc;
      font-size: 1em;
    }
    .chat-input button {
      padding: 10px 15px;
      background: #007acc;
      color: white;
      border: none;
      cursor: pointer;
    }
  </style>
</head>
<body>

<div class="chat-container">
  <div class="chat-header">AI Health Chatbot</div>
  <div class="chat-box" id="chatBox"></div>
  <div class="chat-input">
    <input type="text" id="userInput" placeholder="Ask a health question..." />
    <button onclick="sendMessage()">Send</button>
  </div>
</div>

<script>
  function sendMessage() {
    const input = document.getElementById('userInput');
    const chatBox = document.getElementById('chatBox');
    const userText = input.value.trim();
    if (!userText) return;

    // Show user message
    chatBox.innerHTML += `<div class="chat-message user"><strong>You:</strong> ${userText}</div>`;

    // Simulate bot response
    const botResponse = getBotResponse(userText);
    chatBox.innerHTML += `<div class="chat-message bot"><strong>Bot:</strong> ${botResponse}</div>`;

    input.value = '';
    chatBox.scrollTop = chatBox.scrollHeight;
  }

  function getBotResponse(message) {
    // Basic responses (you can integrate AI API here)
    message = message.toLowerCase();
    if (message.includes("fever")) return "It’s important to stay hydrated and rest. Consider seeing a doctor if it persists.";
    if (message.includes("headache")) return "Try to relax in a quiet, dark room. Drink water and take a break from screens.";
    if (message.includes("covid")) return "For COVID symptoms, isolate and consider testing. Contact a medical professional.";
    return "I'm here to help with health questions! Can you provide more details?";
  }
</script>

</body>
</html>
