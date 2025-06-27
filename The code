// Install mineflayer in Replit or terminal:
// npm install mineflayer

const mineflayer = require('mineflayer');

function createBot() {
  const bot = mineflayer.createBot({
    host: 'yourserver.aternos.me', // 🔁 Replace with your Aternos IP
    port: 25565,
    username: 'YourBotName',       // 🧑 Any name (no login needed)
    auth: 'offline',               // ✅ For cracked servers
    version: '1.21.1',             // 🧩 Match your server version
  });

  bot.on('spawn', () => {
    console.log('✅ Bot joined the server!');

    // 💡 Prevent AFK kick — move every 15 sec
    setInterval(() => {
      const forward = true;
      bot.setControlState('forward', forward);
      setTimeout(() => bot.setControlState('forward', false), 2000); // move for 2 sec
    }, 15000); // every 15 sec

    // Optional: jump every 30 sec
    setInterval(() => {
      bot.setControlState('jump', true);
      setTimeout(() => bot.setControlState('jump', false), 500);
    }, 30000);
  });

  bot.on('end', () => {
    console.log('⚠️ Bot disconnected. Reconnecting in 10s...');
    setTimeout(createBot, 10000);
  });

  bot.on('error', err => {
    console.log('❌ Error: ', err);
  });
}

createBot();
