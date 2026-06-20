:root {
  --bg: #110f18;
  --panel: rgba(255, 255, 255, 0.08);
  --panel-strong: rgba(255, 255, 255, 0.13);
  --card: rgba(255, 255, 255, 0.10);
  --text: #f7f1ff;
  --muted: #c7bcd6;
  --faint: #8e819e;
  --line: rgba(255, 255, 255, 0.14);
  --accent: #b793ff;
  --accent-2: #7ee7d6;
  --danger: #ff8d8d;
  --ok: #8bf2b0;
  --shadow: 0 28px 90px rgba(0, 0, 0, 0.28);
  font-family: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
}

* {
  box-sizing: border-box;
}

body {
  margin: 0;
  min-height: 100vh;
  background:
    radial-gradient(circle at 15% 10%, rgba(183, 147, 255, 0.24), transparent 34rem),
    radial-gradient(circle at 90% 30%, rgba(126, 231, 214, 0.16), transparent 34rem),
    linear-gradient(135deg, #0e0d15 0%, #181423 55%, #10131d 100%);
  color: var(--text);
}

button,
input,
textarea,
select {
  font: inherit;
}

button {
  cursor: pointer;
}

textarea,
input,
select {
  width: 100%;
  color: var(--text);
  background: rgba(255, 255, 255, 0.08);
  border: 1px solid var(--line);
  border-radius: 18px;
  padding: 13px 14px;
  outline: none;
}

textarea {
  resize: vertical;
  line-height: 1.45;
}

textarea::placeholder,
input::placeholder {
  color: rgba(247, 241, 255, 0.42);
}

textarea:focus,
input:focus,
select:focus {
  border-color: rgba(183, 147, 255, 0.85);
  box-shadow: 0 0 0 4px rgba(183, 147, 255, 0.12);
}

label span,
label {
  display: block;
}

label span {
  font-weight: 800;
  margin-bottom: 9px;
  color: #fff;
}

.ambient {
  position: fixed;
  width: 360px;
  height: 360px;
  border-radius: 999px;
  filter: blur(50px);
  opacity: 0.32;
  pointer-events: none;
}

.ambient-one {
  background: var(--accent);
  top: -120px;
  right: 12%;
}

.ambient-two {
  background: var(--accent-2);
  bottom: -140px;
  left: 15%;
}

.layout {
  width: min(1440px, calc(100% - 32px));
  margin: 0 auto;
  padding: 28px 0;
  display: grid;
  grid-template-columns: 360px 1fr;
  gap: 24px;
  min-height: 100vh;
}

.sidebar,
.main-panel,
.composer,
.chat-section {
  border: 1px solid var(--line);
  background: var(--panel);
  backdrop-filter: blur(22px);
  box-shadow: var(--shadow);
}

.sidebar {
  border-radius: 34px;
  padding: 20px;
  height: calc(100vh - 56px);
  position: sticky;
  top: 28px;
  overflow: auto;
}

.main-panel {
  border-radius: 34px;
  padding: 24px;
  display: grid;
  gap: 18px;
}

.brand {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 22px;
}

.brand-mark {
  width: 48px;
  height: 48px;
  border-radius: 18px;
  display: grid;
  place-items: center;
  font-weight: 950;
  color: #130f1d;
  background: linear-gradient(135deg, var(--accent), var(--accent-2));
}

.brand p,
.brand span {
  margin: 0;
}

.brand p {
  font-weight: 950;
}

.brand span,
small,
.subtitle,
.disclaimer,
.history-meta,
.pattern-item p,
.chat-output {
  color: var(--muted);
}

.profile-card,
.insight-card,
.history-card {
  border: 1px solid var(--line);
  border-radius: 26px;
  padding: 16px;
  background: rgba(255, 255, 255, 0.055);
  margin-bottom: 16px;
}

.profile-card label {
  font-weight: 800;
  margin-bottom: 8px;
}

.profile-card small {
  display: block;
  margin-top: 8px;
  line-height: 1.4;
}

.section-title,
.chat-header,
.actions,
.hero {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 16px;
}

.section-title span {
  font-weight: 950;
}

.mini-button {
  border: 1px solid var(--line);
  background: rgba(255, 255, 255, 0.08);
  color: var(--text);
  border-radius: 999px;
  padding: 7px 10px;
  font-size: 0.82rem;
  font-weight: 800;
}

.danger-text {
  color: var(--danger);
}

.hero {
  padding: 10px 4px 4px;
}

.eyebrow {
  color: var(--accent-2);
  text-transform: uppercase;
  letter-spacing: 0.14em;
  font-size: 0.78rem;
  font-weight: 950;
  margin: 0 0 8px;
}

h1,
h2,
h3,
p {
  margin-top: 0;
}

h1 {
  font-size: clamp(2.7rem, 7vw, 6.4rem);
  line-height: 0.86;
  letter-spacing: -0.08em;
  margin-bottom: 20px;
}

h2 {
  margin-bottom: 0;
  letter-spacing: -0.04em;
}

.subtitle {
  max-width: 820px;
  line-height: 1.65;
  font-size: 1.04rem;
}

.hero-badge,
.status-pill {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  white-space: nowrap;
  border: 1px solid var(--line);
  background: rgba(255, 255, 255, 0.08);
  border-radius: 999px;
  padding: 12px 14px;
  color: var(--muted);
  font-weight: 800;
}

.pulse {
  width: 10px;
  height: 10px;
  background: var(--ok);
  border-radius: 999px;
  box-shadow: 0 0 0 8px rgba(139, 242, 176, 0.12);
}

.composer,
.chat-section {
  border-radius: 30px;
  padding: 22px;
}

.composer-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 16px;
}

