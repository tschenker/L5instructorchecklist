[index.html](https://github.com/user-attachments/files/27782641/index.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>L5 Instructor Self-Assessment Checklist</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Sans:wght@300;400;500;600&display=swap');

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --navy:   #1a3556;
    --blue:   #2563a8;
    --mid:    #4a90c4;
    --light:  #ddeef9;
    --pale:   #f2f8fd;
    --white:  #ffffff;
    --ink:    #1c2b3a;
    --muted:  #5a7490;
    --border: #c5ddf0;
    --never:        #e8f0fe;
    --rarely:       #d0e8fd;
    --sometimes:    #a8d4f5;
    --often:        #5aabe0;
    --never-text:       #3a5080;
    --rarely-text:      #2a5f8a;
    --sometimes-text:   #1a4f78;
    --often-text:       #ffffff;
  }

  body {
    font-family: 'DM Sans', sans-serif;
    background: #eef5fb;
    color: var(--ink);
    min-height: 100vh;
    padding: 2rem 1rem 4rem;
  }

  .wrapper {
    max-width: 900px;
    margin: 0 auto;
  }

  /* ── Header ── */
  .header {
    background: var(--navy);
    color: var(--white);
    border-radius: 16px 16px 0 0;
    padding: 2.5rem 2.5rem 2rem;
    position: relative;
    overflow: hidden;
  }
  .header::after {
    content: '';
    position: absolute;
    right: -40px; top: -60px;
    width: 280px; height: 280px;
    border-radius: 50%;
    background: rgba(255,255,255,0.04);
    pointer-events: none;
  }
  .header::before {
    content: '';
    position: absolute;
    right: 60px; bottom: -80px;
    width: 180px; height: 180px;
    border-radius: 50%;
    background: rgba(255,255,255,0.03);
    pointer-events: none;
  }

  .badge {
    display: inline-block;
    background: rgba(255,255,255,0.12);
    border: 1px solid rgba(255,255,255,0.2);
    color: #a8d4f5;
    font-family: 'DM Sans', sans-serif;
    font-size: 0.72rem;
    font-weight: 600;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    padding: 0.25rem 0.75rem;
    border-radius: 100px;
    margin-bottom: 1rem;
  }

  .header h1 {
    font-family: 'DM Serif Display', serif;
    font-size: 2rem;
    font-weight: 400;
    line-height: 1.2;
    margin-bottom: 0.35rem;
  }

  .header .subtitle {
    font-size: 0.95rem;
    color: #a8d4f5;
    font-weight: 300;
    letter-spacing: 0.02em;
  }

  /* ── Meta fields ── */
  .meta {
    background: var(--white);
    border-left: 1px solid var(--border);
    border-right: 1px solid var(--border);
    padding: 1.25rem 2.5rem;
    display: flex;
    gap: 2rem;
    flex-wrap: wrap;
  }
  .meta-field {
    display: flex;
    flex-direction: column;
    gap: 0.25rem;
    flex: 1;
    min-width: 160px;
  }
  .meta-field label {
    font-size: 0.7rem;
    font-weight: 600;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--muted);
  }
  .meta-field input {
    border: none;
    border-bottom: 1.5px solid var(--border);
    padding: 0.25rem 0;
    font-family: 'DM Sans', sans-serif;
    font-size: 0.9rem;
    color: var(--ink);
    background: transparent;
    outline: none;
    transition: border-color 0.2s;
    width: 100%;
  }
  .meta-field input:focus { border-color: var(--blue); }

  /* ── Intro text ── */
  .intro {
    background: var(--pale);
    border-left: 1px solid var(--border);
    border-right: 1px solid var(--border);
    padding: 1rem 2.5rem;
    font-size: 0.85rem;
    color: var(--muted);
    line-height: 1.6;
  }

  /* ── Table ── */
  .table-wrap {
    background: var(--white);
    border: 1px solid var(--border);
    border-top: none;
    overflow-x: auto;
  }

  table {
    width: 100%;
    border-collapse: collapse;
    table-layout: fixed;
  }

  /* column sizing */
  col.c-practice { width: 52%; }
  col.c-freq     { width: 12%; }

  thead tr {
    background: var(--navy);
  }
  thead th {
    padding: 0.9rem 0.6rem;
    font-size: 0.75rem;
    font-weight: 600;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    color: var(--white);
    text-align: center;
    border: 1px solid rgba(255,255,255,0.1);
  }
  thead th.th-practice {
    text-align: left;
    padding-left: 1.5rem;
    color: #a8d4f5;
  }

  tbody tr {
    border-bottom: 1px solid var(--border);
    transition: background 0.15s;
  }
  tbody tr:nth-child(even) { background: var(--pale); }
  tbody tr:hover { background: #e6f3fb; }

  td.td-practice {
    padding: 0.85rem 0.75rem 0.85rem 1.5rem;
    font-size: 0.88rem;
    line-height: 1.5;
    color: var(--ink);
    vertical-align: middle;
  }

  td.td-freq {
    text-align: center;
    vertical-align: middle;
    padding: 0.5rem 0.25rem;
  }

  /* ── Frequency radio buttons ── */
  .freq-btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 36px;
    height: 36px;
    border-radius: 50%;
    cursor: pointer;
    border: 2px solid var(--border);
    background: var(--white);
    transition: all 0.18s ease;
    font-size: 0.7rem;
    font-weight: 600;
    color: var(--muted);
    user-select: none;
    position: relative;
  }
  .freq-btn:hover {
    border-color: var(--mid);
    background: var(--light);
    transform: scale(1.08);
  }

  /* Selected states per column */
  .row-btns input[type=radio] { display: none; }

  input[type=radio].r0:checked ~ .freq-btn.b0,
  input[type=radio].r1:checked ~ .freq-btn.b1,
  input[type=radio].r2:checked ~ .freq-btn.b2,
  input[type=radio].r3:checked ~ .freq-btn.b3,
  input[type=radio].r4:checked ~ .freq-btn.b4 {
    border-color: var(--blue);
    transform: scale(1.12);
  }

  /* we'll use JS for selected state rendering for simplicity */
  .freq-label {
    display: inline-flex;
    flex-direction: column;
    align-items: center;
    gap: 0.25rem;
    cursor: pointer;
    width: 100%;
  }
  .freq-dot {
    width: 34px;
    height: 34px;
    border-radius: 50%;
    border: 2px solid var(--border);
    background: var(--white);
    transition: all 0.18s ease;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.7rem;
    font-weight: 700;
    color: transparent;
  }
  .freq-label:hover .freq-dot {
    border-color: var(--mid);
    background: var(--light);
    transform: scale(1.1);
  }

  /* selected states */
  input[type=radio]:checked + .freq-label .freq-dot {
    color: white;
    border-color: transparent;
  }
  input.sel-0:checked + .freq-label .freq-dot { background: var(--never); color: var(--never-text); border-color: var(--never); }
  input.sel-1:checked + .freq-label .freq-dot { background: var(--rarely); color: var(--rarely-text); border-color: var(--rarely); }
  input.sel-2:checked + .freq-label .freq-dot { background: var(--sometimes); color: var(--sometimes-text); border-color: var(--sometimes); }
  input.sel-3:checked + .freq-label .freq-dot { background: var(--often); color: var(--often-text); border-color: var(--often); }

  input[type=radio] { display: none; }

  /* ── Progress bar ── */
  .progress-section {
    background: var(--white);
    border: 1px solid var(--border);
    border-top: none;
    padding: 1.25rem 2.5rem;
  }
  .progress-label {
    display: flex;
    justify-content: space-between;
    font-size: 0.78rem;
    color: var(--muted);
    font-weight: 500;
    margin-bottom: 0.5rem;
  }
  .progress-bar-bg {
    height: 6px;
    background: var(--light);
    border-radius: 100px;
    overflow: hidden;
  }
  .progress-bar-fill {
    height: 100%;
    background: linear-gradient(90deg, var(--mid), var(--consistently));
    border-radius: 100px;
    transition: width 0.4s ease;
    width: 0%;
  }
  .score-summary {
    margin-top: 0.75rem;
    font-size: 0.82rem;
    color: var(--muted);
    font-style: italic;
  }

  /* ── Reflection ── */
  .reflection {
    background: var(--pale);
    border: 1px solid var(--border);
    border-top: none;
    padding: 1.75rem 2.5rem;
  }
  .reflection h2 {
    font-family: 'DM Serif Display', serif;
    font-size: 1.25rem;
    font-weight: 400;
    color: var(--navy);
    margin-bottom: 1.25rem;
  }
  .reflection-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1.25rem;
  }
  @media (max-width: 600px) { .reflection-grid { grid-template-columns: 1fr; } }
  .reflection-field label {
    display: block;
    font-size: 0.75rem;
    font-weight: 600;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 0.5rem;
  }
  .reflection-field textarea {
    width: 100%;
    border: 1.5px solid var(--border);
    border-radius: 8px;
    padding: 0.75rem;
    font-family: 'DM Sans', sans-serif;
    font-size: 0.88rem;
    color: var(--ink);
    background: var(--white);
    resize: vertical;
    min-height: 90px;
    outline: none;
    transition: border-color 0.2s;
    line-height: 1.5;
  }
  .reflection-field textarea:focus { border-color: var(--blue); }

  /* ── Actions ── */
  .actions {
    background: var(--white);
    border: 1px solid var(--border);
    border-top: none;
    border-radius: 0 0 16px 16px;
    padding: 1.25rem 2.5rem;
    display: flex;
    gap: 0.75rem;
    flex-wrap: wrap;
  }
  .btn {
    padding: 0.6rem 1.4rem;
    border-radius: 8px;
    font-family: 'DM Sans', sans-serif;
    font-size: 0.85rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.18s;
    border: 2px solid transparent;
  }
  .btn-primary {
    background: var(--navy);
    color: var(--white);
    border-color: var(--navy);
  }
  .btn-primary:hover { background: var(--blue); border-color: var(--blue); }
  .btn-secondary {
    background: transparent;
    color: var(--navy);
    border-color: var(--border);
  }
  .btn-secondary:hover { border-color: var(--blue); color: var(--blue); }
  .btn-ghost {
    background: transparent;
    color: var(--muted);
    border-color: transparent;
    font-weight: 400;
  }
  .btn-ghost:hover { color: var(--navy); }

  /* ── Print ── */
  @media print {
    body { background: white; padding: 0; }
    .actions { display: none; }
    .header { border-radius: 0; }
    .freq-dot { print-color-adjust: exact; -webkit-print-color-adjust: exact; }
  }
