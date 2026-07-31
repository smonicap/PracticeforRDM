---
title: <To Take 2026> 
layout: default
nav_order: 1
---

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Data Management Plan — Review Log</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=Source+Serif+4:ital,opsz,wght@0,8..60,400;0,8..60,600;0,8..60,700;1,8..60,500&family=IBM+Plex+Sans:wght@400;500;600&family=IBM+Plex+Mono:wght@400;500&display=swap');

:root{
  --ink:#1E2A28;
  --ink-2:#28352F;
  --paper:#F3EFE4;
  --paper-2:#EAE3D2;
  --line:#D8CFB8;
  --text:#23261F;
  --muted:#726C5C;
  --teal:#3D6E63;
  --teal-deep:#294942;
  --ochre:#AD7C34;
  --rust:#9C4B37;
  --slate:#767B72;
  --gold:#BE9A46;
  --shadow: 0 1px 2px rgba(30,42,40,0.06), 0 8px 24px rgba(30,42,40,0.06);
}

*{box-sizing:border-box;}
html,body{margin:0;padding:0;}
body{
  background:var(--paper);
  color:var(--text);
  font-family:'IBM Plex Sans',sans-serif;
  line-height:1.45;
  -webkit-font-smoothing:antialiased;
}

/* ---------- layout shell ---------- */
.sheet{
  max-width:920px;
  margin:0 auto;
  background:var(--paper);
  position:relative;
}