.wide {
  grid-column: 1 / -1;
}

.primary-button,
.secondary-button {
  border: 0;
  border-radius: 999px;
  padding: 14px 18px;
  font-weight: 950;
}

.primary-button {
  color: #130f1d;
  background: linear-gradient(135deg, var(--accent), var(--accent-2));
}

.secondary-button {
  color: var(--text);
  background: rgba(255, 255, 255, 0.10);
  border: 1px solid var(--line);
}

.disclaimer {
  margin: 12px 0 0;
  font-size: 0.9rem;
}

.chat-output {
  min-height: 440px;
  max-height: 640px;
  overflow: auto;
  border: 1px solid var(--line);
  background: rgba(0, 0, 0, 0.16);
  border-radius: 24px;
  padding: 20px;
  line-height: 1.65;
  margin-top: 18px;
}

.chat-output h3 {
  color: #fff;
  margin-bottom: 8px;
  padding-top: 6px;
}

.chat-output p,
.chat-output li {
  color: var(--muted);
}

.chat-output strong {
  color: #fff;
}

.chat-message {
  animation: fadeIn 0.25s ease both;
}

.empty-state {
  min-height: 360px;
  display: grid;
  place-content: center;
  text-align: center;
  color: var(--faint);
}

.empty-state span {
  font-size: 3rem;
}

.patterns-panel,
.history-list {
  display: grid;
  gap: 10px;
  margin-top: 12px;
}

.pattern-item,
.history-item {
  border: 1px solid var(--line);
  border-radius: 18px;
  padding: 12px;
  background: rgba(255, 255, 255, 0.06);
}

.pattern-item strong,
.history-item strong {
  display: block;
  margin-bottom: 5px;
}

.pattern-meter {
  height: 8px;
  overflow: hidden;
  background: rgba(255, 255, 255, 0.08);
  border-radius: 999px;
  margin-top: 8px;
}

.pattern-meter span {
  display: block;
  height: 100%;
  background: linear-gradient(90deg, var(--accent), var(--accent-2));
  border-radius: inherit;
}

.history-item {
  display: flex;
  gap: 10px;
  justify-content: space-between;
  align-items: start;
}

.history-meta {
  margin: 0;
  font-size: 0.78rem;
}

.empty-small {
  color: var(--faint);
  margin: 0;
  line-height: 1.5;
}