</style>
</head>
<body>
<div class="wrapper">

  <!-- Header -->
  <div class="header">
    <div class="badge">Self-Assessment · Advancedness-Oriented Instruction</div>
    <h1>L5 Instructor Checklist</h1>
    <p class="subtitle">Reflect on your teaching practices over the past 2 weeks</p>
  </div>

  <!-- Meta -->
  <div class="meta">
    <div class="meta-field">
      <label>Instructor</label>
      <input type="text" id="field-instructor" placeholder="Your name" autocomplete="off">
    </div>
    <div class="meta-field">
      <label>Course</label>
      <input type="text" id="field-course" placeholder="Course number / title" autocomplete="off">
    </div>
    <div class="meta-field">
      <label>Date</label>
      <input type="text" id="field-date" placeholder="e.g. Fall 2025, Week 6" autocomplete="off">
    </div>
  </div>

  <!-- Intro -->
  <div class="intro">
    Select a frequency for each practice. Use the <strong>Reflection</strong> section below to note priorities and next steps. You can print or save this page when finished.
  </div>

  <!-- Table -->
  <div class="table-wrap">
    <table>
      <colgroup>
        <col class="c-practice">
        <col class="c-freq"><col class="c-freq"><col class="c-freq"><col class="c-freq">
      </colgroup>
      <thead>
        <tr>
          <th class="th-practice">In the past 2 weeks, I have…</th>
          <th>Never</th>
          <th>Rarely</th>
          <th>Sometimes</th>
          <th>Often</th>
        </tr>
      </thead>
      <tbody id="checklist-body"></tbody>
    </table>
  </div>

  <!-- Progress -->
  <div class="progress-section">
    <div class="progress-label">
      <span>Responses completed</span>
      <span id="progress-text">0 of 16</span>
    </div>
    <div class="progress-bar-bg">
      <div class="progress-bar-fill" id="progress-fill"></div>
    </div>
    <div class="score-summary" id="score-summary"></div>
  </div>

  <!-- Reflection -->
  <div class="reflection">
    <h2>Reflection</h2>
    <div class="reflection-grid">
      <div class="reflection-field">
        <label>One or two practices I want to focus on in the next 2 weeks</label>
        <textarea id="ref-focus" placeholder="e.g. I want to incorporate more dictogloss tasks and push students to elaborate in small-group discussion…"></textarea>
      </div>
      <div class="reflection-field">
        <label>One concrete action I will take</label>
        <textarea id="ref-action" placeholder="e.g. I will design a dictogloss activity around the current reading for Week 8…"></textarea>
      </div>
    </div>
  </div>

  <!-- Actions -->
  <div class="actions">
    <button class="btn btn-primary" onclick="window.print()">🖨 Print / Save as PDF</button>
    <button class="btn btn-secondary" onclick="copyText()">📋 Copy summary to clipboard</button>
    <button class="btn btn-ghost" onclick="resetAll()">Reset</button>
  </div>

