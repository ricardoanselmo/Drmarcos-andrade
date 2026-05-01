[index-drmarcos2026.html](https://github.com/user-attachments/files/27267599/index-drmarcos2026.html)
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Dr Marcos Andrade — CRM</title>
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
  --accent-mid: #7B6EE8;
  --success: #1A6B45;
  --success-bg: #D6F0E3;
  --warn: #8A5A00;
  --warn-bg: #FFF0CC;
  --danger: #8B2020;
  --danger-bg: #FFE5E5;
  --radius: 12px;
  --radius-sm: 8px;
  --shadow: 0 2px 16px rgba(0,0,0,0.07);
}

* { box-sizing: border-box; margin: 0; padding: 0; }

body {
  font-family: 'DM Sans', sans-serif;
  background: var(--bg);
  color: var(--text);
  min-height: 100vh;
  font-size: 14px;
}

.app { display: flex; flex-direction: column; height: 100vh; }

.topbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 28px;
  height: 56px;
  background: var(--surface);
  border-bottom: 1px solid var(--border);
  flex-shrink: 0;
}

.logo {
  font-family: 'Syne', sans-serif;
  font-weight: 700;
  font-size: 18px;
  letter-spacing: -0.03em;
  color: var(--accent);
}

.nav-tabs {
  display: flex;
  gap: 4px;
  background: var(--bg);
  padding: 4px;
  border-radius: var(--radius-sm);
}

.nav-tab {
  padding: 6px 16px;
  border-radius: 6px;
  font-size: 13px;
  font-weight: 500;
  cursor: pointer;
  border: none;
  background: transparent;
  color: var(--muted);
  transition: all 0.15s;
}

.nav-tab.active {
  background: var(--surface);
  color: var(--text);
  box-shadow: 0 1px 4px rgba(0,0,0,0.1);
}

.topbar-right {
  display: flex;
  align-items: center;
  gap: 10px;
}

.notif-pill {
  display: none;
  align-items: center;
  gap: 6px;
  padding: 6px 12px;
  background: var(--accent-bg);
  color: var(--accent);
  border-radius: 20px;
  font-size: 12px;
  font-weight: 500;
  animation: slideIn 0.3s ease;
}

@keyframes slideIn { from { opacity:0; transform:translateY(-6px); } to { opacity:1; transform:translateY(0); } }

.notif-dot {
  width: 7px; height: 7px;
  border-radius: 50%;
  background: var(--accent);
  animation: blink 1.2s infinite;
}
@keyframes blink { 0%,100%{opacity:1} 50%{opacity:0.25} }

.avatar-sm {
  width: 32px; height: 32px; border-radius: 50%;
  background: var(--accent-bg);
  color: var(--accent);
  display: flex; align-items: center; justify-content: center;
  font-size: 12px; font-weight: 600;
}

.main { flex: 1; overflow: hidden; }
.panel { display: none; height: 100%; }
.panel.active { display: flex; }

#view-form {
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 40px 20px;
  overflow-y: auto;
  gap: 20px;
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
  width: 200px; height: 200px;
  border-radius: 50%;
  background: rgba(255,255,255,0.06);
  top: -60px; right: -60px;
}

.form-banner h1 {
  font-family: 'Syne', sans-serif;
  font-size: 22px;
  font-weight: 700;
  color: #fff;
  margin-bottom: 6px;
  letter-spacing: -0.02em;
}

.form-banner p { color: rgba(255,255,255,0.75); font-size: 13px; }

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

.btn-submit {
  width: 100%;
  padding: 13px;
  background: var(--accent);
  color: #fff;
  border: none;
  border-radius: var(--radius-sm);
  font-family: 'DM Sans', sans-serif;
  font-size: 14px;
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

.success-state {
  display: none;
  flex-direction: column;
  align-items: center;
  text-align: center;
  padding: 48px 32px;
  gap: 12px;
}
.success-icon {
  width: 56px; height: 56px; border-radius: 50%;
  background: var(--success-bg);
  color: var(--success);
  display: flex; align-items: center; justify-content: center;
  font-size: 24px;
}
.success-state h2 { font-family: 'Syne', sans-serif; font-size: 20px; }
.success-state p { color: var(--muted); font-size: 13px; }

#view-editor {
  flex-direction: column;
  overflow-y: auto;
  padding: 32px 40px;
  gap: 24px;
}