.status-pill.loading {
  color: #130f1d;
  background: linear-gradient(135deg, var(--accent), var(--accent-2));
}

.status-pill.error {
  color: #2d0f0f;
  background: #ffb6b6;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(4px);
  }

  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@media (max-width: 1050px) {
  .layout {
    grid-template-columns: 1fr;
  }

  .sidebar {
    height: auto;
    position: static;
  }
}

@media (max-width: 720px) {
  .layout {
    width: min(100% - 20px, 1440px);
    padding: 10px 0;
  }

  .main-panel,
  .sidebar {
    border-radius: 24px;
    padding: 16px;
  }

  .hero,
  .section-title,
  .chat-header,
  .thought-map-header,
  .actions {
    align-items: stretch;
    flex-direction: column;
  }

  .composer-grid {
    grid-template-columns: 1fr;
  }

  .hero-badge,
  .primary-button,
  .secondary-button {
    width: 100%;
    justify-content: center;
  }

  .chat-output {
    min-height: 340px;
  }

  .map-confidence {
    align-items: flex-start;
    flex-direction: column;
  }

  .map-flow {
    grid-template-columns: 1fr;
  }

  .map-arrow {
    transform: rotate(90deg);
  }
}

@media (max-width: 1180px) {
  .map-flow {
    grid-template-columns: 1fr;
  }

  .map-arrow {
    transform: rotate(90deg);
  }
}

.patterns-note {
  color: var(--faint);
  font-size: 0.84rem;
  line-height: 1.45;
  margin: 4px 0 2px;
}


.thought-map-section {
  border: 1px solid var(--line);
  background: var(--panel);
  backdrop-filter: blur(22px);
  box-shadow: var(--shadow);
  border-radius: 30px;
  padding: 22px;
}

.thought-map-header {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  gap: 16px;
  margin-bottom: 18px;
}

.map-subtitle {
  margin: 8px 0 0;
  color: var(--muted);
  line-height: 1.55;
  max-width: 760px;
}

.compact-button {
  padding: 11px 14px;
  white-space: nowrap;
}

.thought-map-panel {
  border: 1px solid var(--line);
  border-radius: 24px;
  background: rgba(0, 0, 0, 0.14);
  padding: 18px;
  overflow: auto;
}

.compact-empty {
  min-height: 160px;
}

.map-confidence {
  display: flex;
  justify-content: space-between;
  gap: 12px;
  align-items: center;
  border: 1px solid var(--line);
  background: rgba(255, 255, 255, 0.07);
  border-radius: 18px;
  padding: 12px 14px;
  margin-bottom: 14px;
}

.map-confidence span {
  font-weight: 950;
  color: #fff;
}

.map-confidence small {
  color: var(--faint);
}

.map-flow {
  display: grid;
  grid-template-columns: minmax(170px, 1fr) auto minmax(170px, 1fr) auto minmax(150px, 0.85fr) auto minmax(150px, 0.85fr) auto minmax(220px, 1.15fr);
  gap: 10px;
  align-items: stretch;
}

.map-node {
  position: relative;
  border: 1px solid var(--line);
  border-radius: 22px;
  padding: 16px;
  background: rgba(255, 255, 255, 0.075);
  min-height: 170px;
}

.map-node h3 {
  font-size: 0.95rem;
  margin: 8px 0 10px;
}

.map-value {
  color: #fff;
  font-weight: 850;
  line-height: 1.45;
  margin-bottom: 10px;
}

.map-node small {
  color: var(--faint);
  line-height: 1.4;
}

.map-step {
  width: 30px;
  height: 30px;
  border-radius: 999px;
  display: grid;
  place-items: center;
  background: linear-gradient(135deg, var(--accent), var(--accent-2));
  color: #130f1d;
  font-weight: 950;
}

.map-node-alternative {
  background: linear-gradient(135deg, rgba(183, 147, 255, 0.16), rgba(126, 231, 214, 0.12));
}

.map-arrow {
  display: grid;
  place-items: center;
  color: var(--accent-2);
  font-size: 1.4rem;
  font-weight: 950;
}



