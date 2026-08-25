# kathleenbu.github.io
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>TMUN Companion</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Newsreader:ital,wght@0,400;0,500;1,400&display=swap" rel="stylesheet">
<style>
  :root {
    --page: #EAF3F7;
    --surface: #FFFFFF;
    --surface-alt: #DCEAF0;
    --deep: #1F4C63;
    --border: #C7DCE4;
    --border-strong: #9FC4D3;
    --text: #132C38;
    --text-secondary: #4C6A78;
    --text-muted: #84A0AA;
    --danger-bg: #F8E4E1;
    --danger-text: #9A3324;
    --warning-bg: #F7ECD8;
    --warning-text: #8A5A00;
    --font-serif: 'Newsreader', Georgia, 'Times New Roman', serif;
    --font-sans: -apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif;
  }
  * { box-sizing: border-box; }
  body {
    margin: 0;
    background: #F3F6F8;
    font-family: var(--font-sans);
    color: var(--text);
    display: flex;
    justify-content: center;
    padding: 24px 12px;
  }
  #app {
    max-width: 480px;
    width: 100%;
    background: var(--page);
    border-radius: 14px;
    padding: 16px;
  }
  .banner {
    background: var(--warning-bg);
    color: var(--warning-text);
    font-size: 12px;
    padding: 8px 12px;
    border-radius: 6px;
    margin-bottom: 12px;
  }
  .masthead {
    background: var(--deep);
    border-radius: 10px;
    padding: 18px 20px 14px;
    margin-bottom: 20px;
  }
  .masthead h1 {
    margin: 0 0 16px;
    font-family: var(--font-serif);
    font-size: 19px;
    font-weight: 500;
    color: #fff;
    letter-spacing: 0.3px;
  }
  .masthead nav { display: flex; gap: 28px; }
  .masthead nav button {
    background: transparent;
    border: none;
    border-bottom: 1px solid transparent;
    padding: 0 0 8px;
    font-family: var(--font-serif);
    font-size: 15px;
    color: #fff;
    opacity: 0.55;
    cursor: pointer;
  }
  .masthead nav button.active { opacity: 1; border-bottom-color: #fff; }

  .tabs {
    display: flex;
    gap: 18px;
    margin-bottom: 18px;
    border-bottom: 1px solid var(--border);
    flex-wrap: wrap;
  }
  .tabs button {
    background: transparent;
    border: none;
    padding: 0 0 10px;
    margin-bottom: -1px;
    font-size: 13px;
    font-weight: 500;
    color: var(--text-secondary);
    border-bottom: 2px solid transparent;
    cursor: pointer;
  }
  .tabs button.active { color: var(--deep); border-bottom-color: var(--deep); }

  .room-card {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: var(--deep);
    border-radius: 8px;
    padding: 14px 16px;
    margin-bottom: 8px;
  }
  .room-card .name { margin: 0; font-family: var(--font-serif); font-weight: 500; font-size: 16px; color: #fff; }
  .room-card .floor { margin: 3px 0 0; font-size: 12px; color: #9FC4D3; }
  .room-card .room-tag {
    font-size: 12px; color: #fff; font-weight: 500; text-align: right;
    border: 1px solid rgba(255,255,255,0.35); border-radius: 4px; padding: 3px 8px;
    white-space: nowrap; margin-left: 12px;
  }

  .venue-toggle { display: flex; gap: 20px; border-bottom: 1px solid var(--border); margin-bottom: 10px; }
  .venue-toggle button {
    background: transparent; border: none; padding: 0 0 10px; margin-bottom: -1px;
    font-size: 13px; font-weight: 500; color: var(--text-secondary); border-bottom: 2px solid transparent; cursor: pointer;
  }
  .venue-toggle button.active { color: var(--deep); border-bottom-color: var(--deep); }
  .venue-img { width: 100%; border-radius: 8px; border: 1px solid var(--border); margin-top: 4px; display: block; }
  .venue-caption { font-size: 12px; color: var(--text-muted); margin: 8px 0 0; }

  .day-block { margin-bottom: 22px; }
  .day-block h3 {
    display: inline-block; margin: 0 0 10px; font-family: var(--font-serif); font-size: 15px; font-weight: 500;
    color: var(--deep); padding-bottom: 6px; border-bottom: 1px solid var(--deep);
  }
  .sched-row { display: flex; gap: 12px; padding: 10px 0; border-top: 1px solid var(--border); }
  .sched-row:first-child { border-top: none; }
  .sched-row .time { font-size: 13px; color: var(--text-secondary); min-width: 76px; }
  .sched-row .label { font-size: 14px; color: var(--text); }

  .card {
    background: var(--surface); border: 1px solid var(--border); border-radius: 8px; padding: 12px 16px; margin-bottom: 8px;
  }
  .card h4 { margin: 0; font-family: var(--font-serif); font-size: 15px; font-weight: 500; color: var(--text); }
  .card .meta { font-size: 12px; color: var(--text-muted); }
  .card p.message { margin: 4px 0 0; font-size: 14px; color: var(--text); }

  form { display: flex; flex-direction: column; gap: 12px; }
  .field-note { font-size: 13px; color: var(--text-secondary); margin: 0; }
  input, select, textarea {
    border: 1px solid var(--border); border-radius: 6px; padding: 9px 10px; font-size: 14px;
    font-family: var(--font-sans); color: var(--text); background: #fff; outline: none; width: 100%;
  }
  textarea { font-family: inherit; }
  .btn-primary {
    padding: 10px 0; border-radius: 6px; border: 1px solid var(--deep); background: var(--deep); color: #fff;
    font-size: 14px; font-weight: 500; cursor: pointer;
  }
  .btn-primary:disabled { opacity: 0.7; cursor: default; }
  .btn-secondary {
    font-size: 12px; padding: 5px 12px; border-radius: 6px; border: 1px solid var(--border-strong);
    background: transparent; color: var(--deep); cursor: pointer;
  }
  .btn-secondary.danger { color: var(--danger-text); border-color: var(--danger-text); }
  .error-text { font-size: 13px; color: var(--danger-text); }

  .pin-form { display: flex; flex-direction: column; gap: 12px; max-width: 260px; margin: 40px auto 0; text-align: center; }
  .pin-form p { font-size: 14px; color: var(--text-secondary); margin: 0 0 4px; font-family: var(--font-serif); }
  .pin-form input { text-align: center; font-size: 16px; letter-spacing: 2px; }

  .concern-header, .announce-header { display: flex; justify-content: space-between; align-items: baseline; margin-bottom: 4px; }
  .concern-header h4, .announce-header h4 { font-size: 15px; font-weight: 500; margin: 0; font-family: var(--font-serif); color: var(--text); }
  .section-note { font-size: 13px; color: var(--text-secondary); margin: 0 0 12px; }

  .badge { font-size: 12px; font-weight: 500; padding: 2px 10px; border-radius: 999px; }
  .badge-high { background: var(--danger-bg); color: var(--danger-text); }
  .badge-medium { background: var(--warning-bg); color: var(--warning-text); }
  .badge-low { background: var(--surface-alt); color: var(--text-secondary); }

  .concern-top { display: flex; justify-content: space-between; align-items: center; margin-bottom: 6px; }
  .concern-cat { margin: 0 0 4px; font-size: 14px; font-weight: 500; color: var(--text); }
  .concern-desc { margin: 0 0 6px; font-size: 14px; color: var(--text); }
  .concern-meta { margin: 0 0 8px; font-size: 12px; color: var(--text-muted); }

  .recent-list { margin-top: 16px; display: flex; flex-direction: column; gap: 6px; }
  .recent-list .label { font-size: 12px; color: var(--text-muted); margin: 0; }
  .recent-item { font-size: 13px; color: var(--text-secondary); }
  .recent-item strong { color: var(--text); }
</style>
</head>
<body>
<div id="app"></div>

<script>
// ---- data --------------------------------------------------------------
const STAFF_PIN = "2027"; // change before the conference

const ROOMS = [
  { code: "DISEC", name: "Disarmament and International Security Committee", floor: "2nd Floor", room: "Civic Ballroom South" },
  { code: "COPUOS", name: "Committee on the Peaceful Uses of Outer Space", floor: "Mezzanine", room: "Chestnut West" },
  { code: "WFP", name: "World Food Programme", floor: "Mezzanine", room: "Willow Centre" },
  { code: "ITU", name: "International Telecommunication Union", floor: "Mezzanine", room: "Chestnut East" },
  { code: "ICAO", name: "International Civil Aviation Organization Board of Directors", floor: "Mezzanine", room: "York" },
  { code: "LORAX", name: "The Council of the Trees: A Lorax Specialized Agency", floor: "4th Floor", room: "Rosedale" },
  { code: "KOWLOON", name: "The City of Darkness: Kowloon Walled City", floor: "Mezzanine", room: "Norfolk" },
  { code: "GERMANY", name: "1870: Blood and Iron, The Unification of Germany", floor: "Mezzanine", room: "Cedar" },
  { code: "F1", name: "Lights Out and Away We Go: Formula One 2021 Season", floor: "Mezzanine", room: "Willow West" },
  { code: "CATH", name: "The Councils of Faith and Reformation (Catholics)", floor: "Mezzanine", room: "Maple East" },
  { code: "REFORM", name: "The Councils of Faith and Reformation (Reformers)", floor: "Mezzanine", room: "Maple West" },
  { code: "JFK", name: "From Camelot to Capitol Hill: The Assassination of John F. Kennedy", floor: "Mezzanine", room: "Peel" },
  { code: "JAPAN", name: "Eclipse of Amaterasu: Portuguese Invasion of Japan", floor: "4th Floor", room: "Danforth" },
  { code: "BLOODBORNE", name: "Bloodborne: Fear the Old Blood", floor: "Mezzanine", room: "Willow East" },
  { code: "ASSASSIN", name: "Assassination Classroom: Mandate to Kill", floor: "4th Floor", room: "Leaside" },
  { code: "HELLDIVERS", name: "Helldivers: Heart of Democracy", floor: "4th Floor", room: "Yorkville West" },
  { code: "GREYS", name: "Grey's Anatomy: A Hospital In Crisis", floor: "4th Floor", room: "Davenport" },
  { code: "AH1", name: "Ad Hoc Committee", floor: "4th Floor", room: "Kensington" },
  { code: "REG", name: "Registration", floor: "Concourse", room: "Conference Registration" },
];

const SCHEDULE = [
  { day: "Friday — March 27, 2026", items: [
    { time: "4:15 PM", label: "Opening Ceremony (Willow Ballroom)" },
    { time: "4:45 PM", label: "Beginner's Workshop" },
    { time: "6:00 PM", label: "Committee Session I" },
    { time: "6:15 PM", label: "Chaperone Meeting (Spruce)" },
    { time: "8:00 PM", label: "Dinner" },
    { time: "11:00 PM", label: "Midnight Crisis Committee Session" },
  ]},
  { day: "Saturday — March 28, 2026", items: [
    { time: "9:00 AM", label: "Committee Session II" },
    { time: "11:00 AM", label: "Break" },
    { time: "11:15 AM", label: "Committee Session III" },
    { time: "1:15 PM", label: "Lunch" },
    { time: "2:45 PM", label: "Chaperone Meeting (Spruce)" },
    { time: "2:45 PM", label: "Committee Session IV" },
    { time: "4:45 PM", label: "Break" },
    { time: "5:00 PM", label: "Committee Session V" },
    { time: "7:00 PM", label: "Dinner" },
    { time: "8:30 PM", label: "Delegate Social (Chestnut Ballroom)" },
  ]},
  { day: "Sunday — March 29, 2026", items: [
    { time: "9:15 AM", label: "Committee Session VI" },
    { time: "11:15 AM", label: "Break" },
    { time: "11:30 AM", label: "Chaperone Meeting (Spruce)" },
    { time: "11:30 AM", label: "Committee Session VII" },
    { time: "1:00 PM", label: "Lunch" },
    { time: "2:30 PM", label: "Closing Ceremony (Willow Ballroom)" },
  ]},
];

const MEETING_ROOMS_MAP = "data:image/jpeg;base64,''' + meeting_b64 + '''";
const HOTEL_MAP = "data:image/jpeg;base64,''' + hotel_b64 + '''";

// ---- local persistence (single browser only — see note in chat) --------
function readList(key) {
  try {
    const raw = localStorage.getItem(key);
    const parsed = raw ? JSON.parse(raw) : [];
    return Array.isArray(parsed) ? parsed : [];
  } catch (e) { return []; }
}
function writeList(key, list) {
  try { localStorage.setItem(key, JSON.stringify(list)); return true; }
  catch (e) { return false; }
}

// Keyword-based triage (no network call — see note in chat about the AI
// classifier not being available in a standalone local file).
function classifyConcern(description) {
  const lower = description.toLowerCase();
  if (/unsafe|scared|hurt|harass|threat|crying|sick|emergency/.test(lower)) {
    return { urgency: "high", reason: "Flagged by keyword check." };
  }
  if (/unfair|excluded|rude|argument|ignored/.test(lower)) {
    return { urgency: "medium", reason: "Flagged by keyword check." };
  }
  return { urgency: "low", reason: "Routine logistics concern." };
}

// ---- state ---------------------------------------------------------------
const state = {
  view: "delegate",
  tab: "map",
  mapView: "meeting",
  staffUnlocked: false,
  concerns: readList("tmun_concerns"),
  notifications: readList("tmun_notifications"),
  error: "",
  notifError: "",
  pinError: "",
};

function esc(s) {
  return String(s).replace(/[&<>"']/g, (c) => ({ "&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;" }[c]));
}

function sortedConcerns() {
  const order = { high: 0, medium: 1, low: 2 };
  return [...state.concerns].sort((a, b) => {
    if (a.resolved !== b.resolved) return a.resolved ? 1 : -1;
    return order[a.urgency] - order[b.urgency];
  });
}

function badgeClass(u) { return u === "high" ? "badge-high" : u === "medium" ? "badge-medium" : "badge-low"; }
function badgeLabel(u) { return u === "high" ? "High priority" : u === "medium" ? "Medium priority" : "Low priority"; }

// ---- render ---------------------------------------------------------------
function render() {
  const app = document.getElementById("app");
  const notifCount = state.notifications.length ? ` (${state.notifications.length})` : "";

  let html = "";

  html += `<div class="masthead">
    <h1>TMUN Companion</h1>
    <nav>
      <button data-act="view" data-val="delegate" class="${state.view === "delegate" ? "active" : ""}">Delegate View</button>
      <button data-act="view" data-val="staff" class="${state.view === "staff" ? "active" : ""}">Staff View</button>
    </nav>
  </div>`;

  if (state.view === "delegate") {
    html += `<div class="tabs">
      <button data-act="tab" data-val="map" class="${state.tab==="map"?"active":""}">Rooms</button>
      <button data-act="tab" data-val="venue" class="${state.tab==="venue"?"active":""}">Venue Map</button>
      <button data-act="tab" data-val="schedule" class="${state.tab==="schedule"?"active":""}">Schedule</button>
      <button data-act="tab" data-val="notices" class="${state.tab==="notices"?"active":""}">Announcements${notifCount}</button>
      <button data-act="tab" data-val="concern" class="${state.tab==="concern"?"active":""}">Get help</button>
    </div>`;

    if (state.tab === "map") {
      html += ROOMS.map(r => `
        <div class="room-card">
          <div>
            <p class="name">${esc(r.name)}</p>
            <p class="floor">${esc(r.floor)}</p>
          </div>
          <span class="room-tag">${esc(r.room)}</span>
        </div>`).join("");
    }

    if (state.tab === "venue") {
      html += `<div class="venue-toggle">
        <button data-act="mapview" data-val="meeting" class="${state.mapView==="meeting"?"active":""}">Meeting Room Floors</button>
        <button data-act="mapview" data-val="hotel" class="${state.mapView==="hotel"?"active":""}">Lobby &amp; Concourse</button>
      </div>
      <img class="venue-img" src="${state.mapView === "meeting" ? MEETING_ROOMS_MAP : HOTEL_MAP}" alt="Venue map" />
      <p class="venue-caption">Sheraton Centre Toronto Hotel. Pinch to zoom for room labels.</p>`;
    }

    if (state.tab === "schedule") {
      html += SCHEDULE.map(d => `
        <div class="day-block">
          <h3>${esc(d.day)}</h3>
          ${d.items.map(s => `<div class="sched-row"><span class="time">${esc(s.time)}</span><span class="label">${esc(s.label)}</span></div>`).join("")}
        </div>`).join("");
    }

    if (state.tab === "notices") {
      if (state.notifications.length === 0) {
        html += `<p style="font-size:14px;color:var(--text-muted);">No announcements yet.</p>`;
      } else {
        html += state.notifications.map(n => `
          <div class="card">
            <div style="display:flex;justify-content:space-between;align-items:baseline;">
              <h4>${esc(n.title)}</h4>
              <span class="meta">${esc(n.time)}</span>
            </div>
            <p class="message">${esc(n.message)}</p>
          </div>`).join("");
      }
    }

    if (state.tab === "concern") {
      html += `<form id="concern-form">
        <p class="field-note">Something wrong, confusing, or upsetting? Tell us and it goes straight to Staff.</p>
        <input id="c-name" placeholder="Your name (optional)" />
        <input id="c-committee" placeholder="Committee (optional)" />
        <select id="c-category">
          <option>Logistics</option><option>Interpersonal</option><option>Safety</option><option>Other</option>
        </select>
        <textarea id="c-description" placeholder="What happened?" rows="4"></textarea>
        ${state.error ? `<span class="error-text">${esc(state.error)}</span>` : ""}
        <button type="submit" class="btn-primary">Send to Staff</button>
      </form>`;
    }
  }

  if (state.view === "staff" && !state.staffUnlocked) {
    html += `<form id="pin-form" class="pin-form">
      <p>Enter the Staff PIN</p>
      <input id="pin-input" type="password" inputmode="numeric" placeholder="PIN" autofocus />
      ${state.pinError ? `<span class="error-text">${esc(state.pinError)}</span>` : ""}
      <button type="submit" class="btn-primary">Unlock</button>
    </form>`;
  }

  if (state.view === "staff" && state.staffUnlocked) {
    const sc = sortedConcerns();
    html += `<div class="concern-header">
        <h4>Concerns</h4>
        <div style="display:flex;gap:8px;">
          <button id="refresh-concerns" class="btn-secondary">Refresh</button>
          ${state.concerns.length > 0 ? `<button id="clear-concerns" class="btn-secondary danger">Clear all</button>` : ""}
        </div>
      </div>
      <p class="section-note">Sorted automatically by urgency. Resolved items drop to the bottom.</p>`;

    if (sc.length === 0) {
      html += `<p style="font-size:14px;color:var(--text-muted);">No concerns submitted yet.</p>`;
    } else {
      html += sc.map(c => `
        <div class="card" style="opacity:${c.resolved ? 0.55 : 1};">
          <div class="concern-top">
            <span class="badge ${badgeClass(c.urgency)}">${badgeLabel(c.urgency)}</span>
            <span class="meta">${esc(c.time)}</span>
          </div>
          <p class="concern-cat">${esc(c.category)}${c.committee ? " — " + esc(c.committee) : ""}</p>
          <p class="concern-desc">${esc(c.description)}</p>
          <p class="concern-meta">${c.name ? esc(c.name) : "Anonymous"} · ${esc(c.reason)}</p>
          <button class="btn-secondary toggle-resolved" data-id="${esc(c.id)}">${c.resolved ? "Mark unresolved" : "Mark resolved"}</button>
        </div>`).join("");
    }

    html += `<div style="margin-top:24px;">
      <div class="announce-header">
        <h4>Send an announcement</h4>
        ${state.notifications.length > 0 ? `<button id="clear-notifications" class="btn-secondary danger">Clear all</button>` : ""}
      </div>
      <p class="section-note">Posts instantly to every delegate's Announcements tab.</p>
      <form id="notif-form">
        <input id="n-title" placeholder="Title (e.g. Committee session II delayed)" />
        <textarea id="n-message" placeholder="Message" rows="3"></textarea>
        ${state.notifError ? `<span class="error-text">${esc(state.notifError)}</span>` : ""}
        <button type="submit" class="btn-primary">Post announcement</button>
      </form>`;

    if (state.notifications.length > 0) {
      html += `<div class="recent-list"><p class="label">Recent announcements</p>
        ${state.notifications.slice(0, 3).map(n => `<div class="recent-item"><strong>${esc(n.title)}</strong> · ${esc(n.time)}</div>`).join("")}
      </div>`;
    }
    html += `</div>`;
  }

  app.innerHTML = html;
  bindEvents();
}

function bindEvents() {
  document.querySelectorAll('[data-act="view"]').forEach(b => b.onclick = () => { state.view = b.dataset.val; render(); });
  document.querySelectorAll('[data-act="tab"]').forEach(b => b.onclick = () => { state.tab = b.dataset.val; render(); });
  document.querySelectorAll('[data-act="mapview"]').forEach(b => b.onclick = () => { state.mapView = b.dataset.val; render(); });

  const cf = document.getElementById("concern-form");
  if (cf) cf.onsubmit = (e) => {
    e.preventDefault();
    const description = document.getElementById("c-description").value.trim();
    if (!description) { state.error = "Describe what happened before submitting."; render(); return; }
    const category = document.getElementById("c-category").value;
    const result = classifyConcern(description);
    const entry = {
      id: Date.now() + "-" + Math.random().toString(36).slice(2, 7),
      name: document.getElementById("c-name").value,
      committee: document.getElementById("c-committee").value,
      category, description,
      urgency: result.urgency, reason: result.reason,
      time: new Date().toLocaleTimeString([], { hour: "2-digit", minute: "2-digit" }),
      resolved: false,
    };
    state.concerns = [entry, ...state.concerns];
    writeList("tmun_concerns", state.concerns);
    state.error = "";
    render();
  };

  const pf = document.getElementById("pin-form");
  if (pf) pf.onsubmit = (e) => {
    e.preventDefault();
    const val = document.getElementById("pin-input").value;
    if (val === STAFF_PIN) { state.staffUnlocked = true; state.pinError = ""; }
    else { state.pinError = "Incorrect PIN."; }
    render();
  };

  const nf = document.getElementById("notif-form");
  if (nf) nf.onsubmit = (e) => {
    e.preventDefault();
    const title = document.getElementById("n-title").value.trim();
    const message = document.getElementById("n-message").value.trim();
    if (!title || !message) { state.notifError = "Add a title and message before sending."; render(); return; }
    const entry = { id: Date.now() + "-" + Math.random().toString(36).slice(2, 7), title, message,
      time: new Date().toLocaleTimeString([], { hour: "2-digit", minute: "2-digit" }) };
    state.notifications = [entry, ...state.notifications];
    writeList("tmun_notifications", state.notifications);
    state.notifError = "";
    render();
  };

  const rc = document.getElementById("refresh-concerns");
  if (rc) rc.onclick = () => { state.concerns = readList("tmun_concerns"); render(); };

  const cc = document.getElementById("clear-concerns");
  if (cc) cc.onclick = () => {
    if (!confirm("Clear all concerns? This can't be undone.")) return;
    state.concerns = []; writeList("tmun_concerns", []); render();
  };

  const cn = document.getElementById("clear-notifications");
  if (cn) cn.onclick = () => {
    if (!confirm("Clear all announcements? This can't be undone.")) return;
    state.notifications = []; writeList("tmun_notifications", []); render();
  };

  document.querySelectorAll(".toggle-resolved").forEach(btn => {
    btn.onclick = () => {
      const id = btn.dataset.id;
      state.concerns = state.concerns.map(c => c.id === id ? { ...c, resolved: !c.resolved } : c);
      writeList("tmun_concerns", state.concerns);
      render();
    };
  });
}

render();
</script>
</body>
</html>