.editor-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 24px; }

.editor-section {
  background: var(--surface);
  border-radius: var(--radius);
  border: 1px solid var(--border);
  padding: 24px;
}

.editor-section h3 {
  font-family: 'Syne', sans-serif;
  font-size: 13px;
  font-weight: 600;
  letter-spacing: 0.04em;
  text-transform: uppercase;
  color: var(--muted);
  margin-bottom: 16px;
}

.chip-grid { display: flex; flex-wrap: wrap; gap: 6px; }

.chip {
  display: inline-flex; align-items: center; gap: 6px;
  padding: 6px 12px;
  border: 1.5px solid var(--border2);
  border-radius: 20px;
  font-size: 12px;
  font-weight: 500;
  cursor: pointer;
  background: var(--surface);
  color: var(--muted);
  transition: all 0.15s;
  user-select: none;
}

.chip.on {
  background: var(--accent-bg);
  border-color: var(--accent-mid);
  color: var(--accent);
}

.color-grid { display: flex; gap: 10px; flex-wrap: wrap; }

.swatch {
  width: 28px; height: 28px;
  border-radius: 50%;
  cursor: pointer;
  border: 3px solid transparent;
  transition: all 0.15s;
  box-shadow: 0 1px 4px rgba(0,0,0,0.15);
}

.swatch.active { border-color: var(--text); transform: scale(1.12); }

.col-rows { display: flex; flex-direction: column; gap: 8px; }

.col-row { display: flex; align-items: center; gap: 8px; }

.col-row input {
  flex: 1;
  padding: 7px 10px;
  border: 1.5px solid var(--border2);
  border-radius: var(--radius-sm);
  font-family: 'DM Sans', sans-serif;
  font-size: 13px;
  color: var(--text);
  background: var(--surface);
  outline: none;
}
.col-row input:focus { border-color: var(--accent); }

.col-del {
  width: 24px; height: 24px;
  border-radius: 50%;
  background: var(--surface2);
  border: 1px solid var(--border);
  cursor: pointer;
  display: flex; align-items: center; justify-content: center;
  font-size: 11px; color: var(--muted);
  flex-shrink: 0;
  transition: background 0.1s;
}
.col-del:hover { background: var(--danger-bg); color: var(--danger); }

.btn-add {
  margin-top: 8px;
  padding: 7px 14px;
  border: 1.5px dashed var(--border2);
  border-radius: var(--radius-sm);
  background: none;
  font-family: 'DM Sans', sans-serif;
  font-size: 12px;
  color: var(--muted);
  cursor: pointer;
  transition: all 0.15s;
}
.btn-add:hover { border-color: var(--accent-mid); color: var(--accent); }

.editor-input {
  width: 100%;
  padding: 9px 12px;
  border: 1.5px solid var(--border2);
  border-radius: var(--radius-sm);
  font-family: 'DM Sans', sans-serif;
  font-size: 14px;
  color: var(--text);
  background: var(--surface);
  outline: none;
}
.editor-input:focus { border-color: var(--accent); box-shadow: 0 0 0 3px rgba(61,47,191,0.12); }

#view-kanban {
  flex-direction: column;
  overflow: hidden;
  padding: 24px 28px;
  gap: 20px;
}

.kanban-top {
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-shrink: 0;
}

.kanban-top h2 {
  font-family: 'Syne', sans-serif;
  font-size: 20px;
  font-weight: 700;
}

.stats-row { display: flex; gap: 10px; align-items: center; }

.stat {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: var(--radius-sm);
  padding: 8px 16px;
  text-align: center;
}

.stat-n {
  font-family: 'Syne', sans-serif;
  font-size: 18px;
  font-weight: 700;
  color: var(--accent);
}

.stat-l { font-size: 10px; text-transform: uppercase; letter-spacing: 0.06em; color: var(--muted); }

.btn-reload {
  padding: 8px 14px;
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: var(--radius-sm);
  font-family: 'DM Sans', sans-serif;
  font-size: 12px;
  font-weight: 500;
  color: var(--text);
  cursor: pointer;
  display: flex; align-items: center; gap: 6px;
  transition: all 0.15s;
}
.btn-reload:hover { border-color: var(--accent-mid); color: var(--accent); }
.btn-reload:disabled { opacity: 0.5; cursor: wait; }

