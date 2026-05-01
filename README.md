[formulario.html](https://github.com/user-attachments/files/27288348/formulario.html)
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Dr Marcos Andrade — Agende sua Avaliação</title>

<!-- ══════════════════════════════════════════════════════════════
     META PIXEL — Coloque seu Pixel ID abaixo
     Instruções: Ads Manager → Events Manager → Pixel → copie o ID
     ══════════════════════════════════════════════════════════════ -->
<script>
  const META_PIXEL_ID = '1481871323442318'; // ← troque pelo seu ID

  !function(f,b,e,v,n,t,s){if(f.fbq)return;n=f.fbq=function(){n.callMethod?
  n.callMethod.apply(n,arguments):n.queue.push(arguments)};if(!f._fbq)f._fbq=n;
  n.push=n;n.loaded=!0;n.version='2.0';n.queue=[];t=b.createElement(e);t.async=!0;
  t.src=v;s=b.getElementsByTagName(e)[0];s.parentNode.insertBefore(t,s)}
  (window,document,'script','https://connect.facebook.net/en_US/fbevents.js');
  fbq('init', META_PIXEL_ID);
  fbq('track', 'PageView'); // dispara quando o lead abre o formulário
</script>
<noscript>
  <img height="1" width="1" style="display:none"
    src="https://www.facebook.com/tr?id=SEU_PIXEL_ID_AQUI&ev=PageView&noscript=1"/>
</noscript>
<!-- ══ FIM META PIXEL ══ -->

<link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@300;400;500;600&family=Syne:wght@400;600;700&display=swap" rel="stylesheet">

<style>
:root {
  --bg: #F5F3EE;
  --surface: #FFFFFF;
  --surface2: #F0EDE6;
  --border: rgba(0,0,0,0.08);
  --border2: rgba(0,0,0,0.14);
  --text: #1A1916;
  --muted: #7A7770;
  --accent: #3D2FBF;
  --accent-bg: #EDEAFF;
  --success: #1A6B45;
  --success-bg: #D6F0E3;
  --radius: 12px;
  --radius-sm: 8px;
  --shadow: 0 4px 24px rgba(0,0,0,0.10);
}

* { box-sizing: border-box; margin: 0; padding: 0; }

body {
  font-family: 'DM Sans', sans-serif;
  background: var(--bg);
  color: var(--text);
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 32px 16px;
}

.form-wrapper { width: 100%; max-width: 480px; }

.form-card {
  background: var(--surface);
  border-radius: 20px;
  overflow: hidden;
  box-shadow: var(--shadow);
  border: 1px solid var(--border);
}

.form-banner {
  background: var(--accent);
  padding: 28px 32px 24px;
  position: relative;
  overflow: hidden;
}
.form-banner::before {
  content: '';
  position: absolute;
  width: 220px; height: 220px;
  border-radius: 50%;
  background: rgba(255,255,255,0.06);
  top: -70px; right: -70px;
}
.form-banner h1 {
  font-family: 'Syne', sans-serif;
  font-size: 22px;
  font-weight: 700;
  color: #fff;
  margin-bottom: 6px;
  letter-spacing: -0.02em;
  position: relative;
}
.form-banner p {
  color: rgba(255,255,255,0.78);
  font-size: 13px;
  position: relative;
}

.form-body { padding: 28px 32px; }
.field { margin-bottom: 16px; }

.field label {
  display: block;
  font-size: 11px;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.06em;
  color: var(--muted);
  margin-bottom: 6px;
}

.field input,
.field select,
.field textarea {
  width: 100%;
  padding: 10px 14px;
  border: 1.5px solid var(--border2);
  border-radius: var(--radius-sm);
  font-family: 'DM Sans', sans-serif;
  font-size: 14px;
  color: var(--text);
  background: var(--surface);
  transition: border-color 0.15s, box-shadow 0.15s;
  outline: none;
  appearance: none;
}

.field input:focus,
.field select:focus,
.field textarea:focus {
  border-color: var(--accent);
  box-shadow: 0 0 0 3px rgba(61,47,191,0.12);
}

.field textarea { resize: vertical; min-height: 88px; }
.row-2 { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }

/* ── BOTÃO PRINCIPAL ── */
.btn-submit {
  width: 100%;
  padding: 14px;
  background: var(--accent);
  color: #fff;
  border: none;
  border-radius: var(--radius-sm);
  font-family: 'DM Sans', sans-serif;
  font-size: 15px;
  font-weight: 600;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  transition: all 0.15s;
  margin-top: 8px;
}
.btn-submit:hover { background: #2E22A0; transform: translateY(-1px); }
.btn-submit:active { transform: translateY(0); }
.btn-submit:disabled { opacity: 0.6; cursor: wait; }


.form-footer {
  padding: 14px 32px;
  background: var(--surface2);
  border-top: 1px solid var(--border);
  display: flex;
  align-items: center;
  gap: 8px;
  font-size: 12px;
  color: var(--muted);
}
.form-footer svg { opacity: 0.5; }

/* ── SUCESSO ── */
.success-state {
  display: none;
  flex-direction: column;
  align-items: center;
  text-align: center;
  padding: 40px 32px 32px;
  gap: 10px;
}
.success-icon {
  width: 60px; height: 60px; border-radius: 50%;
  background: var(--success-bg);
  color: var(--success);
  display: flex; align-items: center; justify-content: center;
  font-size: 26px;
  margin-bottom: 4px;
}
.success-state h2 { font-family: 'Syne', sans-serif; font-size: 20px; }
.success-state p { color: var(--muted); font-size: 13px; max-width: 300px; line-height: 1.5; }

@media (max-width: 480px) {
  .form-body { padding: 20px; }
  .form-banner { padding: 22px 20px 18px; }
  .form-footer { padding: 12px 20px; }
  .row-2 { grid-template-columns: 1fr; }
}
</style>
</head>
<body>

<div class="form-wrapper">
  <div class="form-card">

    <div class="form-banner">
      <h1>Agende sua avaliação</h1>
      <p>Deixe seus dados e nossa equipe retorna pelo WhatsApp.</p>
    </div>

    <div id="form-body-wrap">

      <!-- FORMULÁRIO -->
      <div class="form-body" id="form-body">
        <div class="row-2">
          <div class="field"><label>Nome completo</label><input type="text" id="inp-nome" placeholder="Seu nome completo"></div>
          <div class="field"><label>WhatsApp</label><input type="text" id="inp-whatsapp" placeholder="(62) 9 0000-0000"></div>
        </div>
        <div class="field"><label>Email</label><input type="email" id="inp-email" placeholder="voce@email.com"></div>
        <div class="field">
          <label>Serviço de interesse</label>
          <select id="inp-servico">
            <option value="">Selecione um serviço...</option>
            <!-- ✏️ EDITE A LISTA DE SERVIÇOS AQUI -->
            <option>Botox / Toxina botulínica</option>
            <option>Preenchimento facial</option>
            <option>Harmonização facial</option>
            <option>Bioestimulador de colágeno</option>
            <option>Limpeza de pele profunda</option>
            <option>Peeling químico</option>
            <option>Microagulhamento</option>
            <option>Depilação a laser</option>
            <option>Tratamento de manchas</option>
            <option>Tratamento para acne</option>
            <option>Avaliação dermatológica</option>
            <option>Outro / Não tenho certeza</option>
            <!-- ✏️ Para adicionar: <option>Nome do serviço</option> -->
            <!-- ✏️ Para remover: apague a linha inteira do serviço  -->
          </select>
        </div>
        <div class="field"><label>Mensagem (opcional)</label><textarea id="inp-mensagem" placeholder="Conte-nos mais sobre o que procura..."></textarea></div>

        <button class="btn-submit" id="btn-submit" onclick="submitForm()">
          <svg width="16" height="16" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M22 2L11 13M22 2l-7 20-4-9-9-4 20-7z"/></svg>
          <span id="btn-label">Enviar e agendar</span>
        </button>
      </div>

      <!-- SUCESSO -->
      <div class="success-state" id="success-state">
        <div class="success-icon">✓</div>
        <h2>Recebemos seus dados!</h2>
        <p>Em breve entraremos em contato pelo WhatsApp para agendar sua avaliação com o Dr. Marcos Andrade.</p>
      </div>

    </div>

    <div class="form-footer">
      <svg width="14" height="14" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><rect x="3" y="11" width="18" height="11" rx="2"/><path d="M7 11V7a5 5 0 0 1 10 0v4"/></svg>
      Seus dados estão seguros e não serão compartilhados.
    </div>

  </div>
</div>

<script>
// ═══════════════════════════════════════════════════════════════
// 🔧 CONFIGURAÇÃO — troque apenas os dois valores abaixo
// ═══════════════════════════════════════════════════════════════
const SCRIPT_URL = 'COLE_AQUI_A_URL_DO_APPS_SCRIPT';
const SECRET_KEY = 'Rico123';
// ═══════════════════════════════════════════════════════════════

function trackWppClick() {
  // Dispara evento no Meta Pixel quando clica no botão WhatsApp
  if (window.fbq) fbq('track', 'Contact');
}

async function submitForm() {
  const nome     = document.getElementById('inp-nome').value.trim();
  const whatsapp = document.getElementById('inp-whatsapp').value.trim();
  const email    = document.getElementById('inp-email').value.trim();
  const servico  = document.getElementById('inp-servico').value;
  const mensagem = document.getElementById('inp-mensagem').value.trim();

  if (!nome)     { alert('Por favor, preencha seu nome.'); return; }
  if (!whatsapp) { alert('Por favor, informe seu WhatsApp.'); return; }

  if (SCRIPT_URL.startsWith('COLE_AQUI')) {
    alert('⚠️ Configure o SCRIPT_URL no topo do <script> deste arquivo.');
    return;
  }

  const btn = document.getElementById('btn-submit');
  const lbl = document.getElementById('btn-label');
  btn.disabled = true;
  lbl.textContent = 'Enviando...';

  const payload = {
    action: 'create',
    key: SECRET_KEY,
    id: 'c_' + Date.now(),
    tag: 'new',
    status: 'Novo lead',
    nome, whatsapp, email, servico, mensagem
  };

  try {
    const res = await fetch(SCRIPT_URL, {
      method: 'POST',
      headers: { 'Content-Type': 'text/plain;charset=utf-8' },
      body: JSON.stringify(payload)
    });
    const json = await res.json();
    if (!json.ok) throw new Error(json.error || 'erro desconhecido');

    // ── Dispara eventos no Meta Pixel ──
    if (window.fbq) {
      fbq('track', 'Lead');
      fbq('track', 'CompleteRegistration');
    }

    // Mostra tela de sucesso brevemente e redireciona pro WhatsApp
    document.getElementById('form-body').style.display = 'none';
    document.getElementById('success-state').style.display = 'flex';

    // Após 1.5s abre o WhatsApp (tempo suficiente para o pixel disparar)
    setTimeout(() => {
      window.location.href = 'https://wa.me/5562920008978?text=Ol%C3%A1!%20Quero%20agendar%20uma%20avalia%C3%A7%C3%A3o';
    }, 1500);

  } catch (err) {
    alert('Erro ao enviar: ' + err.message + '\n\nTente pelo WhatsApp abaixo.');
    btn.disabled = false;
    lbl.textContent = 'Enviar e agendar';
  }
}
</script>
</body>
</html>