/* ---------- header / strata banner ---------- */
.banner{
  background:
    repeating-linear-gradient(180deg,
      rgba(255,255,255,0.02) 0px, rgba(255,255,255,0.02) 2px,
      transparent 2px, transparent 4px),
    linear-gradient(155deg,#1B2624 0%,#233530 38%,#2E463D 62%,#20302B 100%);
  color:#EDE7D6;
  padding:40px 44px 30px;
  position:relative;
  overflow:hidden;
}
.banner::after{
  content:"";
  position:absolute; left:0; right:0; bottom:0;
  height:8px;
  background:linear-gradient(90deg,var(--gold) 0%,var(--ochre) 35%,var(--rust) 62%,var(--teal) 100%);
  opacity:0.9;
}
.eyebrow-top{
  font-family:'IBM Plex Mono',monospace;
  font-size:11px;
  letter-spacing:.16em;
  text-transform:uppercase;
  color:#B9CFC5;
  margin:0 0 10px;
}
.banner h1{
  font-family:'Source Serif 4',serif;
  font-weight:600;
  font-size:34px;
  margin:0 0 6px;
  letter-spacing:-.01em;
}
.banner p.sub{
  margin:0;
  font-size:14.5px;
  color:#CBD8CE;
  max-width:60ch;
}

/* ---------- project meta card ---------- */
.meta-card{
  margin:-26px 44px 0;
  background:#fff;
  border:1px solid var(--line);
  box-shadow:var(--shadow);
  border-radius:3px;
  position:relative;
  z-index:2;
  padding:22px 24px 8px;
}
.meta-grid{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:0 28px;
}
.field{
  margin-bottom:16px;
}
.field label{
  display:block;
  font-family:'IBM Plex Mono',monospace;
  font-size:10.5px;
  letter-spacing:.09em;
  text-transform:uppercase;
  color:var(--muted);
  margin-bottom:5px;
}
.field input{
  width:100%;
  border:none;
  border-bottom:1px solid var(--line);
  background:transparent;
  font-family:'IBM Plex Sans',sans-serif;
  font-size:14.5px;
  color:var(--text);
  padding:4px 2px 7px;
  outline:none;
  transition:border-color .15s;
}
.field input:focus{border-bottom:1.5px solid var(--teal);}
.field input::placeholder{color:#B9B29B;}

/* ---------- tally / progress bar ---------- */
.tally-bar{
  position:sticky;
  top:0;
  z-index:20;
  background:rgba(243,239,228,0.94);
  backdrop-filter:blur(6px);
  border-bottom:1px solid var(--line);
  padding:11px 44px;
  display:flex;
  align-items:center;
  gap:22px;
  font-size:13px;
}
.tally-bar .progress-wrap{
  flex:1;
  display:flex;
  align-items:center;
  gap:10px;
}
.progress-track{
  flex:1;
  height:6px;
  border-radius:4px;
  background:var(--paper-2);
  overflow:hidden;
  border:1px solid var(--line);
}
.progress-fill{
  height:100%;
  width:0%;
  background:linear-gradient(90deg,var(--teal),var(--gold));
  transition:width .3s ease;
}
.progress-label{
  font-family:'IBM Plex Mono',monospace;
  font-size:11px;
  color:var(--muted);
  white-space:nowrap;
}
.tally-counts{
  display:flex;
  gap:14px;
  font-family:'IBM Plex Mono',monospace;
  font-size:11.5px;
}
.tally-counts span{display:flex;align-items:center;gap:5px;}
.dot{width:8px;height:8px;border-radius:50%;display:inline-block;}
.dot.yes{background:var(--teal);}
.dot.ish{background:var(--ochre);}
.dot.no{background:var(--rust);}
.dot.na{background:var(--slate);}

/* ---------- sections ---------- */
.content{padding:34px 44px 10px;}
.section{
  display:flex;
  margin-bottom:6px;
  border:1px solid var(--line);
  background:#fff;
  border-radius:3px;
  overflow:hidden;
  box-shadow:var(--shadow);
}
.section + .section{margin-top:22px;}
.strata{
  width:14px;
  flex-shrink:0;
}
.strata.s0{background:linear-gradient(180deg,var(--teal),var(--teal-deep));}
.strata.s1{background:linear-gradient(180deg,var(--ochre),#8C6528);}
.strata.s2{background:linear-gradient(180deg,#6F8577,#4E6055);}
.strata.s3{background:linear-gradient(180deg,var(--rust),#763527);}
.strata.s4{background:linear-gradient(180deg,var(--gold),#8C6528,var(--teal));}

.section-body{flex:1; padding:22px 26px 20px;}
.section-head{
  display:flex;
  justify-content:space-between;
  align-items:baseline;
  flex-wrap:wrap;
  gap:6px 16px;
  margin-bottom:4px;
  border-bottom:1px solid var(--paper-2);
  padding-bottom:12px;
}
.section-head .titles{display:flex; flex-direction:column;}
.section-eyebrow{
  font-family:'IBM Plex Mono',monospace;
  font-size:10.5px;
  letter-spacing:.1em;
  text-transform:uppercase;
  color:var(--muted);
  margin-bottom:2px;
}
.section-head h2{
  font-family:'Source Serif 4',serif;
  font-weight:600;
  font-size:20px;
  margin:0;
  color:var(--ink);
}
.section-desc{
  font-size:12.5px;
  color:var(--muted);
  max-width:34ch;
  text-align:right;
}

.subgroup-label{
  font-family:'IBM Plex Mono',monospace;
  font-size:11px;
  letter-spacing:.08em;
  text-transform:uppercase;
  color:var(--teal-deep);
  margin:18px 0 6px;
  padding-top:8px;
  border-top:1px dashed var(--paper-2);
}
.subgroup-label:first-of-type{border-top:none; margin-top:14px;}

.item-row{
  display:flex;
  align-items:flex-start;
  justify-content:space-between;
  gap:18px;
  padding:11px 0;
  border-bottom:1px solid #F0EBDD;
}
.item-row:last-child{border-bottom:none;}
.item-text{
  font-size:14px;
  color:var(--text);
  padding-top:5px;
  max-width:60ch;
}
.item-text b{font-weight:600; color:var(--ink);}

.status-group{
  display:flex;
  gap:6px;
  flex-shrink:0;
}
.status-btn{
  font-family:'IBM Plex Mono',monospace;
  font-size:11px;
  letter-spacing:.03em;
  border:1.3px solid var(--line);
  background:#fff;
  color:var(--muted);
  padding:7px 11px;
  border-radius:20px;
  cursor:pointer;
  transition:all .12s ease;
  user-select:none;
}
.status-btn:hover{border-color:#B9B29B;}
.status-btn.active[data-val="yes"]{background:var(--teal); border-color:var(--teal); color:#fff;}
.status-btn.active[data-val="ish"]{background:var(--ochre); border-color:var(--ochre); color:#fff;}
.status-btn.active[data-val="no"]{background:var(--rust); border-color:var(--rust); color:#fff;}
.status-btn.active[data-val="na"]{background:var(--slate); border-color:var(--slate); color:#fff;}

/* ---------- notes ---------- */
.notes-wrap{margin-top:18px;}
.notes-wrap label{
  display:block;
  font-family:'IBM Plex Mono',monospace;
  font-size:10.5px;
  letter-spacing:.08em;
  text-transform:uppercase;
  color:var(--muted);
  margin-bottom:6px;
}
.notes-wrap textarea{
  width:100%;
  min-height:56px;
  resize:vertical;
  border:1px solid var(--line);
  border-radius:3px;
  background:var(--paper);
  font-family:'IBM Plex Sans',sans-serif;
  font-size:13px;
  color:var(--text);
  padding:9px 11px;
  outline:none;
}
.notes-wrap textarea:focus{border-color:var(--teal);}

/* ---------- totals footer ---------- */
.totals-card{
  margin:26px 0 8px;
  border:1px solid var(--line);
  background:var(--ink);
  color:#EDE7D6;
  border-radius:3px;
  padding:20px 26px;
  display:flex;
  align-items:center;
  justify-content:space-between;
  flex-wrap:wrap;
  gap:14px;
}
.totals-card h3{
  font-family:'Source Serif 4',serif;
  font-weight:600;
  font-size:17px;
  margin:0;
}
.totals-grid{display:flex; gap:26px;}
.totals-grid div{text-align:center;}
.totals-grid .num{font-family:'IBM Plex Mono',monospace; font-size:22px; font-weight:500;}
.totals-grid .lbl{font-family:'IBM Plex Mono',monospace; font-size:10px; letter-spacing:.08em; text-transform:uppercase; color:#B9CFC5;}

/* ---------- action bar ---------- */
.actions{
  display:flex; gap:10px; justify-content:flex-end;
  padding:14px 44px 40px;
  flex-wrap:wrap;
}
.btn{
  font-family:'IBM Plex Mono',monospace;
  font-size:12px;
  letter-spacing:.04em;
  padding:10px 18px;
  border-radius:3px;
  border:1.3px solid var(--ink);
  background:transparent;
  color:var(--ink);
  cursor:pointer;
  transition:all .15s;
}
.btn:hover{background:var(--ink); color:#EDE7D6;}
.btn.primary{background:var(--ink); color:#EDE7D6;}
.btn.primary:hover{background:var(--teal-deep); border-color:var(--teal-deep);}
.btn.ghost{border-color:var(--line); color:var(--muted);}
.btn.ghost:hover{background:var(--paper-2); color:var(--text); border-color:var(--paper-2);}

.save-note{
  font-family:'IBM Plex Mono',monospace;
  font-size:10.5px;
  color:var(--muted);
  padding:0 44px 26px;
  text-align:right;
}

.attribution{
  font-size:11.5px;
  color:var(--muted);
  padding:0 44px 40px;
  border-top:1px solid var(--line);
  margin-top:6px;
  padding-top:16px;
}
.attribution a{color:var(--teal-deep);}

/* ---------- print ---------- */
@media print{
  .tally-bar, .actions, .save-note{display:none !important;}
  body{background:#fff;}
  .section{box-shadow:none; break-inside:avoid;}
  .banner::after{display:none;}
}

@media (max-width:640px){
  .meta-grid{grid-template-columns:1fr;}
  .banner,.content,.actions,.save-note,.attribution{padding-left:20px; padding-right:20px;}
  .tally-bar{padding-left:20px; padding-right:20px;}
  .item-row{flex-direction:column; align-items:flex-start;}
  .section-desc{text-align:left;}
}
</style>
</head>
<body>

<div class="sheet">

  <div class="banner">
    <p class="eyebrow-top">Research Data Management · Review Instrument</p>
    <h1>Data Management Plan — Review Log</h1>
    <p class="sub">A working checklist for reviewing DMPs against the Alliance Simplified Template rubric. Mark each criterion, leave dated notes per section, and track completeness as you go.</p>
  </div>

  <div class="meta-card">
    <div class="meta-grid">
      <div class="field"><label>Project Title</label><input type="text" data-meta="projectTitle" placeholder="e.g. Longitudinal Study of..."></div>
      <div class="field"><label>PI(s)</label><input type="text" data-meta="pis" placeholder="Principal investigator(s)"></div>
      <div class="field"><label>DMP Creator</label><input type="text" data-meta="creator" placeholder="Name of DMP author"></div>
      <div class="field"><label>DMP URL</label><input type="text" data-meta="url" placeholder="Link to plan"></div>
      <div class="field"><label>Review Date</label><input type="date" data-meta="date"></div>
      <div class="field"><label>Reviewer</label><input type="text" data-meta="reviewer" placeholder="Your name"></div>
    </div>
  </div>

  <div class="tally-bar">
    <div class="progress-wrap">
      <div class="progress-track"><div class="progress-fill" id="progressFill"></div></div>
      <div class="progress-label" id="progressLabel">0 / 24 reviewed</div>
    </div>
    <div class="tally-counts">
      <span><span class="dot yes"></span><span id="countYes">0</span> Yes</span>
      <span><span class="dot ish"></span><span id="countIsh">0</span> Ish</span>
      <span><span class="dot no"></span><span id="countNo">0</span> No</span>
      <span><span class="dot na"></span><span id="countNa">0</span> N/A</span>
    </div>
  </div>

  <div class="content" id="content"></div>

  <div class="content" style="padding-top:0;">
    <div class="totals-card">
      <h3>Overall assessment</h3>
      <div class="totals-grid">
        <div><div class="num" id="totYes">0</div><div class="lbl">Yes</div></div>
        <div><div class="num" id="totIsh">0</div><div class="lbl">Ish</div></div>
        <div><div class="num" id="totNo">0</div><div class="lbl">No</div></div>
        <div><div class="num" id="totNa">0</div><div class="lbl">N/A</div></div>
      </div>
    </div>
  </div>

  <div class="actions">
    <button class="btn ghost" id="resetBtn">Clear all</button>
    <button class="btn" id="printBtn">Print / Export PDF</button>
    <button class="btn primary" id="saveBtn">Save review</button>
  </div>
  <div class="save-note" id="saveNote">Not yet saved</div>

  <div class="attribution">
    Adapted from the Alliance Simplified Template (Funding Application Stage) Rubric, developed by the Data Management Planning Expert Group. Intended as a shorter checklist companion to the longform criteria. Originally created by McMaster RDM Services, 2025-08-18 · Last updated 2026-02-02.
  </div>

</div>

<script>
const SECTIONS = [
  {
    id:'responsibility', strata:'s0',
    eyebrow:'01 · Ethics & Agreements',
    title:'Responsibility',
    desc:'Ethical, legal, and commercial responsibilities',
    items:[
      {id:'r1', text:'Demonstrates consideration of <b>policies, terms of use, & other agreements</b>'},
      {id:'r2', text:'Provides info on how <b>sensitive data</b> will be safeguarded (esp. participant data)'},
      {id:'r3', text:'Identifies if research relates to <b>Indigenous data</b> and outlines plan for data sovereignty'}
    ]
  },
  {
    id:'collection', strata:'s1',
    eyebrow:'02 · Sources & Formats',
    title:'Data Collection',
    desc:'Sources and formats',
    items:[
      {id:'c1', text:'Thoroughly describes <b>data types</b> collected/acquired including non-proprietary formats'},
      {id:'c2', text:'Provides estimate of <b>data size</b> (GB, TB) including all data types and file versioning'},
      {id:'c3', text:'Indicates which data is <b>sensitive</b> and/or involves Indigenous groups/knowledge'}
    ]
  },
  {
    id:'documentation', strata:'s2',
    eyebrow:'03 · Reproducibility',
    title:'Documentation',
    desc:'Understandable and reproducible',
    items:[
      {id:'d1', text:'Outlines clear <b>plan for documentation & metadata</b> (inc. standards) for full data cycle'},
      {id:'d2', text:'Names <b>formats</b> — codebooks, dictionaries, READMEs, notes, code, files/folder system'}
    ]
  },
  {
    id:'active', strata:'s3',
    eyebrow:'04 · Storage, Security, Backups',
    title:'Active Data Management',
    desc:'Data storage, security, backups',
    items:[
      {id:'a1', text:'Describes <b>active storage</b> location and process, inc. software, versions, platforms'},
      {id:'a2', text:'Details <b>backup</b> locations, workflows, length, and access process'},
      {id:'a3', text:'Identifies <b>access permissions</b> (inc. roles or team members and what data accessed)'},
      {id:'a4', text:'Describes <b>security measures</b> and protection of sensitive data (inc. restrictions)'}
    ]
  },
  {
    id:'longterm', strata:'s4',
    eyebrow:'05 · Stewardship, Retention, Deposit, Preservation',
    title:'Long-Term Data Management',
    desc:'',
    items:[
      {id:'l1', text:'Provides information on mechanisms to protect <b>participant confidentiality</b>'},
      {id:'l2', text:'Outlines <b>long term stewardship</b> and access plan in compliance with ethics'}
    ],
    subgroups:[
      {label:'Retention', items:[
        {id:'ret1', text:'Describes which data they will <b>keep/delete</b> long-term and why'},
        {id:'ret2', text:'Provides <b>retention timelines</b> for all data types'},
        {id:'ret3', text:'Process for <b>quality assurance, normalizing, & de-identification</b> of files'},
        {id:'ret4', text:'For copies <b>retained but not deposited</b> — addresses storage location and files'},
        {id:'ret5', text:'<b>Data cleaning & format changes</b>, proprietary/nonproprietary files, scripts, programs'}
      ]},
      {label:'Deposit', items:[
        {id:'dep1', text:'Explains how the data will be made <b>discoverable, accessible, and reusable</b>'},
        {id:'dep2', text:'Describes <b>data repository features</b> (DOI minting, searchable record, reuse terms)'},
        {id:'dep3', text:'Outlines <b>access details</b>, ex. embargoes, open access licenses, or access restrictions'},
        {id:'dep4', text:'<b>Data cleaning & format changes</b>, proprietary/nonproprietary files, scripts, programs'}
      ]},
      {label:'Preservation', items:[
        {id:'pres1', text:'<b>Data cleaning & format changes</b>, proprietary/nonproprietary files, scripts, programs'}
      ]}
    ]
  }
];

const STATUS_OPTS = [
  {val:'yes', label:'Yes'},
  {val:'ish', label:'Ish'},
  {val:'no', label:'No'},
  {val:'na', label:'N/A'}
];

const STORAGE_KEY = 'dmp-review-log-v1';
let state = { meta:{}, status:{}, notes:{} };

function allItems(){
  let out = [];
  SECTIONS.forEach(s=>{
    (s.items||[]).forEach(i=>out.push(i));
    (s.subgroups||[]).forEach(g=>g.items.forEach(i=>out.push(i)));
  });
  return out;
}
const ITEM_IDS = allItems().map(i=>i.id);

function renderSections(){
  const root = document.getElementById('content');
  root.innerHTML = '';
  SECTIONS.forEach(sec=>{
    const wrap = document.createElement('div');
    wrap.className = 'section';

    const strata = document.createElement('div');
    strata.className = 'strata ' + sec.strata;
    wrap.appendChild(strata);

    const body = document.createElement('div');
    body.className = 'section-body';

    const head = document.createElement('div');
    head.className = 'section-head';
    head.innerHTML = `
      <div class="titles">
        <div class="section-eyebrow">${sec.eyebrow}</div>
        <h2>${sec.title}</h2>
      </div>
      <div class="section-desc">${sec.desc||''}</div>
    `;
    body.appendChild(head);

    (sec.items||[]).forEach(item=>body.appendChild(renderItemRow(item)));

    (sec.subgroups||[]).forEach(g=>{
      const lbl = document.createElement('div');
      lbl.className = 'subgroup-label';
      lbl.textContent = g.label;
      body.appendChild(lbl);
      g.items.forEach(item=>body.appendChild(renderItemRow(item)));
    });

    const notesWrap = document.createElement('div');
    notesWrap.className = 'notes-wrap';
    notesWrap.innerHTML = `<label>${sec.title} notes (include date)</label>`;
    const ta = document.createElement('textarea');
    ta.placeholder = 'Reviewer comments...';
    ta.dataset.notes = sec.id;
    ta.value = state.notes[sec.id] || '';
    ta.addEventListener('input', e=>{
      state.notes[sec.id] = e.target.value;
      queueSave();
    });
    notesWrap.appendChild(ta);
    body.appendChild(notesWrap);

    wrap.appendChild(body);
    root.appendChild(wrap);
  });
}

function renderItemRow(item){
  const row = document.createElement('div');
  row.className = 'item-row';

  const text = document.createElement('div');
  text.className = 'item-text';
  text.innerHTML = item.text;
  row.appendChild(text);

  const grp = document.createElement('div');
  grp.className = 'status-group';
  STATUS_OPTS.forEach(opt=>{
    const btn = document.createElement('button');
    btn.className = 'status-btn';
    btn.dataset.val = opt.val;
    btn.dataset.item = item.id;
    btn.textContent = opt.label;
    if(state.status[item.id] === opt.val) btn.classList.add('active');
    btn.addEventListener('click', ()=>{
      state.status[item.id] = (state.status[item.id] === opt.val) ? null : opt.val;
      renderSections();
      updateTallies();
      queueSave();
    });
    grp.appendChild(btn);
  });
  row.appendChild(grp);
  return row;
}

function updateTallies(){
  let counts = {yes:0, ish:0, no:0, na:0};
  ITEM_IDS.forEach(id=>{
    const v = state.status[id];
    if(v) counts[v]++;
  });
  const answered = counts.yes + counts.ish + counts.no + counts.na;
  document.getElementById('countYes').textContent = counts.yes;
  document.getElementById('countIsh').textContent = counts.ish;
  document.getElementById('countNo').textContent = counts.no;
  document.getElementById('countNa').textContent = counts.na;
  document.getElementById('totYes').textContent = counts.yes;
  document.getElementById('totIsh').textContent = counts.ish;
  document.getElementById('totNo').textContent = counts.no;
  document.getElementById('totNa').textContent = counts.na;
  document.getElementById('progressLabel').textContent = `${answered} / ${ITEM_IDS.length} reviewed`;
  document.getElementById('progressFill').style.width = (answered/ITEM_IDS.length*100).toFixed(0) + '%';
}

function bindMetaFields(){
  document.querySelectorAll('[data-meta]').forEach(el=>{
    el.value = state.meta[el.dataset.meta] || '';
    el.addEventListener('input', e=>{
      state.meta[el.dataset.meta] = e.target.value;
      queueSave();
    });
  });
}

let saveTimer = null;
function queueSave(){
  const note = document.getElementById('saveNote');
  note.textContent = 'Unsaved changes...';
  clearTimeout(saveTimer);
  saveTimer = setTimeout(doSave, 700);
}

async function doSave(){
  const note = document.getElementById('saveNote');
  try{
    const result = await window.storage.set(STORAGE_KEY, JSON.stringify(state), false);
    if(result){
      note.textContent = 'Saved ' + new Date().toLocaleTimeString();
    } else {
      note.textContent = 'Could not save (storage unavailable)';
    }
  }catch(err){
    note.textContent = 'Could not save (storage unavailable)';
  }
}

async function loadState(){
  try{
    const result = await window.storage.get(STORAGE_KEY, false);
    if(result && result.value){
      const parsed = JSON.parse(result.value);
      state = Object.assign({meta:{}, status:{}, notes:{}}, parsed);
    }
  }catch(err){
    // no saved state yet
  }
  renderSections();
  bindMetaFields();
  updateTallies();
  document.getElementById('saveNote').textContent = 'Loaded';
}

document.getElementById('saveBtn').addEventListener('click', doSave);
document.getElementById('printBtn').addEventListener('click', ()=>window.print());
document.getElementById('resetBtn').addEventListener('click', async ()=>{
  if(!confirm('Clear all responses and notes? This cannot be undone.')) return;
  state = {meta:{}, status:{}, notes:{}};
  try{ await window.storage.delete(STORAGE_KEY, false); }catch(e){}
  renderSections();
  bindMetaFields();
  updateTallies();
  document.getElementById('saveNote').textContent = 'Cleared';
});

loadState();
</script>

</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Data Management Plan (DMP) Interactive Checklist</title>
  <style>
    :root {
      --primary: #2563eb;
      --bg: #f8fafc;
      --card-bg: #ffffff;
      --text: #1e293b;
      --text-muted: #64748b;
      --border: #e2e8f0;
      --accent: #dbeafe;
    }

    body {
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
      background-color: var(--bg);
      color: var(--text);
      line-height: 1.5;
      padding: 40px 20px;
      max-width: 800px;
      margin: 0 auto;
    }

    .header-container {
      margin-bottom: 30px;
      background: var(--card-bg);
      padding: 24px;
      border-radius: 12px;
      border: 1px solid var(--border);
      box-shadow: 0 1px 3px rgba(0,0,0,0.05);
    }

    h1 {
      margin: 0 0 10px 0;
      font-size: 28px;
      color: #0f172a;
    }

    .progress-container {
      background: var(--border);
      height: 10px;
      border-radius: 5px;
      overflow: hidden;
      margin-top: 15px;
    }

    .progress-bar {
      background: var(--primary);
      height: 100%;
      width: 0%;
      transition: width 0.3s ease;
    }

    .counter-text {
      font-size: 14px;
      color: var(--text-muted);
      margin-top: 8px;
      display: block;
    }

    .section-card {
      background: var(--card-bg);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 24px;
      margin-bottom: 24px;
      box-shadow: 0 1px 3px rgba(0,0,0,0.05);
    }

    .section-title {
      font-size: 18px;
      font-weight: 700;
      margin-top: 0;
      margin-bottom: 6px;
      color: #0f172a;
      text-transform: uppercase;
      letter-spacing: 0.5px;
    }

    .section-subtitle {
      font-size: 14px;
      color: var(--text-muted);
      margin-bottom: 16px;
      font-style: italic;
    }

    .checklist-group {
      display: flex;
      flex-direction: column;
      gap: 12px;
    }

    .checklist-item {
      display: flex;
      align-items: flex-start;
      padding: 12px;
      border-radius: 8px;
      border: 1px solid transparent;
      cursor: pointer;
      transition: background 0.2s, border 0.2s;
    }

    .checklist-item:hover {
      background: var(--bg);
      border-color: var(--border);
    }

    .checklist-item input[type="checkbox"] {
      width: 18px;
      height: 18px;
      margin-top: 3px;
      margin-right: 12px;
      cursor: pointer;
      accent-color: var(--primary);
      flex-shrink: 0;
    }

    .checklist-text {
      font-size: 15px;
      transition: color 0.2s, text-decoration 0.2s;
    }

    /* Completed Item States */
    .checklist-item input[type="checkbox"]:checked + .checklist-text {
      text-decoration: line-through;
      color: var(--text-muted);
    }

    .footer {
      text-align: center;
      margin-top: 40px;
      font-size: 13px;
      color: var(--text-muted);
    }
  </style>
</head>
<body>

  <!-- Summary Dashboard Card -->
  <div class="header-container">
    <h1>DMP Compliance Checklist</h1>
    <p style="margin: 0; color: var(--text-muted);">Track your progress across all mandatory Data Management Plan sections.</p>
    <div class="progress-container">
      <div class="progress-bar" id="progressBar"></div>
    </div>
    <span class="counter-text" id="counterText">0 of 0 requirements completed (0%)</span>
  </div>

  <form id="dmpForm">

    <!-- 1. Responsibility -->
    <div class="section-card">
      <div class="section-title">Responsibility</div>
      <div class="section-subtitle">Ethical, legal, and commercial responsibilities</div>
      <div class="checklist-group">
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text">Demonstrates clear consideration of institutional policies, platform terms of use, and third-party agreements.</span>
        </label>
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text">Provides specific information on how sensitive data will be safeguarded (especially private participant data).</span>
        </label>
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text">Identifies if the research relates to Indigenous data and explicitly outlines a plan for Indigenous data sovereignty.</span>
        </label>
      </div>
    </div>

    <!-- 2. Data Collection -->
    <div class="section-card">
      <div class="section-title">Data Collection</div>
      <div class="section-subtitle">Sources and formats</div>
      <div class="checklist-group">
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text">Thoroughly describes all data types collected or acquired, including a commitment to open, non-proprietary formats.</span>
        </label>
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text">Provides a clear estimate of overall data size (in GB or TB) including all expected data types and file versioning data.</span>
        </label>
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text">Explicitly indicates which data subsets are sensitive and/or directly involve Indigenous groups and traditional knowledge.</span>
        </label>
      </div>
    </div>

    <!-- 3. Documentation -->
    <div class="section-card">
      <div class="section-title">Documentation</div>
      <div class="section-subtitle">Understandable and reproducible</div>
      <div class="checklist-group">
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text">Outlines a clear plan for metadata and documentation standards across the full lifecycle of the data cycle.</span>
        </label>
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text">Explicitly names and structures tracking formats: codebooks, data dictionaries, READMEs, lab notes, code scripts, and file/folder naming systems.</span>
        </label>
      </div>
    </div>

    <!-- 4. Active Data Management -->
    <div class="section-card">
      <div class="section-title">Active Data Management</div>
      <div class="section-subtitle">Data storage, security, backups</div>
      <div class="checklist-group">
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text">Describes active working storage locations and operational processes, including specific software, program versions, and hosting platforms.</span>
        </label>
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text">Details alternate backup locations, regular backup workflows, retention length, and the data access recovery process.</span>
        </label>
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text">Identifies clear access permissions (including explicit roles or team member designations mapping to specific accessible data tiers).</span>
        </label>
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text">Describes physical and digital security measures alongside active protection protocols for sensitive data (including strict access restrictions).</span>
        </label>
      </div>
    </div>

    <!-- 5. Long-Term Data Management -->
    <div class="section-card">
      <div class="section-title">Long-Term Data Management</div>
      <div class="section-subtitle">Stewardship, Retention, Deposit, and Preservation</div>
      <div class="checklist-group">
        <!-- Base Stewardship/Confidentiality -->
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text">Provides explicit information on procedural mechanisms used to protect long-term participant confidentiality.</span>
        </label>
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text">Outlines a long-term data stewardship and general access plan that remains fully compliant with institutional research ethics.</span>
        </label>
        
        <!-- Retention sub-points -->
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text"><strong>Retention:</strong> Describes exactly which data files will be kept vs. permanently deleted long-term, providing rationales for each.</span>
        </label>
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text"><strong>Retention Timelines:</strong> Formulates concrete, time-bound retention milestones for all involved data types.</span>
        </label>
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text"><strong>Quality & De-identification:</strong> Explains the process for quality assurance, data normalizing, and rigorous file de-identification.</span>
        </label>
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text"><strong>Non-Deposited Copies:</strong> Addresses storage locations, security setups, and file parameters for copies retained but not deposited in a public registry.</span>
        </label>

        <!-- Deposit sub-points -->
