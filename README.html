<!DOCTYPE html>
<html lang="km">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>ផ្ញើរូបថតទៅ Telegram</title>
  <style>
    * { box-sizing: border-box; }
    body {
      font-family: -apple-system, 'Khmer OS', sans-serif;
      max-width: 500px;
      margin: 30px auto;
      padding: 20px;
      background: #f0f4f8;
      text-align: center;
    }
    h2 { color: #0088cc; margin-bottom: 10px; }
    .consent {
      background: #fff8e1;
      border-left: 4px solid #ffc107;
      padding: 14px;
      border-radius: 8px;
      text-align: left;
      margin-bottom: 20px;
      font-size: 14px;
      line-height: 1.6;
    }
    video {
      width: 100%;
      border-radius: 12px;
      background: #000;
      margin-bottom: 15px;
      transform: scaleX(-1);
    }
    canvas { display: none; }
    button {
      padding: 14px 22px;
      margin: 6px 4px;
      border: none;
      border-radius: 8px;
      background: #0088cc;
      color: white;
      font-size: 16px;
      font-weight: bold;
      cursor: pointer;
      transition: background 0.2s;
    }
    button:hover:not(:disabled) { background: #006699; }
    button:disabled { background: #aaa; cursor: not-allowed; }
    #status {
      margin-top: 18px;
      padding: 12px;
      border-radius: 8px;
      font-weight: bold;
      display: none;
    }
    #status.ok   { background: #c8e6c9; color: #2e7d32; display: block; }
    #status.err  { background: #ffcdd2; color: #c62828; display: block; }
    #status.wait { background: #fff9c4; color: #f57f17; display: block; }
    #preview-photo {
      max-width: 100%;
      border-radius: 12px;
      margin-top: 15px;
      display: none;
    }
  </style>
</head>
<body>

  <h2>📸 ផ្ញើរូបថតទៅ Telegram</h2>

  <div class="consent">
    <strong>⚠️ ការជូនដំណឹង៖</strong><br>
    នៅពេលអ្នកចុច "ថត និងផ្ញើ" រូបថតពីកាមេរ៉ារបស់អ្នក
    នឹងត្រូវផ្ញើទៅម្ចាស់គេហទំព័រតាម Telegram។
    សូមចុចប៊ូតុង ប្រសិនបើអ្នកយល់ព្រម។
  </div>

  <video id="preview" autoplay playsinline muted></video>
  <canvas id="canvas"></canvas>

  <div>
    <button id="startBtn">🎥 បើកកាមេរ៉ា</button>
    <button id="sendBtn" disabled>📤 ថត និងផ្ញើ</button>
  </div>

  <div id="status"></div>
  <img id="preview-photo" alt="រូបថតដែលបានថត">

  <script>
    // ============================================================
    //  ⚙️  កែ ២ បន្ទាត់នេះជារបស់អ្នក
    // ============================================================
    const BOT_TOKEN = '9266815035:AAG--x0KL5bzZF1XG-IquhxatTNjzPWbTZ4';
    const CHAT_ID   = '8671454236';
    // ============================================================

    const video      = document.getElementById('preview');
    const canvas     = document.getElementById('canvas');
    const startBtn   = document.getElementById('startBtn');
    const sendBtn    = document.getElementById('sendBtn');
    const statusEl   = document.getElementById('status');
    const previewImg = document.getElementById('preview-photo');

    let stream = null;

    function showStatus(text, type) {
      statusEl.textContent = text;
      statusEl.className = type;
    }

    // បើកកាមេរ៉ា
    startBtn.onclick = async () => {
      try {
        stream = await navigator.mediaDevices.getUserMedia({
          video: { facingMode: 'user' },
          audio: false
        });
        video.srcObject = stream;
        startBtn.disabled = true;
        sendBtn.disabled = false;
        showStatus('✅ កាមេរ៉ាបើកហើយ។ ចុច "ថត និងផ្ញើ" ដើម្បីបន្ត។', 'ok');
      } catch (err) {
        showStatus('❌ មិនអាចបើកកាមេរ៉ា៖ ' + err.message, 'err');
      }
    };

    // ថត និងផ្ញើ
    sendBtn.onclick = async () => {
      // ពិនិត្យ config
      if (BOT_TOKEN.includes('9266815035:AAG--x0KL5bzZF1XG-IquhxatTNjzPWbTZ4') || CHAT_ID.includes('8671454236')) {
        showStatus('❌ សូមកែ BOT_TOKEN និង CHAT_ID ក្នុងកូដជាមុនសិន!', 'err');
        return;
      }

      sendBtn.disabled = true;
      showStatus('⏳ កំពុងថត និងផ្ញើ...', 'wait');

      // ថតរូប
      canvas.width  = video.videoWidth;
      canvas.height = video.videoHeight;
      const ctx = canvas.getContext('2d');
      ctx.translate(canvas.width, 0);
      ctx.scale(-1, 1); // បញ្ច្រាសដូចកញ្ចក់
      ctx.drawImage(video, 0, 0);

      // បង្ហាញ preview
      previewImg.src = canvas.toDataURL('image/jpeg', 0.9);
      previewImg.style.display = 'block';

      // បម្លែងទៅ Blob ហើយផ្ញើ
      canvas.toBlob(async (blob) => {
        const form = new FormData();
        form.append('chat_id', CHAT_ID);
        form.append('photo', blob, 'photo.jpg');
        form.append('caption', '📸 រូបថតថ្មីពីគេហទំព័រ\n🕐 ' + new Date().toLocaleString('km-KH'));

        try {
          const res = await fetch(
            `https://api.telegram.org/bot${BOT_TOKEN}/sendPhoto`,
            { method: 'POST', body: form }
          );
          const data = await res.json();

          if (data.ok) {
            showStatus('✅ ផ្ញើរូបថតបានជោគជ័យ! សូមពិនិត្យ Telegram។', 'ok');
          } else {
            showStatus('❌ Telegram បដិសេធ៖ ' + (data.description || 'unknown'), 'err');
            console.error('Telegram error:', data);
          }
        } catch (err) {
          showStatus('❌ បញ្ហាបណ្តាញ៖ ' + err.message, 'err');
          console.error(err);
        } finally {
          sendBtn.disabled = false;
        }
      }, 'image/jpeg', 0.9);
    };

    // បិទកាមេរ៉ានៅពេលបិទទំព័រ
    window.addEventListener('beforeunload', () => {
      if (stream) stream.getTracks().forEach(t => t.stop());
    });
  </script>
</body>
</html>