</div>

<script>
const practices = [
  "included partner/small-group interaction and extended discussion tasks.",
  "incorporated debates, role-based discussion, or interpretive exchanges.",
  "encouraged paraphrasing, circumlocution, and elaboration.",
  "targeted advanced language features (e.g., Konjunktiv, passive, modal particles, idioms, academic language).",
  "incorporated activities requiring narration and hypothesizing.",
  "incorporated activities involving comparison, interpretation, or discussion of abstract topics.",
  "designed tasks for different audiences/registers (e.g., personal vs. professional).",
  "provided opportunities for students to produce extended spoken or written discourse.",
  "integrated intercultural reflection, perspectives, or engagement with L2 speakers/communities.",
  "encouraged critical analysis of texts, media, language, or cultural representation.",
  "provided feedback that encouraged self-repair and modified output.",
  "incorporated planned vocabulary and grammar-focused activities.",
  "included collaborative reconstruction, information-gap, or dictogloss-style tasks.",
  "encouraged imaginative or creative engagement with texts (e.g., readers' theater, scene extensions, reinterpretations).",
  "incorporated reflective blogging, journals, or other reflective tasks.",
  "encouraged students to engage with authentic historical and/or contemporary texts and language varieties.",
];

const freqLabels = ["Never","Rarely","Sometimes","Often"];
const selClasses = ["sel-0","sel-1","sel-2","sel-3"];