/* Corrección del desplegable de emoción:
   en algunos navegadores el menú se abría con fondo claro y texto blanco. */
select option,
select optgroup {
  color: #1b1728;
  background: #ffffff;
}

select option:checked {
  color: #1b1728;
  background: #ece4ff;
}


/* v5: selectors de modo y tono */
.composer-grid select {
  min-height: 48px;
}

.chat-output h3:first-child {
  padding-top: 0;
}

.chat-output p {
  max-width: 78ch;
}


/* v6: diseño simplificado y conversación libre */
.help-card,
.simple-summary-section,
.feelings-chat-section {
  border: 1px solid var(--line);
  background: var(--panel);
  backdrop-filter: blur(22px);
  box-shadow: var(--shadow);
}

.help-card {
  border-radius: 26px;
  padding: 16px;
  margin-bottom: 16px;
  background: rgba(126, 231, 214, 0.08);
}

.help-intro {
  color: var(--muted);
  font-size: 0.9rem;
  line-height: 1.45;
  margin: 8px 0 12px;
}

.help-list {
  display: grid;
  gap: 8px;
}

.help-list a {
  text-decoration: none;
  color: var(--text);
  border: 1px solid var(--line);
  border-radius: 16px;
  padding: 10px 12px;
  display: grid;
  gap: 2px;
  background: rgba(255, 255, 255, 0.06);
}

.help-list a strong {
  font-size: 0.98rem;
}

.help-list a span {
  color: var(--muted);
  font-size: 0.82rem;
}

.simple-summary-section,
.feelings-chat-section {
  border-radius: 30px;
  padding: 22px;
}

.simple-summary-header {
  display: flex;
  justify-content: space-between;
  gap: 16px;
  align-items: flex-start;
  margin-bottom: 16px;
}

.simple-summary-panel {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 14px;
}

.simple-summary-card {
  border: 1px solid var(--line);
  border-radius: 22px;
  padding: 16px;
  background: rgba(255, 255, 255, 0.07);
  min-height: 132px;
}

.simple-summary-card h3 {
  margin-bottom: 8px;
}

.simple-summary-card p {
  color: var(--muted);
  line-height: 1.55;
  margin-bottom: 0;
}

.simple-summary-card.calming {
  background: linear-gradient(135deg, rgba(183, 147, 255, 0.12), rgba(126, 231, 214, 0.10));
}

.summary-pill {
  display: inline-flex;
  width: fit-content;
  border: 1px solid var(--line);
  border-radius: 999px;
  padding: 5px 9px;
  color: var(--accent-2);
  font-weight: 900;
  font-size: 0.78rem;
  margin-bottom: 10px;
}

.feelings-messages {
  min-height: 260px;
  max-height: 460px;
  overflow: auto;
  border: 1px solid var(--line);
  border-radius: 24px;
  padding: 16px;
  background: rgba(0, 0, 0, 0.14);
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.feelings-empty {
  min-height: 210px;
  display: grid;
  place-content: center;
  text-align: center;
  color: var(--faint);
}

.feelings-empty span {
  font-size: 2.4rem;
}

.feelings-input-row {
  display: grid;
  grid-template-columns: 1fr auto;
  gap: 12px;
  margin-top: 14px;
  align-items: end;
}

.feelings-bubble {
  max-width: min(78ch, 92%);
  border: 1px solid var(--line);
  border-radius: 20px;
  padding: 12px 14px;
  line-height: 1.55;
}

.feelings-bubble p {
  margin: 0;
}

.user-bubble {
  align-self: flex-end;
  background: rgba(183, 147, 255, 0.18);
}

.assistant-bubble {
  align-self: flex-start;
  background: rgba(255, 255, 255, 0.07);
}

.assistant-bubble h3 {
  margin-top: 0;
}

@media (max-width: 820px) {
  .simple-summary-header,
  .feelings-input-row {
    grid-template-columns: 1fr;
    flex-direction: column;
  }

  .simple-summary-panel {
    grid-template-columns: 1fr;
  }
}
