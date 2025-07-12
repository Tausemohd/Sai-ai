# Sai-ai
My personal ai saif ai 

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Saif AI</title>
  <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
</head>
<body class="bg-gray-100 text-gray-800">
  <div class="max-w-2xl mx-auto mt-10 p-4 bg-white rounded-xl shadow-lg">
    <h1 class="text-3xl font-bold text-center mb-4">🤖 Saif AI</h1>

    <div id="chatBox" class="h-96 overflow-y-auto border p-4 mb-4 rounded bg-gray-50 text-sm"></div>

    <div class="flex gap-2">
      <input
        id="userInput"
        type="text"
        placeholder="Type something..."
        class="flex-1 border rounded px-3 py-2"
        onkeydown="if(event.key==='Enter') sendMessage()"
      />
      <button onclick="sendMessage()" class="bg-blue-600 text-white px-4 py-2 rounded hover:bg-blue-700">
        Send
      </button>
    </div>
  </div>

  <script>
    const chatBox = document.getElementById('chatBox');
    const userInput = document.getElementById('userInput');

    const addMessage = (sender, text) => {
      const msgDiv = document.createElement('div');
      msgDiv.className = sender === 'You' ? 'text-right my-2' : 'text-left my-2';
      msgDiv.innerHTML = `<strong>${sender}:</strong> ${text}`;
      chatBox.appendChild(msgDiv);
      chatBox.scrollTop = chatBox.scrollHeight;
    }

    const sendMessage = () => {
      const msg = userInput.value.trim();
      if (!msg) return;

      addMessage('You', msg);
      userInput.value = '';

      setTimeout(() => {
        const response = 'Yeh to bas shuruaat hai! 😄';
        addMessage('Saif AI', response);
      }, 1000);
    }

    window.onload = () => {
      addMessage('Saif AI', 'Namaste! Main Saif AI hoon. Aap kya janna chahenge?');
    };
  </script>
</body>
</html>