.board {
  display: flex;
  gap: 14px;
  overflow-x: auto;
  flex: 1;
  padding-bottom: 8px;
}

.col {
  flex: 0 0 260px;
  display: flex;
  flex-direction: column;
  background: var(--surface2);
  border-radius: var(--radius);
  padding: 14px;
  border: 1px solid var(--border);
}

.col-head {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 12px;
  flex-shrink: 0;
}

.col-name {
  font-size: 12px;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.06em;
}

.col-badge {
  padding: 2px 8px;
  border-radius: 20px;
  background: var(--surface);
  font-size: 11px;
  font-weight: 600;
  color: var(--muted);
  border: 1px solid var(--border);
}

.cards {
  flex: 1;
  overflow-y: auto;
  min-height: 80px;
  display: flex;
  flex-direction: column;
  gap: 8px;
  border-radius: var(--radius-sm);
  transition: background 0.15s;
  padding: 4px;
}

.cards.over { background: rgba(61,47,191,0.06); }

.card {
  background: var(--surface);
  border-radius: var(--radius-sm);
  padding: 12px 14px;
  border: 1.5px solid var(--border);
  cursor: grab;
  transition: box-shadow 0.15s, transform 0.15s;
  user-select: none;
}

.card:hover { box-shadow: 0 4px 16px rgba(0,0,0,0.1); transform: translateY(-1px); }
.card:active { cursor: grabbing; opacity: 0.85; }

.card-top {
  display: flex; align-items: center; justify-content: space-between; margin-bottom: 6px;
}

.card-name-text { font-size: 13px; font-weight: 600; }
.card-time { font-size: 10px; color: var(--muted); }
.card-detail { font-size: 11px; color: var(--muted); margin-bottom: 8px; }
.card-chips { display: flex; gap: 4px; flex-wrap: wrap; }

.chip-sm {
  padding: 3px 8px;
  border-radius: 20px;
  font-size: 10px;
  font-weight: 600;
}

