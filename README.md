<!DOCTYPE html>
<html>
<head>
    <title>与机器人聊天</title>
</head>
<body>
    <div id="chat-container">
        <div id="messages"></div>
        <input type="text" id="message-input" placeholder="输入消息...">
        <button onclick="sendMessage()">发送</button>
    </div>
    
    <script>
    async function sendMessage() {
        const message = document.getElementById('message-input').value;
        const response = await fetch('https://your-worker.workers.dev/chat', {
            method: 'POST',
            headers: {'Content-Type': 'application/json'},
            body: JSON.stringify({message: message})
        });
        const result = await response.json();
        // 显示机器人回复
    }
    </script>
</body>
</html>