const tbody = document.getElementById('checklist-body');

practices.forEach((text, i) => {
  const tr = document.createElement('tr');

  // Practice cell
  const tdP = document.createElement('td');
  tdP.className = 'td-practice';
  tdP.textContent = text;
  tr.appendChild(tdP);

  // Frequency cells
  freqLabels.forEach((_, j) => {
    const td = document.createElement('td');
    td.className = 'td-freq';

    const id = `r${i}_${j}`;
    const inp = document.createElement('input');
    inp.type = 'radio';
    inp.name = `row${i}`;
    inp.id = id;
    inp.className = selClasses[j];
    inp.value = j;
    inp.addEventListener('change', updateProgress);

    const lbl = document.createElement('label');
    lbl.htmlFor = id;
    lbl.className = 'freq-label';

    const dot = document.createElement('span');
    dot.className = 'freq-dot';
    dot.textContent = '✓';

    lbl.appendChild(dot);
    td.appendChild(inp);
    td.appendChild(lbl);
    tr.appendChild(td);
  });

  tbody.appendChild(tr);
});

function updateProgress() {
  const total = practices.length;
  let answered = 0;
  let scoreSum = 0;

  practices.forEach((_, i) => {
    const checked = document.querySelector(`input[name="row${i}"]:checked`);
    if (checked) {
      answered++;
      scoreSum += parseInt(checked.value);
    }
  });

  document.getElementById('progress-text').textContent = `${answered} of ${total}`;
  document.getElementById('progress-fill').style.width = `${(answered/total)*100}%`;

  if (answered === total) {
    const avg = scoreSum / total;
    const label = avg < 0.75 ? "largely unexplored — consider prioritizing a few areas"
                : avg < 1.5  ? "emerging — there are clear areas to build on"
                : avg < 2.25 ? "developing — good foundation with room to expand"
                : "strong — these practices are well-integrated";
    document.getElementById('score-summary').textContent =
      `Average frequency: ${avg.toFixed(1)} / 3 — ${label}.`;
  } else {
    document.getElementById('score-summary').textContent = '';
  }
}

function resetAll() {
  if (!confirm('Reset all responses?')) return;
  document.querySelectorAll('input[type=radio]').forEach(r => r.checked = false);
  document.querySelectorAll('textarea').forEach(t => t.value = '');
  ['field-instructor','field-course','field-date'].forEach(id => {
    document.getElementById(id).value = '';
  });
  updateProgress();
}

function copyText() {
  const instructor = document.getElementById('field-instructor').value || '(not set)';
  const course = document.getElementById('field-course').value || '(not set)';
  const date = document.getElementById('field-date').value || '(not set)';
  const focus = document.getElementById('ref-focus').value || '(not completed)';
  const action = document.getElementById('ref-action').value || '(not completed)';

  let lines = [
    'L5 INSTRUCTOR SELF-ASSESSMENT CHECKLIST',
    `Instructor: ${instructor}  |  Course: ${course}  |  Date: ${date}`,
    '',
    'RESPONSES',
    '─────────────────────────────────────────'
  ];

  practices.forEach((text, i) => {
    const checked = document.querySelector(`input[name="row${i}"]:checked`);
    const val = checked ? freqLabels[parseInt(checked.value)] : '(not answered)';
    lines.push(`${i+1}. ${text}\n   → ${val}`);
  });

  lines.push('', 'REFLECTION', '─────────────────────────────────────────');
  lines.push(`Focus areas:\n${focus}`);
  lines.push(`Concrete next step:\n${action}`);

  navigator.clipboard.writeText(lines.join('\n'))
    .then(() => alert('Summary copied to clipboard!'))
    .catch(() => alert('Could not copy — please select and copy manually.'));
}
</script>
</body>
</html>