.chip-new { background: var(--accent-bg); color: var(--accent); }
.chip-hot { background: #FFE8E0; color: #C03A0A; }
.chip-warm { background: var(--warn-bg); color: var(--warn); }
.chip-cold { background: #E6F1FB; color: #185FA5; }
.chip-won { background: var(--success-bg); color: var(--success); }

.wpp-btn {
  display: inline-flex; align-items: center; justify-content: center;
  width: 26px; height: 26px;
  border-radius: 50%;
  background: #25D366;
  color: #fff;
  font-size: 13px;
  text-decoration: none;
  transition: transform 0.1s, box-shadow 0.1s;
  cursor: pointer;
}
.wpp-btn:hover { transform: scale(1.1); box-shadow: 0 2px 8px rgba(37,211,102,0.4); }

.mini-av {
  width: 26px; height: 26px; border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-size: 10px; font-weight: 700;
  flex-shrink: 0;
}

/* Login simples */
.login-overlay {
  position: fixed; inset: 0;
  background: var(--bg);
  display: flex; align-items: center; justify-content: center;
  z-index: 9999;
}
.login-card {
  background: var(--surface);
  padding: 32px;
  border-radius: 16px;
  border: 1px solid var(--border);
  box-shadow: var(--shadow);
  max-width: 360px; width: 100%;
}
.login-card h2 { font-family: 'Syne', sans-serif; margin-bottom: 6px; }
.login-card p { font-size: 13px; color: var(--muted); margin-bottom: 18px; }
.login-card input {
  width: 100%; padding: 10px 14px;
  border: 1.5px solid var(--border2);
  border-radius: var(--radius-sm);
  font-family: 'DM Sans', sans-serif; font-size: 14px;
  outline: none; margin-bottom: 12px;
}
.login-card input:focus { border-color: var(--accent); }
.login-err { color: var(--danger); font-size: 12px; margin-bottom: 8px; min-height: 16px; }

::-webkit-scrollbar { width: 5px; height: 5px; }
::-webkit-scrollbar-track { background: transparent; }
::-webkit-scrollbar-thumb { background: var(--border2); border-radius: 99px; }
</style>
</head>
<body>

<!-- LOGIN (proteção simples para ser de uso pessoal) -->
<div class="login-overlay" id="login-overlay">
  <div class="login-card">
    <h2>Dr Marcos Andrade</h2>
    <p>Digite a senha para acessar o painel.</p>
    <input type="password" id="login-input" placeholder="Senha" onkeydown="if(event.key==='Enter')doLogin()">
    <div class="login-err" id="login-err"></div>
    <button class="btn-submit" onclick="doLogin()">Entrar</button>
  </div>
</div>

<div class="app" id="app" style="display:none">

  <div class="topbar">
    <div class="logo">Dr Marcos Andrade</div>
    <div class="nav-tabs">
      <button class="nav-tab active" onclick="switchTab('form')">Formulário</button>
      <button class="nav-tab" onclick="switchTab('editor')">Personalizar</button>
      <button class="nav-tab" onclick="switchTab('kanban')">Kanban</button>
    </div>
    <div class="topbar-right">
      <div class="notif-pill" id="notif-pill">
        <div class="notif-dot"></div>
        <span id="notif-text">Novo lead!</span>
      </div>
      <div class="avatar-sm">VC</div>
    </div>
  </div>

  <div class="main">

    <!-- FORM -->
    <div class="panel active" id="view-form">
      <div class="form-wrapper">
        <div class="form-card">
          <div class="form-banner">
            <h1 id="form-title">Agende sua avaliação</h1>
            <p id="form-sub">Deixe seus dados e nossa equipe retorna pelo WhatsApp.</p>
          </div>

          <div id="form-body-wrap">
            <div class="form-body" id="form-body">
              <div class="row-2">
                <div class="field" id="f-nome"><label>Nome completo</label><input type="text" data-key="nome" placeholder="Seu nome completo"></div>
                <div class="field" id="f-empresa" style="display:none"><label>Empresa</label><input type="text" data-key="empresa" placeholder="Nome da empresa"></div>
              </div>
              <div class="row-2">
                <div class="field" id="f-whatsapp"><label>WhatsApp</label><input type="text" data-key="whatsapp" placeholder="+55 (11) 9 0000-0000"></div>
                <div class="field" id="f-email"><label>Email</label><input type="email" data-key="email" placeholder="voce@email.com"></div>
              </div>
              <div class="field" id="f-servico"><label>Serviço de interesse</label>
                <select data-key="servico">
                  <option value="">Selecione um serviço...</option>
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
                </select>
              </div>
              <div class="row-2">
                <div class="field" id="f-cidade" style="display:none"><label>Cidade</label><input type="text" data-key="cidade" placeholder="Sua cidade"></div>
                <div class="field" id="f-melhor-horario" style="display:none"><label>Melhor horário pra contato</label><input type="text" data-key="melhor_horario" placeholder="Ex: manhã, tarde, após 18h"></div>
              </div>
              <div class="field" id="f-mensagem"><label>Mensagem (opcional)</label><textarea data-key="mensagem" placeholder="Conte-nos mais sobre o que procura..."></textarea></div>
              <button class="btn-submit" id="btn-submit" onclick="submitForm()">
                <svg width="16" height="16" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M22 2L11 13M22 2l-7 20-4-9-9-4 20-7z"/></svg>
                <span id="btn-submit-label">Enviar mensagem</span>
              </button>
            </div>
            <div class="success-state" id="success-state">
              <div class="success-icon">✓</div>
              <h2>Recebemos seus dados!</h2>
              <p>Em breve entraremos em contato pelo WhatsApp para agendar sua avaliação.</p>
            </div>
          </div>

          <div class="form-footer">
            <svg width="14" height="14" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><rect x="3" y="11" width="18" height="11" rx="2"/><path d="M7 11V7a5 5 0 0 1 10 0v4"/></svg>
            Seus dados estão seguros e não serão compartilhados.
          </div>
        </div>
      </div>
    </div>

    <!-- EDITOR -->
    <div class="panel" id="view-editor">
      <div class="editor-grid" style="width:100%;max-width:860px;margin:0 auto">
        <div class="editor-section">
          <h3>Campos do formulário</h3>
          <div class="chip-grid" id="field-chips">
            <div class="chip on" data-field="f-nome">✓ Nome</div>
            <div class="chip on" data-field="f-whatsapp">✓ WhatsApp</div>
            <div class="chip on" data-field="f-email">✓ Email</div>
            <div class="chip on" data-field="f-servico">✓ Serviço</div>
            <div class="chip on" data-field="f-mensagem">✓ Mensagem</div>
            <div class="chip" data-field="f-cidade">+ Cidade</div>
            <div class="chip" data-field="f-melhor-horario">+ Melhor horário</div>
            <div class="chip" data-field="f-empresa">+ Empresa</div>
          </div>
        </div>
        <div class="editor-section">
          <h3>Textos</h3>
          <div class="field">
            <label style="font-size:11px;font-weight:600;text-transform:uppercase;letter-spacing:0.06em;color:var(--muted);display:block;margin-bottom:6px">Título</label>
            <input class="editor-input" type="text" value="Agende sua avaliação" oninput="document.getElementById('form-title').textContent=this.value">
          </div>
          <div class="field" style="margin-top:12px">
            <label style="font-size:11px;font-weight:600;text-transform:uppercase;letter-spacing:0.06em;color:var(--muted);display:block;margin-bottom:6px">Subtítulo</label>
            <input class="editor-input" type="text" value="Deixe seus dados e nossa equipe retorna pelo WhatsApp." oninput="document.getElementById('form-sub').textContent=this.value">
          </div>
        </div>
        <div class="editor-section">
          <h3>Cor principal</h3>
          <div class="color-grid">
            <div class="swatch active" style="background:#3D2FBF" onclick="setAccent('#3D2FBF','#EDEAFF','#7B6EE8',this)"></div>
            <div class="swatch" style="background:#0F6E56" onclick="setAccent('#0F6E56','#D6F0E3','#1D9E75',this)"></div>
            <div class="swatch" style="background:#C03A0A" onclick="setAccent('#C03A0A','#FFE8E0','#E87040',this)"></div>
            <div class="swatch" style="background:#185FA5" onclick="setAccent('#185FA5','#E6F1FB','#378ADD',this)"></div>
            <div class="swatch" style="background:#7B2D8B" onclick="setAccent('#7B2D8B','#F5E6FF','#B97BC8',this)"></div>
            <div class="swatch" style="background:#8B6000" onclick="setAccent('#8B6000','#FFF0CC','#E0A010',this)"></div>
            <div class="swatch" style="background:#1A1916" onclick="setAccent('#1A1916','#F0EDE6','#888780',this)"></div>
          </div>
        </div>
        <div class="editor-section">
          <h3>Colunas do Kanban</h3>
          <div class="col-rows" id="col-editor">
            <div class="col-row"><input type="text" value="Novo lead" oninput="syncCols()"><div class="col-del" onclick="removeColRow(this)" title="Remover">✕</div></div>
            <div class="col-row"><input type="text" value="Em contato" oninput="syncCols()"><div class="col-del" onclick="removeColRow(this)" title="Remover">✕</div></div>
            <div class="col-row"><input type="text" value="Avaliação agendada" oninput="syncCols()"><div class="col-del" onclick="removeColRow(this)" title="Remover">✕</div></div>
            <div class="col-row"><input type="text" value="Cliente fechado" oninput="syncCols()"><div class="col-del" onclick="removeColRow(this)" title="Remover">✕</div></div>
            <div class="col-row"><input type="text" value="Não converteu" oninput="syncCols()"><div class="col-del" onclick="removeColRow(this)" title="Remover">✕</div></div>
          </div>
          <button class="btn-add" onclick="addColRow()">+ nova coluna</button>
        </div>
      </div>
    </div>

    <!-- KANBAN -->
    <div class="panel" id="view-kanban">
      <div class="kanban-top">
        <h2>Pipeline de vendas</h2>
        <div class="stats-row">
          <div class="stat"><div class="stat-n" id="stat-total">0</div><div class="stat-l">Leads</div></div>
          <div class="stat"><div class="stat-n" id="stat-hoje">0</div><div class="stat-l">Hoje</div></div>
          <button class="btn-reload" id="btn-reload" onclick="loadFromSheet(true)">↻ Recarregar</button>
        </div>
      </div>
      <div class="board" id="board"></div>
    </div>

  </div>
</div>

<script>
// ═══════════════════════════════════════════════════════════════
// 🔧 CONFIGURAÇÃO — TROQUE OS DOIS VALORES ABAIXO
// ═══════════════════════════════════════════════════════════════

// 1) URL do seu Apps Script implantado como Web App
//    (gerada quando você clica em "Implantar → Nova implantação")
const SCRIPT_URL = 'COLE_AQUI_A_URL_DO_APPS_SCRIPT';

// 2) Senha — tem que ser EXATAMENTE igual ao SECRET_KEY do Apps Script.
//    Também é usada pra entrar no painel.
const SECRET_KEY = 'drmarcos2026';

// ═══════════════════════════════════════════════════════════════

// ─── LOGIN (proteção simples por senha) ───
function doLogin() {
  const v = document.getElementById('login-input').value;
  if (v === SECRET_KEY) {
    sessionStorage.setItem('lf_auth', '1');
    showApp();
  } else {
    document.getElementById('login-err').textContent = 'Senha incorreta.';
  }
}
function showApp() {
  document.getElementById('login-overlay').style.display = 'none';
  document.getElementById('app').style.display = 'flex';
}
if (sessionStorage.getItem('lf_auth') === '1') showApp();

// ─── STATE ───
const state = {
  accent: '#3D2FBF',
  accentBg: '#EDEAFF',
  accentMid: '#7B6EE8',
  cols: ['Novo lead', 'Em contato', 'Avaliação agendada', 'Cliente fechado', 'Não converteu'],
  cards: { 'Novo lead': [], 'Em contato': [], 'Avaliação agendada': [], 'Cliente fechado': [], 'Não converteu': [] },
  drag: null,
  loaded: false
};

// ─── TABS ───
function switchTab(t) {
  document.querySelectorAll('.nav-tab').forEach((b, i) => b.classList.toggle('active', ['form', 'editor', 'kanban'][i] === t));
  document.querySelectorAll('.panel').forEach(p => p.classList.remove('active'));
  document.getElementById('view-' + t).classList.add('active');
  if (t === 'kanban') {
    if (!state.loaded) loadFromSheet();
    else renderBoard();
  }
}

// ─── ACCENT ───
function setAccent(c, bg, mid, el) {
  state.accent = c; state.accentBg = bg; state.accentMid = mid;
  document.querySelectorAll('.swatch').forEach(s => s.classList.remove('active'));
  el.classList.add('active');
  document.querySelector(':root').style.setProperty('--accent', c);
  document.querySelector(':root').style.setProperty('--accent-bg', bg);
  document.querySelector(':root').style.setProperty('--accent-mid', mid);
}

// ─── FIELD CHIPS ───
document.getElementById('field-chips').addEventListener('click', e => {
  const chip = e.target.closest('.chip');
  if (!chip) return;
  const field = document.getElementById(chip.dataset.field);
  if (!field) return;
  const on = chip.classList.toggle('on');
  chip.textContent = (on ? '✓ ' : '+ ') + chip.textContent.replace(/^[✓+] /, '');
  field.style.display = on ? '' : 'none';
});

// ─── COL EDITOR ───
function addColRow() {
  const d = document.createElement('div');
  d.className = 'col-row';
  d.innerHTML = `<input type="text" placeholder="Nova coluna" oninput="syncCols()"><div class="col-del" onclick="removeColRow(this)" title="Remover">✕</div>`;
  document.getElementById('col-editor').appendChild(d);
  syncCols();
}
function removeColRow(el) { el.parentElement.remove(); syncCols(); }
function syncCols() {
  const inputs = document.querySelectorAll('#col-editor input');
  const newCols = Array.from(inputs).map(i => i.value.trim()).filter(Boolean);
  const newCards = {};
  newCols.forEach(c => { newCards[c] = state.cards[c] || []; });
  state.cols = newCols;
  state.cards = newCards;
}

// ═══════════════════════════════════════════════════════════════
// 🌐 INTEGRAÇÃO COM GOOGLE SHEETS (via Apps Script)
// ═══════════════════════════════════════════════════════════════

function checkConfig() {
  if (SCRIPT_URL.startsWith('COLE_AQUI') || SECRET_KEY.startsWith('TROQUE')) {
    alert('⚠️ Você ainda não configurou o SCRIPT_URL e a SECRET_KEY no topo do <script> do HTML. Veja o guia.');
    return false;
  }
  return true;
}

// Envia lead novo para a planilha
async function submitForm() {
  if (!checkConfig()) return;

  const body = document.getElementById('form-body');
  const data = { action: 'create', key: SECRET_KEY, id: 'c_' + Date.now(), tag: 'new', status: state.cols[0] || 'Novo lead' };

  body.querySelectorAll('input, select, textarea').forEach(el => {
    const k = el.dataset.key;
    if (k && el.closest('.field').style.display !== 'none') data[k] = el.value;
  });

  if (!data.nome) { alert('Por favor, preencha o nome.'); return; }

  const btn = document.getElementById('btn-submit');
  const lbl = document.getElementById('btn-submit-label');
  btn.disabled = true; lbl.textContent = 'Enviando...';

  try {
    // Apps Script aceita text/plain sem disparar preflight CORS
    const res = await fetch(SCRIPT_URL, {
      method: 'POST',
      headers: { 'Content-Type': 'text/plain;charset=utf-8' },
      body: JSON.stringify(data)
    });
    const json = await res.json();
    if (!json.ok) throw new Error(json.error || 'erro');

    document.getElementById('form-body').style.display = 'none';
    document.getElementById('success-state').style.display = 'flex';

    // Notificação
    document.getElementById('notif-text').textContent = `Novo lead: ${data.nome}`;
    const pill = document.getElementById('notif-pill');
    pill.style.display = 'flex';
    setTimeout(() => pill.style.display = 'none', 5000);

    // Marca para recarregar Kanban quando abrir
    state.loaded = false;

    // Reset depois de 3s pra permitir novo envio
    setTimeout(() => {
      document.getElementById('form-body').style.display = '';
      document.getElementById('success-state').style.display = 'none';
      body.querySelectorAll('input, textarea').forEach(el => el.value = '');
      body.querySelectorAll('select').forEach(el => el.selectedIndex = 0);
      btn.disabled = false; lbl.textContent = 'Enviar mensagem';
    }, 3000);

  } catch (err) {
    alert('Erro ao enviar: ' + err.message);
    btn.disabled = false; lbl.textContent = 'Enviar mensagem';
  }
}

// Carrega leads existentes da planilha
async function loadFromSheet(force) {
  if (!checkConfig()) { renderBoard(); return; }

  const btn = document.getElementById('btn-reload');
  if (btn) { btn.disabled = true; btn.textContent = '⌛ Carregando...'; }

  try {
    const url = SCRIPT_URL + '?key=' + encodeURIComponent(SECRET_KEY) + '&t=' + Date.now();
    const res = await fetch(url);
    const json = await res.json();
    if (!json.ok) throw new Error(json.error || 'erro');

    syncCols();
    // Reset cards
    state.cols.forEach(c => state.cards[c] = []);

    json.leads.forEach(lead => {
      const status = lead.status || state.cols[0];
      if (!state.cards[status]) state.cards[status] = [];
      state.cards[status].push({
        id: lead.id || ('c_' + Math.random()),
        name: lead.nome || '(sem nome)',
        detail: [lead.servico || '', lead.whatsapp || lead.email || ''].filter(Boolean).join(' · '),
        whatsapp: lead.whatsapp || '',
        tag: lead.tag || 'new',
        time: formatTime(lead.criado_em)
      });
    });

    state.loaded = true;
  } catch (err) {
    console.error(err);
    if (force) alert('Erro ao carregar leads: ' + err.message);
  } finally {
    if (btn) { btn.disabled = false; btn.textContent = '↻ Recarregar'; }
    renderBoard();
  }
}

function formatTime(iso) {
  if (!iso) return '';
  const d = new Date(iso);
  if (isNaN(d)) return '';
  const diff = (Date.now() - d.getTime()) / 1000;
  if (diff < 60) return 'agora';
  if (diff < 3600) return `há ${Math.floor(diff / 60)} min`;
  if (diff < 86400) return `há ${Math.floor(diff / 3600)}h`;
  if (diff < 172800) return 'ontem';
  return d.toLocaleDateString('pt-BR');
}

// Atualiza status do lead na planilha (drag & drop)
async function updateStatusOnSheet(id, status) {
  if (!checkConfig()) return;
  try {
    await fetch(SCRIPT_URL, {
      method: 'POST',
      headers: { 'Content-Type': 'text/plain;charset=utf-8' },
      body: JSON.stringify({ action: 'update_status', key: SECRET_KEY, id, status })
    });
  } catch (err) {
    console.error('Falha ao atualizar status:', err);
    alert('Não consegui salvar a mudança na planilha. Recarregue para tentar de novo.');
  }
}

// ═══════════════════════════════════════════════════════════════
// KANBAN
// ═══════════════════════════════════════════════════════════════

const tagMap = {
  new: ['chip-new', 'novo'],
  hot: ['chip-hot', 'quente'],
  warm: ['chip-warm', 'morno'],
  cold: ['chip-cold', 'frio'],
  won: ['chip-won', 'fechado']
};

function initials(name) {
  return (name || '?').split(' ').map(w => w[0]).join('').toUpperCase().slice(0, 2);
}

const avatarColors = ['#EDEAFF', '#D6F0E3', '#FFE8E0', '#E6F1FB', '#F5E6FF', '#FFF0CC'];
const avatarText = ['#3D2FBF', '#0F6E56', '#C03A0A', '#185FA5', '#7B2D8B', '#8B6000'];

function renderBoard() {
  const board = document.getElementById('board');
  board.innerHTML = '';
  syncCols();

  state.cols.forEach((colName, ci) => {
    const cards = state.cards[colName] || [];
    const col = document.createElement('div');
    col.className = 'col';
    col.innerHTML = `
      <div class="col-head">
        <span class="col-name" style="color:var(--accent)">${colName}</span>
        <span class="col-badge">${cards.length}</span>
      </div>
      <div class="cards" id="cards-${ci}" ondragover="onOver(event,this)" ondrop="onDrop(event,'${colName.replace(/'/g, "\\'")}')" ondragleave="onLeave(event,this)"></div>`;
    board.appendChild(col);

    const container = col.querySelector('.cards');
    cards.forEach(card => container.appendChild(makeCard(card, ci)));
  });

  updateStats();
}

function makeCard(card, ci) {
  const [cls, label] = tagMap[card.tag] || ['chip-new', 'novo'];
  const av = document.createElement('div');
  const idx = (card.id || '').charCodeAt(0) % avatarColors.length || 0;
  av.className = 'mini-av';
  av.style.background = avatarColors[idx];
  av.style.color = avatarText[idx];
  av.textContent = initials(card.name);

  const el = document.createElement('div');
  el.className = 'card';
  el.id = card.id;
  el.draggable = true;
  const wppNumber = (card.whatsapp || '').replace(/\D/g, '');
  const wppBtn = wppNumber ? `<a href="https://wa.me/${wppNumber.startsWith('55') ? wppNumber : '55' + wppNumber}" target="_blank" rel="noopener" class="wpp-btn" title="Abrir WhatsApp" onclick="event.stopPropagation()">💬</a>` : '';
  el.innerHTML = `
    <div class="card-top">
      <span class="card-name-text">${card.name}</span>
      <span class="card-time">${card.time || ''}</span>
    </div>
    <div class="card-detail">${card.detail || ''}</div>
    <div style="display:flex;align-items:center;justify-content:space-between;gap:6px">
      <div class="card-chips"><span class="chip-sm ${cls}">${label}</span></div>
      ${wppBtn}
    </div>`;
  el.querySelector('.card-chips').parentElement.appendChild(av);
  el.addEventListener('dragstart', () => { state.drag = { card, fromCol: state.cols[ci] }; el.style.opacity = '0.5'; });
  el.addEventListener('dragend', () => el.style.opacity = '1');
  return el;
}

function onOver(e, el) { e.preventDefault(); el.classList.add('over'); }
function onLeave(e, el) { el.classList.remove('over'); }

function onDrop(e, toColName) {
  e.preventDefault();
  e.currentTarget.classList.remove('over');
  if (!state.drag) return;
  const { card, fromCol } = state.drag;
  if (fromCol === toColName) return;
  state.cards[fromCol] = (state.cards[fromCol] || []).filter(c => c.id !== card.id);
  if (!state.cards[toColName]) state.cards[toColName] = [];
  state.cards[toColName].push(card);
  state.drag = null;
  renderBoard();
  updateStatusOnSheet(card.id, toColName); // persiste na planilha
}

function updateStats() {
  let total = 0;
  state.cols.forEach(c => total += (state.cards[c] || []).length);
  document.getElementById('stat-total').textContent = total;
  const today = state.cols.reduce((sum, c) => sum + (state.cards[c] || []).filter(card => /agora|min/.test(card.time || '')).length, 0);
  document.getElementById('stat-hoje').textContent = today;
}

// ─── INIT ───
renderBoard();
</script>
</body>
</html>
