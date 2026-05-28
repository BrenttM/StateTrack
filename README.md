
<style>
  @import url('https://fonts.googleapis.com/css2?family=Barlow+Condensed:wght@400;600;700;900&family=Barlow:wght@400;500;600&display=swap');

  *{box-sizing:border-box;margin:0;padding:0;}
  :root{--orange:#D4600A;--black:#1a1100;--navy:#1a1a2e;--gold:#ffc800;}

  .sr{font-family:'Barlow',sans-serif;color:var(--color-text-primary);width:100%;}

  .hdr{background:var(--navy);color:#fff;padding:1rem;border-radius:var(--border-radius-lg) var(--border-radius-lg) 0 0;position:relative;overflow:hidden;}
  .hdr::before{content:'';position:absolute;top:-20px;right:-20px;width:130px;height:130px;border-radius:50%;border:16px solid rgba(255,200,0,0.1);}
  .hdr-top{display:flex;align-items:flex-start;justify-content:space-between;gap:8px;margin-bottom:8px;}
  .hdr-title{font-family:'Barlow Condensed',sans-serif;font-size:clamp(18px,4vw,26px);font-weight:900;line-height:1.1;text-transform:uppercase;letter-spacing:1px;}
  .hdr-title span{color:var(--gold);}
  .hdr-badge{background:var(--gold);color:var(--navy);font-family:'Barlow Condensed',sans-serif;font-weight:900;font-size:10px;letter-spacing:1.5px;text-transform:uppercase;padding:3px 8px;border-radius:3px;flex-shrink:0;white-space:nowrap;}
  .hdr-meta{display:flex;gap:10px;flex-wrap:wrap;font-size:11px;color:rgba(255,255,255,0.6);}
  .hdr-meta-item{display:flex;align-items:center;gap:4px;}
  .hdr-dot{width:4px;height:4px;border-radius:50%;background:var(--gold);}
  .hdr-note{background:rgba(255,200,0,0.12);border-left:3px solid var(--gold);padding:7px 10px;font-size:11px;color:rgba(255,255,255,0.8);line-height:1.5;margin-top:8px;}

  .tabs{display:flex;background:var(--color-background-secondary);border-bottom:0.5px solid var(--color-border-tertiary);overflow-x:auto;-webkit-overflow-scrolling:touch;scrollbar-width:none;}
  .tabs::-webkit-scrollbar{display:none;}
  .tab{flex:1;min-width:70px;padding:10px 4px;text-align:center;font-family:'Barlow Condensed',sans-serif;font-size:12px;font-weight:700;letter-spacing:0.5px;text-transform:uppercase;cursor:pointer;border:none;background:transparent;color:var(--color-text-secondary);border-bottom:3px solid transparent;white-space:nowrap;}
  .tab.active{color:var(--navy);border-bottom-color:var(--gold);background:var(--color-background-primary);}
  .tab.ltab.active{color:var(--orange);border-bottom-color:var(--orange);}

  .body{background:var(--color-background-primary);}
  .panel{display:none;}
  .panel.active{display:block;}

  .sec-lbl{font-family:'Barlow Condensed',sans-serif;font-size:10px;font-weight:700;letter-spacing:2px;text-transform:uppercase;color:var(--color-text-secondary);padding:8px 12px 5px;border-bottom:0.5px solid var(--color-border-tertiary);}

  .legend{display:flex;gap:5px;flex-wrap:wrap;padding:7px 12px;border-bottom:0.5px solid var(--color-border-tertiary);align-items:center;}
  .chip{display:inline-block;font-family:'Barlow Condensed',sans-serif;font-weight:700;font-size:10px;padding:2px 4px;border-radius:3px;white-space:nowrap;}
  .lchip{cursor:pointer;padding:3px 8px;font-size:11px;border:1.5px solid transparent;transition:transform 0.1s,box-shadow 0.1s;user-select:none;}
  .lchip:hover{transform:scale(1.08);}
  .lchip.selected{border-color:currentColor;box-shadow:0 0 0 2px rgba(0,0,0,0.15);}
  .c1{background:#E6F1FB;color:#0C447C;}
  .c2{background:#EAF3DE;color:#27500A;}
  .c3{background:#FAEEDA;color:#633806;}
  .c4{background:#FBEAF0;color:#72243E;}
  .c5{background:#EEEDFE;color:#3C3489;}
  .c6{background:#E1F5EE;color:#085041;}
  .legend-hint{font-size:10px;color:var(--color-text-secondary);margin-left:4px;}

  .tbl-wrap{overflow-x:auto;-webkit-overflow-scrolling:touch;}
  .ftbl{width:100%;border-collapse:collapse;font-size:11px;min-width:520px;}
  .ftbl th{font-family:'Barlow Condensed',sans-serif;font-size:10px;font-weight:700;letter-spacing:1px;text-transform:uppercase;color:var(--color-text-secondary);padding:5px 6px;background:var(--color-background-secondary);border-bottom:0.5px solid var(--color-border-tertiary);text-align:center;}
  .ftbl th:first-child,.ftbl th:nth-child(2),.ftbl th:nth-child(3){text-align:left;}
  .ftbl td{padding:4px 6px;border-bottom:0.5px solid var(--color-border-tertiary);text-align:center;vertical-align:middle;transition:background 0.15s;}
  .ftbl td:first-child,.ftbl td:nth-child(2),.ftbl td:nth-child(3){text-align:left;}
  .ftbl tr:hover td{background:var(--color-background-secondary);}
  .ftbl.has-filter tr.no-match td{opacity:0.2;}
  .ftbl.has-filter tr.has-match td{background:var(--color-background-primary);}
  .cell-chip{display:inline-block;font-family:'Barlow Condensed',sans-serif;font-weight:700;font-size:10px;padding:2px 4px;border-radius:3px;white-space:nowrap;transition:transform 0.15s,box-shadow 0.15s;}
  .cell-chip.lit{transform:scale(1.18);box-shadow:0 0 0 2px currentColor;position:relative;}

  .dfri{color:var(--navy);font-weight:700;font-size:9px;background:var(--gold);padding:2px 5px;border-radius:3px;display:inline-block;}
  .dsat{color:#fff;font-weight:700;font-size:9px;background:var(--navy);padding:2px 5px;border-radius:3px;display:inline-block;}
  .sn{font-family:'Barlow Condensed',sans-serif;font-weight:700;font-size:12px;color:var(--color-text-secondary);}

  .rb{padding:8px 12px;}
  .rst{font-family:'Barlow Condensed',sans-serif;font-weight:700;font-size:13px;letter-spacing:1px;text-transform:uppercase;color:var(--color-text-secondary);margin:10px 0 5px;padding-bottom:3px;border-bottom:0.5px solid var(--color-border-tertiary);}
  .r3row{display:flex;gap:6px;flex-wrap:wrap;padding:5px 0;border-bottom:0.5px solid var(--color-border-tertiary);}
  .r3item{background:var(--color-background-secondary);border-radius:var(--border-radius-md);padding:5px 10px;flex:1;min-width:90px;}
  .r3ev{font-size:11px;font-weight:500;}
  .r3t{font-family:'Barlow Condensed',sans-serif;font-size:14px;font-weight:700;color:var(--navy);margin-top:1px;}
  .pgrid{display:grid;grid-template-columns:1fr 90px 90px;gap:0;}
  .pgrid-hdr div{font-size:9px;color:var(--color-text-secondary);font-weight:600;text-transform:uppercase;letter-spacing:1px;padding-bottom:3px;border-bottom:0.5px solid var(--color-border-tertiary);}
  .pgrid-hdr div:nth-child(2),.pgrid-hdr div:nth-child(3){text-align:right;}
  .prow{display:contents;}
  .prow div{padding:4px 0;border-bottom:0.5px solid var(--color-border-tertiary);font-size:11px;}
  .prow div:nth-child(2),.prow div:nth-child(3){font-family:'Barlow Condensed',sans-serif;font-size:12px;font-weight:700;text-align:right;}
  .prow div:nth-child(3){color:var(--color-text-secondary);}

  .score-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:6px;margin-bottom:16px;}
  .score-card{text-align:center;padding:8px 4px;background:var(--color-background-secondary);border-radius:var(--border-radius-md);}
  .score-pts{font-family:'Barlow Condensed',sans-serif;font-size:20px;font-weight:900;color:var(--navy);}
  .score-pl{font-size:9px;color:var(--color-text-secondary);font-weight:600;}
  .info-block{background:var(--color-background-secondary);border-radius:var(--border-radius-md);padding:8px 12px;font-size:12px;margin-bottom:12px;}
  .wc-row{display:flex;justify-content:space-between;padding:5px 0;border-bottom:0.5px solid var(--color-border-tertiary);font-size:12px;}
  .wc-row:last-child{border-bottom:none;}
  .wc-t{font-family:'Barlow Condensed',sans-serif;font-weight:700;font-size:13px;}

  .lhdr{background:var(--black);color:#fff;padding:10px 12px;display:flex;align-items:center;gap:10px;border-bottom:3px solid var(--orange);}
  .lschool{font-family:'Barlow Condensed',sans-serif;font-size:clamp(15px,3.5vw,20px);font-weight:900;text-transform:uppercase;letter-spacing:1px;}
  .lsub{font-size:10px;color:rgba(255,255,255,0.6);margin-top:1px;}
  .lbadge{background:var(--orange);color:#fff;font-family:'Barlow Condensed',sans-serif;font-weight:900;font-size:10px;letter-spacing:1px;text-transform:uppercase;padding:3px 8px;border-radius:3px;white-space:nowrap;}
  .lnote{padding:6px 12px;background:rgba(212,96,10,0.07);border-bottom:0.5px solid var(--color-border-tertiary);display:flex;align-items:center;gap:6px;flex-wrap:wrap;}
  .qbadge{display:inline-flex;align-items:center;gap:3px;font-size:9px;font-weight:700;color:var(--orange);background:rgba(212,96,10,0.12);border-radius:3px;padding:1px 5px;font-family:'Barlow Condensed',sans-serif;letter-spacing:0.5px;text-transform:uppercase;white-space:nowrap;}
  .lday-hdr{display:flex;align-items:center;gap:8px;padding:8px 12px 5px;border-bottom:0.5px solid var(--color-border-tertiary);background:var(--color-background-secondary);}
  .ldpill{font-family:'Barlow Condensed',sans-serif;font-size:10px;font-weight:700;letter-spacing:1px;text-transform:uppercase;padding:2px 7px;border-radius:3px;}
  .ldfri{background:var(--orange);color:#fff;}
  .ldsat{background:var(--black);color:#fff;}
  .ldtitle{font-family:'Barlow Condensed',sans-serif;font-size:11px;font-weight:700;letter-spacing:1px;text-transform:uppercase;color:var(--color-text-secondary);}
  .lrow{display:grid;grid-template-columns:68px 1fr 1fr;gap:0;padding:6px 12px;border-bottom:0.5px solid var(--color-border-tertiary);align-items:start;}
  .lrow:hover{background:var(--color-background-secondary);}
  .lrow.q{background:rgba(212,96,10,0.05);}
  .lrow.q:hover{background:rgba(212,96,10,0.1);}
  .ltime{font-family:'Barlow Condensed',sans-serif;font-size:13px;font-weight:700;white-space:nowrap;padding-top:1px;}
  .levent{font-size:11px;font-weight:600;line-height:1.4;}
  .lathletes{font-size:10px;color:var(--color-text-secondary);line-height:1.5;}

  @media(max-width:480px){
    .lrow{grid-template-columns:60px 1fr;grid-template-rows:auto auto;}
    .lathletes{grid-column:2;grid-row:2;padding-top:2px;}
    .pgrid{grid-template-columns:1fr 80px 80px;}
    .r3item{min-width:80px;}
    .hdr-note{font-size:10px;}
  }

  .ftr{background:var(--navy);color:rgba(255,255,255,0.7);font-size:10px;padding:8px 12px;line-height:1.6;border-radius:0 0 var(--border-radius-lg) var(--border-radius-lg);}
  .ftr strong{color:var(--gold);}
  .award-note{margin-top:8px;padding:7px;background:rgba(255,200,0,0.1);border-radius:var(--border-radius-md);border-left:3px solid var(--gold);}
  .award-title{font-size:10px;font-weight:600;margin-bottom:2px;}
  .award-sub{font-size:10px;color:var(--color-text-secondary);}
</style>

<div class="sr">
  <div class="hdr">
    <div class="hdr-top">
      <div class="hdr-title">2026 Kansas State<br><span>Track &amp; Field</span> Championship</div>
      <div class="hdr-badge">KSHSAA</div>
    </div>
    <div class="hdr-meta">
      <div class="hdr-meta-item"><div class="hdr-dot"></div>Friday &amp; Saturday</div>
      <div class="hdr-meta-item"><div class="hdr-dot"></div>Classes 1A - 6A</div>
      <div class="hdr-meta-item"><div class="hdr-dot"></div>All six classes, one site</div>
    </div>
    <div class="hdr-note">Schedule is a guide - events may run ahead without delay. Fri Session 1: 4A-5A-6A | Session 2: 1A-2A-3A | Sat: 1A-2A-3A-4A-5A-6A.</div>
  </div>

  <div class="tabs">
    <button class="tab active" onclick="showTab('field')">Field</button>
    <button class="tab" onclick="showTab('running')">Running</button>
    <button class="tab" onclick="showTab('scoring')">Scoring</button>
    <button class="tab ltab" onclick="showTab('lyndon')">Lyndon HS</button>
  </div>

  <div class="body">

    <div id="panel-field" class="panel active">
      <div class="sec-lbl">Prelims &amp; Finals - All Sessions</div>
      <div class="legend">
        <span class="chip c1 lchip" data-class="1A" onclick="toggleFilter('1A',this)">1A</span>
        <span class="chip c2 lchip" data-class="2A" onclick="toggleFilter('2A',this)">2A</span>
        <span class="chip c3 lchip" data-class="3A" onclick="toggleFilter('3A',this)">3A</span>
        <span class="chip c4 lchip" data-class="4A" onclick="toggleFilter('4A',this)">4A</span>
        <span class="chip c5 lchip" data-class="5A" onclick="toggleFilter('5A',this)">5A</span>
        <span class="chip c6 lchip" data-class="6A" onclick="toggleFilter('6A',this)">6A</span>
        <span class="legend-hint">tap to highlight</span>
      </div>
      <div class="tbl-wrap">
        <table class="ftbl" id="ftbl">
          <thead><tr><th>Sess</th><th>Day</th><th>Time</th><th>LJ</th><th>TJ</th><th>HJ-1</th><th>HJ-2</th><th>PV-N</th><th>PV-S</th><th>Shot</th><th>Disc</th><th>Jav</th></tr></thead>
          <tbody id="ftbody"></tbody>
        </table>
      </div>
    </div>

    <div id="panel-running" class="panel">
      <div class="rb">
        <div class="rst"><span class="dfri">Fri</span> 3200m Finals - 4A 5A 6A</div>
        <div class="r3row">
          <div class="r3item"><div class="r3ev">4A Girls &amp; Boys</div><div class="r3t">7:45-8:05 am</div></div>
          <div class="r3item"><div class="r3ev">5A Girls &amp; Boys</div><div class="r3t">8:05-8:25 am</div></div>
          <div class="r3item"><div class="r3ev">6A Girls &amp; Boys</div><div class="r3t">8:25-8:50 am</div></div>
        </div>
        <div class="rst" style="margin-top:12px;"><span class="dfri">Fri</span> Prelims - 4A/5A/6A &amp; 1A/2A/3A</div>
        <div class="pgrid pgrid-hdr">
          <div>Event</div><div style="text-align:right;">4A/5A/6A</div><div style="text-align:right;">1A/2A/3A</div>
        </div>
        <div class="pgrid" id="fpgrid"></div>
        <div style="font-size:10px;color:var(--color-text-secondary);padding:4px 0;font-style:italic;">Prelims concluded: 1:40 pm (4A/5A/6A) · 6:50 pm (1A/2A/3A)</div>
        <div class="rst" style="margin-top:12px;"><span class="dfri">Fri</span> 3200m Finals - 1A 2A 3A</div>
        <div class="r3row">
          <div class="r3item"><div class="r3ev">1A Girls &amp; Boys</div><div class="r3t">7:00-7:20 pm</div></div>
          <div class="r3item"><div class="r3ev">2A Girls &amp; Boys</div><div class="r3t">7:20-7:40 pm</div></div>
          <div class="r3item"><div class="r3ev">3A Girls &amp; Boys</div><div class="r3t">7:40-8:00 pm</div></div>
        </div>
        <div class="rst" style="margin-top:12px;"><span class="dsat">Sat</span> 100m Prelims - All Classes</div>
        <div class="r3row">
          <div class="r3item"><div class="r3ev">Girls 100m Dash</div><div class="r3t">8:30 am</div></div>
          <div class="r3item"><div class="r3ev">Boys 100m Dash</div><div class="r3t">9:00 am</div></div>
        </div>
        <div class="rst" style="margin-top:12px;"><span class="dsat">Sat</span> Finals</div>
        <div id="sfgrid"></div>
        <div class="award-note">
          <div class="award-title">Team Award Presentations</div>
          <div class="award-sub">Following the last race. Only coaches &amp; athletes on the infield.</div>
        </div>
      </div>
    </div>

    <div id="panel-scoring" class="panel">
      <div class="rb">
        <div class="rst">Point Scoring System</div>
        <div class="score-grid">
          <div class="score-card"><div class="score-pts">10</div><div class="score-pl">1st</div></div>
          <div class="score-card"><div class="score-pts">8</div><div class="score-pl">2nd</div></div>
          <div class="score-card"><div class="score-pts">6</div><div class="score-pl">3rd</div></div>
          <div class="score-card"><div class="score-pts">5</div><div class="score-pl">4th</div></div>
          <div class="score-card"><div class="score-pts">4</div><div class="score-pl">5th</div></div>
          <div class="score-card"><div class="score-pts">3</div><div class="score-pl">6th</div></div>
          <div class="score-card"><div class="score-pts">2</div><div class="score-pl">7th</div></div>
          <div class="score-card"><div class="score-pts">1</div><div class="score-pl">8th</div></div>
        </div>
        <div class="rst">Hall of Fame Inductions</div>
        <div class="info-block">Held Saturday - between Girls 4x800m Relay and Girls 100m Dash finals.</div>
        <div class="rst">Wheelchair Events - Saturday</div>
        <div style="margin-bottom:16px;">
          <div class="wc-row"><span>Wheelchair 100m Dash</span><span class="wc-t">1:20 pm</span></div>
          <div class="wc-row"><span>Wheelchair 1600m Run</span><span class="wc-t">2:50 pm</span></div>
          <div class="wc-row" style="border-bottom:none;"><span>Wheelchair 400m Dash</span><span class="wc-t">4:17 pm</span></div>
        </div>
        <div class="rst">Important Notes</div>
        <div class="info-block" style="font-size:11px;color:var(--color-text-secondary);line-height:1.7;">With all six classes at the same site, classes 1A, 2A, and 3A will have the earlier sessions. Running events will not be held back if proceeding ahead of schedule.</div>
      </div>
    </div>

    <div id="panel-lyndon" class="panel">
      <div class="lhdr">
        <div style="flex:1;">
          <div class="lschool">Lyndon High School</div>
          <div class="lsub">May 29-30, 2026 · State Track &amp; Field</div>
        </div>
        <div class="lbadge">Tigers</div>
      </div>
      <div class="lnote">
        <span class="qbadge">* If Qualified</span>
        <span style="font-size:10px;color:var(--color-text-secondary);">Requires qualifying from Day 1 prelims</span>
      </div>
      <div class="lday-hdr">
        <span class="ldpill ldfri">Friday</span>
        <span class="ldtitle">May 29 - Prelims &amp; Field Events</span>
      </div>
      <div id="lfri"></div>
      <div class="lday-hdr" style="margin-top:4px;">
        <span class="ldpill ldsat">Saturday</span>
        <span class="ldtitle">May 30 - Finals</span>
      </div>
      <div id="lsat"></div>
    </div>

  </div>

  <div class="ftr"><strong>Field events</strong> run simultaneously across all venues. See the Field tab for full session assignments.</div>
</div>

<script>
const cmap={'1A':'c1','2A':'c2','3A':'c3','4A':'c4','5A':'c5','6A':'c6'};

// LJ, TJ, HJ-1, HJ-2, PV-N, PV-S, Shot, Disc, Jav
const fd=[
  [1, 'Fri','7:45 am', '5A B','6A G','4A B','5A G','4A G','6A B','5A G','6A B','4A G'],
  [2, 'Fri','9:30 am', '4A G','6A B','',    '',    '',    '',    '5A B','4A G','4A B'],
  [3, 'Fri','11:15 am','4A B','5A B','6A G','4A G','6A G','5A B','4A B','6A G','5A G'],
  [4, 'Fri','1:00 pm', '1A B','5A G','',    '',    '',    '',    '1A G','3A B','5A B'],
  [5, 'Fri','2:45 pm', '1A G','3A G','1A B','2A G','1A G','2A B','2A G','1A B','3A B'],
  [6, 'Fri','4:30 pm', '2A B','3A B','',    '',    '',    '',    '3A G','2A B','1A B'],
  [7, 'Fri','6:15 pm', '3A G','2A G','3A B','1A G','2A G','1A B','3A B','1A G','2A B'],
  [8, 'Sat','8:00 am', '6A B','2A B','5A B','3A G','5A G','3A B','6A G','5A B','2A G'],
  [9, 'Sat','9:45 am', '6A G','1A G','',    '',    '',    '',    '6A B','5A G','1A G'],
  [10,'Sat','11:30 am','5A G','1A B','6A B','2A B','3A G','4A B','4A G','3A G','6A G'],
  [11,'Sat','1:15 pm', '3A B','4A G','',    '',    '',    '',    '2A B','4A B','6A B'],
  [12,'Sat','3:00 pm', '2A G','4A B','',    '',    '',    '',    '1A B','2A G','3A G'],
];

let activeFilter = null;

function makeChip(v) {
  if (!v) return '<span style="color:var(--color-text-secondary);font-size:9px;">-</span>';
  const m = v.match(/^(\d+A)\s([BG])$/);
  if (!m) return v;
  return `<span class="cell-chip ${cmap[m[1]]}" data-class="${m[1]}">${m[1]} ${m[2]}</span>`;
}

const tb = document.getElementById('ftbody');
fd.forEach(([s,d,t,...cells]) => {
  const db = d==='Fri' ? `<span class="dfri">Fri</span>` : `<span class="dsat">Sat</span>`;
  const classes = [...new Set(cells.map(c => { const m=c.match(/^(\d+A)/); return m?m[1]:''; }).filter(Boolean))].join(' ');
  tb.innerHTML += `<tr data-classes="${classes}"><td class="sn">${s}</td><td>${db}</td><td style="white-space:nowrap;font-size:10px;">${t}</td>${cells.map(c=>`<td>${makeChip(c)}</td>`).join('')}</tr>`;
});

function toggleFilter(cls, el) {
  const table = document.getElementById('ftbl');
  if (activeFilter === cls) {
    activeFilter = null;
    el.classList.remove('selected');
    table.classList.remove('has-filter');
    document.querySelectorAll('#ftbody tr').forEach(r => r.classList.remove('has-match','no-match'));
    document.querySelectorAll('#ftbody .cell-chip').forEach(c => c.classList.remove('lit'));
  } else {
    document.querySelectorAll('.lchip.selected').forEach(c => c.classList.remove('selected'));
    activeFilter = cls;
    el.classList.add('selected');
    table.classList.add('has-filter');
    document.querySelectorAll('#ftbody tr').forEach(r => {
      const match = (r.getAttribute('data-classes')||'').split(' ').includes(cls);
      r.classList.toggle('has-match', match);
      r.classList.toggle('no-match', !match);
    });
    document.querySelectorAll('#ftbody .cell-chip').forEach(c => {
      c.classList.toggle('lit', c.getAttribute('data-class') === cls);
    });
  }
}

const fp=[
  ['Girls 100m High Hurdles','9:00 am','2:10 pm'],
  ['Boys 110m High Hurdles','9:20 am','2:30 pm'],
  ['Girls 4x100 Relay','9:45 am','2:55 pm'],
  ['Boys 4x100 Relay','10:05 am','3:15 pm'],
  ['Girls 400m Dash','10:25 am','3:35 pm'],
  ['Boys 400m Dash','10:45 am','3:55 pm'],
  ['Girls 300m Low Hurdles','11:10 am','4:20 pm'],
  ['Boys 300m Int. Hurdles','11:35 am','4:45 pm'],
  ['Girls 200m Dash','12:05 pm','5:15 pm'],
  ['Boys 200m Dash','12:25 pm','5:35 pm'],
  ['Girls 4x400 Relay','12:45 pm','5:55 pm'],
  ['Boys 4x400 Relay','1:15 pm','6:25 pm'],
];
const fpg = document.getElementById('fpgrid');
fp.forEach(([e,t1,t2]) => {
  fpg.innerHTML += `<div class="prow"><div style="font-size:11px;font-weight:500;">${e}</div><div>${t1}</div><div>${t2}</div></div>`;
});

const sf=[
  ['Girls 100m High Hurdles','9:30 am'],['Boys 110m High Hurdles','10:00 am'],
  ['Girls 4x800 Relay','10:30 am'],['Boys 4x800 Relay','11:40 am'],
  ['* Hall of Fame Inductions',''],
  ['Girls 100m Dash','12:45 pm'],['Boys 100m Dash','1:05 pm'],
  ['Girls 1600m Run','1:25 pm'],['Boys 1600m Run','2:10 pm'],
  ['Girls 4x100 Relay','3:00 pm'],['Boys 4x100 Relay','3:20 pm'],
  ['Girls 400m Dash','3:45 pm'],['Boys 400m Dash','4:05 pm'],
  ['Girls 300m Low Hurdles','4:30 pm'],['Boys 300m Int. Hurdles','4:50 pm'],
  ['Girls 800m Run','5:10 pm'],['Boys 800m Run','5:35 pm'],
  ['Girls 200m Dash','5:55 pm'],['Boys 200m Dash','6:15 pm'],
  ['Girls 4x400 Relay','6:35 pm'],['Boys 4x400 Relay','7:00 pm'],
];
const sfg = document.getElementById('sfgrid');
sf.forEach(([e,t]) => {
  if (e.startsWith('*')) {
    sfg.innerHTML += `<div style="text-align:center;padding:4px;font-size:10px;color:var(--color-text-secondary);font-style:italic;letter-spacing:1px;border-bottom:0.5px solid var(--color-border-tertiary);">${e}</div>`;
  } else {
    sfg.innerHTML += `<div style="display:flex;justify-content:space-between;align-items:center;padding:4px 0;border-bottom:0.5px solid var(--color-border-tertiary);"><span style="font-size:11px;font-weight:500;">${e}</span><span style="font-family:'Barlow Condensed',sans-serif;font-size:12px;font-weight:700;">${t}</span></div>`;
  }
});

const lfi=[
  {t:'2:30 PM',e:'110m Hurdles',g:'Boys',q:false,a:'Lyric Medina'},
  {t:'2:45 PM',e:'High Jump',g:'Girls',q:false,a:'Phoebe Wright'},
  {t:'2:45 PM',e:'Pole Vault',g:'Boys',q:false,a:'Lucas Griffin'},
  {t:'2:55 PM',e:'4x100 Relay',g:'Girls',q:false,a:'Lexi Totty, Trysten Sowers, Jaedyn Segrist, Charleigh Bean'},
  {t:'3:15 PM',e:'4x100 Relay',g:'Boys',q:false,a:'Zach Criqui, Asher Edington, Lucas Griffin, James Marcotte'},
  {t:'3:35 PM',e:'400m Dash',g:'Girls',q:false,a:'Trysten Sowers, Charleigh Bean'},
  {t:'3:55 PM',e:'400m Dash',g:'Boys',q:false,a:'Zach Criqui, Cason Rhoads, Owen Edington'},
  {t:'4:45 PM',e:'300m Hurdles',g:'Boys',q:false,a:'Lyric Medina'},
  {t:'5:15 PM',e:'200m Dash',g:'Girls',q:false,a:'Trysten Sowers'},
  {t:'5:35 PM',e:'200m Dash',g:'Boys',q:false,a:'Asher Edington'},
  {t:'5:55 PM',e:'4x400 Relay',g:'Girls',q:false,a:'Lexi Totty, Trysten Sowers, Jaedyn Segrist, Charleigh Bean'},
  {t:'6:15 PM',e:'Pole Vault',g:'Girls',q:false,a:'Lexi Totty'},
  {t:'6:15 PM',e:'Javelin',g:'Boys',q:false,a:'Lyric Medina'},
  {t:'6:25 PM',e:'4x400 Relay',g:'Boys',q:false,a:'Zach Criqui, Owen Edington, Cason Rhoads, Lucas Griffin'},
];
const lsa=[
  {t:'8:00 AM',e:'Triple Jump',g:'Boys',q:false,a:'James Marcotte, Cason Rhoads'},
  {t:'9:00 AM',e:'100m Prelims',g:'Boys',q:false,a:'Asher Edington'},
  {t:'10:00 AM',e:'110m Hurdles Finals',g:'Boys',q:true,a:'Lyric Medina'},
  {t:'11:30 AM',e:'High Jump',g:'Boys',q:false,a:'Cason Rhoads'},
  {t:'11:40 AM',e:'4x800 Relay',g:'Boys',q:false,a:'Owen Edington, Lawson Moon, Cameron Weston, Kendall Wine'},
  {t:'1:05 PM',e:'100m Finals',g:'Boys',q:true,a:'Asher Edington'},
  {t:'1:15 PM',e:'Shot Put',g:'Boys',q:false,a:'James Chauncey'},
  {t:'3:00 PM',e:'4x100 Relay',g:'Girls',q:true,a:'Lexi Totty, Trysten Sowers, Jaedyn Segrist, Charleigh Bean'},
  {t:'3:20 PM',e:'4x100 Relay',g:'Boys',q:true,a:'Zach Criqui, Asher Edington, Lucas Griffin, James Marcotte'},
  {t:'3:45 PM',e:'400m Dash',g:'Girls',q:true,a:'Trysten Sowers, Charleigh Bean'},
  {t:'4:05 PM',e:'400m Dash',g:'Boys',q:true,a:'Zach Criqui, Cason Rhoads, Owen Edington'},
  {t:'4:50 PM',e:'300m Hurdles',g:'Boys',q:true,a:'Lyric Medina'},
  {t:'5:35 PM',e:'800m Run',g:'Boys',q:false,a:'Kendall Wine'},
  {t:'5:55 PM',e:'200m Dash',g:'Girls',q:true,a:'Trysten Sowers'},
  {t:'6:15 PM',e:'200m Dash',g:'Boys',q:true,a:'Asher Edington'},
  {t:'6:35 PM',e:'4x400 Relay',g:'Girls',q:true,a:'Lexi Totty, Trysten Sowers, Jaedyn Segrist, Charleigh Bean'},
  {t:'7:00 PM',e:'4x400 Relay',g:'Boys',q:true,a:'Zach Criqui, Owen Edington, Cason Rhoads, Lucas Griffin'},
];

function renderL(data,id){
  const el=document.getElementById(id);
  data.forEach(({t,e,g,q,a})=>{
    const gb=g==='Girls'
      ?`<span style="font-family:'Barlow Condensed',sans-serif;font-size:9px;font-weight:700;background:#FBEAF0;color:#72243E;padding:1px 4px;border-radius:3px;">G</span>`
      :`<span style="font-family:'Barlow Condensed',sans-serif;font-size:9px;font-weight:700;background:#E6F1FB;color:#0C447C;padding:1px 4px;border-radius:3px;">B</span>`;
    const ql=q?`<div class="qbadge" style="margin-bottom:2px;">* If Qualified</div>`:'';
    el.innerHTML+=`<div class="lrow${q?' q':''}"><div class="ltime">${t}</div><div>${ql}<div class="levent">${e} ${gb}</div></div><div class="lathletes">${a}</div></div>`;
  });
}
renderL(lfi,'lfri');
renderL(lsa,'lsat');

function showTab(n){
  document.querySelectorAll('.tab').forEach((t,i)=>{
    t.classList.toggle('active',['field','running','scoring','lyndon'][i]===n);
  });
  document.querySelectorAll('.panel').forEach(p=>p.classList.remove('active'));
  document.getElementById('panel-'+n).classList.add('active');
}
</script>
