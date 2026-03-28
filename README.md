
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>MAD MUSCLE MENU</title>
<link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;500;600;700&display=swap" rel="stylesheet"/>
<style>
:root {
  --wa-green: #25D366;
  --wa-teal: #128C7E;
  --wa-bg: #ECE5DD;
  --bubble-bot: #ffffff;
  --bubble-user: #DCF8C6;
  --text-main: #111b21;
  --text-secondary: #667781;
  --border: #e0e0e0;
  --shadow: 0 1px 2px rgba(0,0,0,0.13);
}
* { box-sizing: border-box; margin: 0; padding: 0; }
body {
  font-family: 'Nunito', sans-serif;
  background: #111b21;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
}
.phone-frame {
  width: 390px;
  height: 780px;
  background: var(--wa-bg);
  border-radius: 32px;
  overflow: hidden;
  display: flex;
  flex-direction: column;
  box-shadow: 0 30px 80px rgba(0,0,0,0.6);
}
.chat-header {
  background: var(--wa-teal);
  padding: 12px 16px;
  display: flex;
  align-items: center;
  gap: 12px;
  box-shadow: 0 2px 6px rgba(0,0,0,0.2);
}
.header-avatar {
  width: 40px; height: 40px;
  border-radius: 50%;
  overflow: hidden;
  flex-shrink: 0;
}
.header-avatar img {
  width: 100%; height: 100%;
  object-fit: cover;
}
.header-info { flex: 1; }
.header-name { color: #fff; font-size: 16px; font-weight: 700; }
.header-status { color: rgba(255,255,255,0.75); font-size: 12px; }
.header-dots { color: rgba(255,255,255,0.8); font-size: 22px; cursor: pointer; letter-spacing: 2px; }
.chat-area {
  flex: 1;
  overflow-y: auto;
  padding: 12px 10px 6px;
  background: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23c8bdb0' fill-opacity='0.25'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E"), var(--wa-bg);
  scroll-behavior: smooth;
}
.date-divider { text-align: center; margin: 10px 0; }
.date-divider span {
  background: rgba(255,255,255,0.75);
  color: var(--text-secondary);
  font-size: 11.5px;
  padding: 4px 10px;
  border-radius: 8px;
}
.msg-row { display: flex; margin-bottom: 4px; animation: popIn 0.22s cubic-bezier(.34,1.56,.64,1); }
@keyframes popIn { from { opacity: 0; transform: scale(0.88) translateY(6px); } to { opacity: 1; transform: scale(1) translateY(0); } }
.msg-row.bot { justify-content: flex-start; }
.msg-row.user { justify-content: flex-end; }
.bubble {
  max-width: 78%;
  padding: 8px 12px 6px;
  border-radius: 10px;
  font-size: 14.5px;
  line-height: 1.45;
  box-shadow: var(--shadow);
}
.msg-row.bot .bubble { background: var(--bubble-bot); border-top-left-radius: 2px; }
.msg-row.user .bubble { background: var(--bubble-user); border-top-right-radius: 2px; }
.bubble-time { font-size: 10.5px; color: var(--text-secondary); text-align: right; margin-top: 3px; }
.input-bar {
  background: var(--wa-bg);
  padding: 8px 10px;
  display: flex;
  align-items: center;
  gap: 8px;
}
.input-wrap {
  flex: 1;
  background: #fff;
  border-radius: 24px;
  display: flex;
  align-items: center;
  padding: 8px 14px;
  gap: 8px;
}
.chat-input {
  flex: 1;
  border: none;
  outline: none;
  font-size: 14.5px;
  background: transparent;
}
.send-btn {
  width: 44px; height: 44px;
  border-radius: 50%;
  background: var(--wa-green);
  border: none;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
}
.modal-overlay {
  position: absolute;
  inset: 0;
  background: rgba(0,0,0,0.45);
  z-index: 100;
  display: flex;
  align-items: flex-end;
}
.modal-sheet {
  width: 100%;
  background: #fff;
  border-radius: 20px 20px 0 0;
  max-height: 82%;
  display: flex;
  flex-direction: column;
}
.modal-header {
  padding: 18px 18px 12px;
  border-bottom: 1px solid #eee;
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
}
.modal-title { font-size: 16px; font-weight: 700; color: #111b21; }
.modal-body { overflow-y: auto; flex: 1; padding: 10px 0; }
</style>
</head>
<body>

<div class="phone-frame">
  <div class="chat-header">
    <div class="header-avatar">
      <img src="https://share.icloud.com/photos/0a2FUAO2flNnUxmVUHeTgoZrA" alt="UK MUSCLE" />
    </div>
    <div class="header-info">
      <div class="header-name">🇬🇧MAD MUSCLE MENU🇮🇪</div>
      <div class="header-status">online</div>
    </div>
    <div class="header-dots">⋮</div>
  </div>

  <div class="chat-area" id="chatArea">
    <div class="date-divider"><span>Today</span></div>
  </div>

  <div class="input-bar">
    <div class="input-wrap">
      <span class="emoji-btn">😊</span>
      <textarea class="chat-input" id="chatInput" placeholder="Type a message" rows="1" onInput="autoResize(this)" onKeydown="handleKey(event)"></textarea>
      <span class="attach-btn">📎</span>
    </div>
    <button class="send-btn" onclick="sendUserMessage()">
      <svg viewBox="0 0 24 24"><path d="M2.01 21L23 12 2.01 3 2 10l15 2-15 2z"/></svg>
    </button>
  </div>
</div>

<div class="modal-overlay" id="modalOverlay" style="display:none" onclick="if(event.target===this)closeModal()">
  <div class="modal-sheet">
    <div class="modal-header">
      <div class="modal-title" id="modalTitle">UK Muscle Shop</div>
      <button onclick="closeModal()" style="background:none;border:none;font-size:24px;cursor:pointer;">✕</button>
    </div>
    <div class="modal-body" id="modalBody"></div>
  </div>
</div>

<script>
  const chatArea = document.getElementById('chatArea');
  let cart = [];

  const now = () => {
    const d = new Date();
    return d.getHours().toString().padStart(2,'0') + ':' + d.getMinutes().toString().padStart(2,'0');
  };

  function addBotBubble(text, delay = 600) {
    return new Promise(resolve => {
      const typing = document.createElement('div');
      typing.className = 'msg-row bot';
      typing.innerHTML = `<div class="bubble"><div class="typing"><span></span><span></span><span></span></div></div>`;
      chatArea.appendChild(typing);
      setTimeout(() => {
        typing.remove();
        const row = document.createElement('div');
        row.className = 'msg-row bot';
        row.innerHTML = `<div class="bubble">${text.replace(/\n/g,'<br>')}<div class="bubble-time">${now()}</div></div>`;
        chatArea.appendChild(row);
        chatArea.scrollTop = chatArea.scrollHeight;
        resolve();
      }, delay);
    });
  }

  function addListCard() {
    const row = document.createElement('div');
    row.className = 'msg-row bot';
    row.innerHTML = `
      <div class="bubble" style="padding:0;max-width:78%;">
        <div style="padding:12px 14px 8px;">
          <div style="font-weight:700;font-size:15px;">🛒 UK Muscle Shop</div>
          <div style="font-size:13.5px;color:#667781;margin-top:4px;">Browse our full range</div>
        </div>
        <button onclick="openMainMenu()" style="width:100%;border:none;background:none;color:#128C7E;font-weight:700;padding:12px 0;cursor:pointer;">View Products</button>
      </div>`;
    chatArea.appendChild(row);
    chatArea.scrollTop = chatArea.scrollHeight;
  }

  function openMainMenu() {
    const body = document.getElementById('modalBody');
    body.innerHTML = `
      <div style="padding:10px 18px;font-size:15px;">
        <div onclick="showCategory('injectables')" style="padding:14px 0;border-bottom:1px solid #eee;cursor:pointer;">💉 INJECTABLE ANABOLICS</div>
        <div onclick="showCategory('orals')" style="padding:14px 0;border-bottom:1px solid #eee;cursor:pointer;">💊 ORAL ANABOLICS</div>
        <div onclick="showCategory('peptides')" style="padding:14px 0;border-bottom:1px solid #eee;cursor:pointer;">🧬 PEPTIDES & GROWTH</div>
        <div onclick="showCategory('pct')" style="padding:14px 0;border-bottom:1px solid #eee;cursor:pointer;">🛡️ PCT & FAT BURNERS</div>
        <div onclick="showCategory('benzos')" style="padding:14px 0;border-bottom:1px solid #eee;cursor:pointer;">🌿 BENZOS & CHILL</div>
        <div onclick="showCategory('pain')" style="padding:14px 0;border-bottom:1px solid #eee;cursor:pointer;">💊 PAIN & OPIATES</div>
        <div onclick="showCategory('sleepsex')" style="padding:14px 0;border-bottom:1px solid #eee;cursor:pointer;">😴 SLEEP & SEX</div>
        <div onclick="showCategory('others')" style="padding:14px 0;cursor:pointer;">🧪 OTHERS</div>
      </div>`;
    document.getElementById('modalOverlay').style.display = 'flex';
  }

  function showCategory(cat) {
    const products = {
      injectables: [{name:"Test Prop 100",price:25},{name:"Test Cyp 250",price:30},{name:"Sus 250",price:30},{name:"Test E 250",price:30},{name:"Test 400",price:35},{name:"Eq 350",price:30},{name:"Mast P 100",price:30},{name:"Tren A 100",price:30},{name:"Tren E 200",price:35},{name:"NPP 100",price:30},{name:"Deca 250",price:30},{name:"Primo 100",price:45}],
      orals: [{name:"Dianabol 100x10mg",price:25},{name:"Winstrol 50x20mg",price:25},{name:"Winstrol 50x50mg",price:35},{name:"Anavar 100x10mg",price:30},{name:"Anavar 50x20mg",price:30},{name:"Anadrol 100x50mg",price:40}],
      peptides: [{name:"Viogen HGH 100iu",price:120},{name:"SLU-PP-332 60x500mcg",price:60},{name:"BPC/TB500 40MG PEN",price:90},{name:"GHK GLOW 70MG PEN",price:90},{name:"IGF-1 LR3 1mg",price:35},{name:"Ipamorelin",price:12},{name:"CJC-1295 5mg",price:20},{name:"NAD+ 500mg",price:40},{name:"Mots-c",price:20},{name:"Water for injection",price:1}],
      pct: [{name:"Arimidex 50x1mg",price:35},{name:"Clomid 30x50mg",price:20},{name:"HCG 10,000iu",price:35},{name:"HMG 150iu",price:25},{name:"T3 50x25mcg",price:20},{name:"Clen 100x40mcg",price:30},{name:"Thermo lipid 50ml",price:35},{name:"Ozempic pen 10mg",price:85},{name:"Mounjaro pen 50mg",price:120},{name:"Retatrutide 30mg",price:120}],
      benzos: [{name:"Bensedin Diazepam 30x10mg",price:25},{name:"Martin Dow Diazepam 30x10mg",price:25},{name:"Pharma Diazepam 100x5mg",price:50},{name:"EU Lorazepam 20x2.5mg",price:25},{name:"UK Clonazepam 50x2mg",price:60},{name:"Replek Alprazolam 30x1mg",price:30},{name:"Alprazolam 75x1mg",price:50},{name:"UK Nitrazepam 28x5mg",price:40}],
      pain: [{name:"DHC 100x30mg",price:70},{name:"DHC 28x30mg",price:30},{name:"Codeine Phosphate 28x30mg",price:30},{name:"Tapentadol 100x100mg",price:60},{name:"Pregabalin 150x300mg",price:45}],
      sleepsex: [{name:"Zopsign 140x10mg",price:40},{name:"UK Zopiclone 28x7.5mg",price:35},{name:"Melatonin 50x10mg",price:30},{name:"Zolpidem 100x10mg",price:55},{name:"Cialis 100x60mg",price:50},{name:"Viagra 100x100mg",price:40},{name:"Viagra 100x200mg",price:55},{name:"Kamagra 7 sachets",price:12}],
      others: [{name:"Modafinil 100x200mg",price:40},{name:"Nasal Tanner",price:20},{name:"Accutane 50x20mg",price:30},{name:"10ml syringe pure RSO",price:160},{name:"Don Vape Cart 1000mg",price:40},{name:"Vape Juice 10ml",price:25},{name:"Edible 500mg",price:15},{name:"Metformin 100x1000mg",price:40},{name:"Finasteride 100x1mg",price:35}]
    };

    let html = `<div style="padding:10px 18px;">`;
    products[cat].forEach(p => {
      html += `
        <div style="display:flex;justify-content:space-between;align-items:center;padding:12px 0;border-bottom:1px solid #eee;">
          <div>
            <div style="font-weight:600;">${p.name}</div>
            <div style="color:#25D366;font-size:15px;">£${p.price}</div>
          </div>
          <div style="display:flex;align-items:center;gap:8px;">
            <button onclick="changeQty(this, -1)" style="width:28px;height:28px;border-radius:50%;background:#eee;border:none;cursor:pointer;">–</button>
            <span class="qty" style="width:30px;text-align:center;font-weight:600;">1</span>
            <button onclick="changeQty(this, 1)" style="width:28px;height:28px;border-radius:50%;background:#eee;border:none;cursor:pointer;">+</button>
            <button onclick="addToCart('${p.name}', ${p.price}, this)" style="margin-left:10px;padding:6px 14px;background:#25D366;color:#fff;border:none;border-radius:20px;cursor:pointer;font-size:13px;">Add to basket</button>
          </div>
        </div>`;
    });
    html += `</div>`;
    document.getElementById('modalBody').innerHTML = html;
  }

  function changeQty(btn, delta) {
    const qtySpan = btn.parentElement.querySelector('.qty');
    let qty = parseInt(qtySpan.textContent);
    qty = Math.max(1, qty + delta);
    qtySpan.textContent = qty;
  }

  function addToCart(name, price, btn) {
    const qty = parseInt(btn.parentElement.querySelector('.qty').textContent);
    cart.push({name, price, qty});
    alert(`✅ Added ${qty}x ${name} to basket\n\nCurrent total: £${cart.reduce((sum, item) => sum + item.price * item.qty, 0)}`);
  }

  function closeModal() {
    document.getElementById('modalOverlay').style.display = 'none';
  }

  function sendUserMessage() {
    const input = document.getElementById('chatInput');
    const text = input.value.trim();
    if (!text) return;
    input.value = '';
    const row = document.createElement('div');
    row.className = 'msg-row user';
    row.innerHTML = `<div class="bubble">${text}<div class="bubble-time">${now()} ✓✓</div></div>`;
    chatArea.appendChild(row);
    chatArea.scrollTop = chatArea.scrollHeight;
  }

  function handleKey(e) {
    if (e.key === 'Enter' && !e.shiftKey) {
      e.preventDefault();
      sendUserMessage();
    }
  }

  function autoResize(el) {
    el.style.height = 'auto';
    el.style.height = Math.min(el.scrollHeight, 80) + 'px';
  }

  (async () => {
    await addBotBubble("Welcome To UK Muscle 💪", 800);
    await addBotBubble("Take a browse — anything not listed please feel free to ask. We have a partnered vendor who has what we don’t (and vice versa).\n\nFor same day dispatch orders must be in by 3pm.\nWe send to anywhere on the planet 🌍\n\nShipping:\n• £5 NDD\n• £10 Special\n• £15 International tracked\n• £20 International tracked priority", 1200);
    addListCard();
  })();
</script>

</body>
</html>