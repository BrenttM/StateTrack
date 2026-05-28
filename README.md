
<style>
  @import url('https://fonts.googleapis.com/css2?family=Barlow+Condensed:wght@400;600;700;900&family=Barlow:wght@400;500;600&display=swap');
  *{box-sizing:border-box;margin:0;padding:0;}
  :root{--orange:#D4600A;--black:#1a1100;--navy:#1a1a2e;--gold:#ffc800;}
  .sr{font-family:'Barlow',sans-serif;color:var(--color-text-primary);width:100%;}
  .hdr{background:var(--navy);color:#fff;padding:1.25rem;border-radius:var(--border-radius-lg) var(--border-radius-lg) 0 0;position:relative;overflow:hidden;}
  .hdr::before{content:'';position:absolute;top:-20px;right:-20px;width:140px;height:140px;border-radius:50%;border:18px solid rgba(255,200,0,0.1);}
  .hdr-top{display:flex;align-items:flex-start;justify-content:space-between;gap:10px;margin-bottom:10px;}
  .hdr-title{font-family:'Barlow Condensed',sans-serif;font-size:clamp(22px,5vw,30px);font-weight:900;line-height:1.1;text-transform:uppercase;letter-spacing:1px;}
  .hdr-title span{color:var(--gold);}
  .hdr-badge{background:var(--gold);color:var(--navy);font-family:'Barlow Condensed',sans-serif;font-weight:900;font-size:12px;letter-spacing:1.5px;text-transform:uppercase;padding:4px 10px;border-radius:3px;flex-shrink:0;white-space:nowrap;}
  .hdr-meta{display:flex;gap:12px;flex-wrap:wrap;font-size:13px;color:rgba(255,255,255,0.6);}
  .hdr-meta-item{display:flex;align-items:center;gap:5px;}
  .hdr-dot{width:5px;height:5px;border-radius:50%;background:var(--gold);}
  .hdr-note{background:rgba(255,200,0,0.12);border-left:3px solid var(--gold);padding:8px 12px;font-size:12px;color:rgba(255,255,255,0.8);line-height:1.6;margin-top:10px;}
  .tabs{display:flex;background:var(--color-background-secondary);border-bottom:0.5px solid var(--color-border-tertiary);overflow-x:auto;-webkit-overflow-scrolling:touch;scrollbar-width:none;}
  .tabs::-webkit-scrollbar{display:none;}
  .tab{flex:1;min-width:80px;padding:12px 6px;text-align:center;font-family:'Barlow Condensed',sans-serif;font-size:14px;font-weight:700;letter-spacing:0.5px;text-transform:uppercase;cursor:pointer;border:none;background:transparent;color:var(--color-text-secondary);border-bottom:3px solid transparent;white-space:nowrap;}
  .tab.active{color:var(--navy);border-bottom-color:var(--gold);background:var(--color-background-primary);}
  .tab.ltab.active{color:var(--orange);border-bottom-color:var(--orange);}
  .body{background:var(--color-background-primary);}
  .panel{display:none;}.panel.active{display:block;}
  .sec-lbl{font-family:'Barlow Condensed',sans-serif;font-size:12px;font-weight:700;letter-spacing:2px;text-transform:uppercase;color:var(--color-text-secondary);padding:10px 14px 7px;border-bottom:0.5px solid var(--color-border-tertiary);}
  .legend{display:flex;gap:7px;flex-wrap:wrap;padding:9px 14px;border-bottom:0.5px solid var(--color-border-tertiary);align-items:center;}
  .chip{display:inline-block;font-family:'Barlow Condensed',sans-serif;font-weight:700;font-size:12px;padding:3px 6px;border-radius:3px;white-space:nowrap;}
  .lchip{cursor:pointer;padding:4px 10px;font-size:13px;border:1.5px solid transparent;transition:transform 0.1s,box-shadow 0.1s;user-select:none;}
  .lchip:hover{transform:scale(1.08);}
  .lchip.selected{border-color:currentColor;box-shadow:0 0 0 2px rgba(0,0,0,0.15);}
  .c1{background:#E6F1FB;color:#0C447C;}.c2{background:#EAF3DE;color:#27500A;}.c3{background:#FAEEDA;color:#633806;}
  .c4{background:#FBEAF0;color:#72243E;}.c5{background:#EEEDFE;color:#3C3489;}.c6{background:#E1F5EE;color:#085041;}
  .legend-hint{font-size:12px;color:var(--color-text-secondary);margin-left:4px;}
  .tbl-wrap{overflow-x:auto;-webkit-overflow-scrolling:touch;}
  .ftbl{width:100%;border-collapse:collapse;font-size:13px;min-width:560px;}
  .ftbl th{font-family:'Barlow Condensed',sans-serif;font-size:12px;font-weight:700;letter-spacing:1px;text-transform:uppercase;color:var(--color-text-secondary);padding:7px 8px;background:var(--color-background-secondary);border-bottom:0.5px solid var(--color-border-tertiary);text-align:center;}
  .ftbl th:first-child,.ftbl th:nth-child(2),.ftbl th:nth-child(3){text-align:left;}
  .ftbl td{padding:6px 8px;border-bottom:0.5px solid var(--color-border-tertiary);text-align:center;vertical-align:middle;}
  .ftbl td:first-child,.ftbl td:nth-child(2),.ftbl td:nth-child(3){text-align:left;}
  .ftbl tr:hover td{background:var(--color-background-secondary);}
  .ftbl.has-filter tr.no-match td{opacity:0.2;}
  .cell-chip{display:inline-block;font-family:'Barlow Condensed',sans-serif;font-weight:700;font-size:12px;padding:3px 5px;border-radius:3px;white-space:nowrap;transition:transform 0.15s,box-shadow 0.15s;}
  .cell-chip.lit{transform:scale(1.18);box-shadow:0 0 0 2px currentColor;position:relative;}
  .dfri{color:var(--navy);font-weight:700;font-size:11px;background:var(--gold);padding:2px 6px;border-radius:3px;display:inline-block;}
  .dsat{color:#fff;font-weight:700;font-size:11px;background:var(--navy);padding:2px 6px;border-radius:3px;display:inline-block;}
  .sn{font-family:'Barlow Condensed',sans-serif;font-weight:700;font-size:14px;color:var(--color-text-secondary);}
  .rb{padding:10px 14px;}
  .rst{font-family:'Barlow Condensed',sans-serif;font-weight:700;font-size:15px;letter-spacing:1px;text-transform:uppercase;color:var(--color-text-secondary);margin:12px 0 7px;padding-bottom:4px;border-bottom:0.5px solid var(--color-border-tertiary);}
  .r3row{display:flex;gap:8px;flex-wrap:wrap;padding:6px 0;border-bottom:0.5px solid var(--color-border-tertiary);}
  .r3item{background:var(--color-background-secondary);border-radius:var(--border-radius-md);padding:7px 12px;flex:1;min-width:100px;}
  .r3ev{font-size:13px;font-weight:500;}
  .r3t{font-family:'Barlow Condensed',sans-serif;font-size:17px;font-weight:700;color:var(--navy);margin-top:2px;}
  .pgrid{display:grid;grid-template-columns:1fr 100px 100px;gap:0;}
  .pgrid-hdr div{font-size:11px;color:var(--color-text-secondary);font-weight:600;text-transform:uppercase;letter-spacing:1px;padding-bottom:4px;border-bottom:0.5px solid var(--color-border-tertiary);}
  .pgrid-hdr div:nth-child(2),.pgrid-hdr div:nth-child(3){text-align:right;}
  .prow{display:contents;}
  .prow div{padding:6px 0;border-bottom:0.5px solid var(--color-border-tertiary);font-size:13px;}
  .prow div:nth-child(2),.prow div:nth-child(3){font-family:'Barlow Condensed',sans-serif;font-size:14px;font-weight:700;text-align:right;}
  .prow div:nth-child(3){color:var(--color-text-secondary);}
  .score-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:8px;margin-bottom:18px;}
  .score-card{text-align:center;padding:10px 4px;background:var(--color-background-secondary);border-radius:var(--border-radius-md);}
  .score-pts{font-family:'Barlow Condensed',sans-serif;font-size:26px;font-weight:900;color:var(--navy);}
  .score-pl{font-size:11px;color:var(--color-text-secondary);font-weight:600;}
  .info-block{background:var(--color-background-secondary);border-radius:var(--border-radius-md);padding:10px 14px;font-size:13px;margin-bottom:14px;}
  .wc-row{display:flex;justify-content:space-between;padding:7px 0;border-bottom:0.5px solid var(--color-border-tertiary);font-size:13px;}
  .wc-row:last-child{border-bottom:none;}
  .wc-t{font-family:'Barlow Condensed',sans-serif;font-weight:700;font-size:15px;}
  .lhdr{background:var(--black);color:#fff;padding:12px 14px;display:flex;align-items:center;gap:12px;border-bottom:3px solid var(--orange);}
  .lschool{font-family:'Barlow Condensed',sans-serif;font-size:clamp(18px,4vw,24px);font-weight:900;text-transform:uppercase;letter-spacing:1px;}
  .lsub{font-size:12px;color:rgba(255,255,255,0.6);margin-top:2px;}
  .lbadge{background:var(--orange);color:#fff;font-family:'Barlow Condensed',sans-serif;font-weight:900;font-size:12px;letter-spacing:1px;text-transform:uppercase;padding:4px 10px;border-radius:3px;white-space:nowrap;}
  .lnote{padding:8px 14px;background:rgba(212,96,10,0.07);border-bottom:0.5px solid var(--color-border-tertiary);display:flex;align-items:center;gap:8px;flex-wrap:wrap;}
  .qbadge{display:inline-flex;align-items:center;gap:3px;font-size:11px;font-weight:700;color:var(--orange);background:rgba(212,96,10,0.12);border-radius:3px;padding:2px 7px;font-family:'Barlow Condensed',sans-serif;letter-spacing:0.5px;text-transform:uppercase;white-space:nowrap;}

  /* Auto-refresh status bar */
  .refresh-bar{display:flex;align-items:center;justify-content:space-between;padding:6px 14px;background:var(--color-background-secondary);border-bottom:0.5px solid var(--color-border-tertiary);font-size:11px;color:var(--color-text-secondary);}
  .refresh-left{display:flex;align-items:center;gap:6px;}
  .refresh-dot{width:7px;height:7px;border-radius:50%;background:#ccc;flex-shrink:0;transition:background 0.3s;}
  .refresh-dot.syncing{background:var(--orange);animation:pulse 1s infinite;}
  .refresh-dot.live{background:#22c55e;}
  @keyframes pulse{0%,100%{opacity:1;}50%{opacity:0.4;}}
  .refresh-countdown{font-family:'Barlow Condensed',sans-serif;font-size:12px;font-weight:700;}
  .refresh-now-btn{background:transparent;border:1px solid var(--color-border-tertiary);border-radius:4px;padding:2px 8px;font-family:'Barlow Condensed',sans-serif;font-size:11px;font-weight:700;color:var(--color-text-secondary);cursor:pointer;transition:all 0.15s;}
  .refresh-now-btn:hover{border-color:var(--orange);color:var(--orange);}

  /* Meet gallery */
  .meet-gallery{padding:12px 14px;border-bottom:2px solid var(--color-border-tertiary);}
  .meet-gallery-header{display:flex;align-items:center;justify-content:space-between;margin-bottom:10px;}
  .meet-gallery-title{display:flex;align-items:center;gap:8px;}
  .meet-gallery-title h3{font-family:'Barlow Condensed',sans-serif;font-size:16px;font-weight:900;text-transform:uppercase;letter-spacing:1px;color:var(--color-text-primary);}
  .meet-gallery-title .count-pill{background:var(--orange);color:#fff;font-family:'Barlow Condensed',sans-serif;font-weight:700;font-size:11px;padding:1px 7px;border-radius:10px;}
  .add-meet-photo-btn{display:flex;align-items:center;gap:6px;background:var(--orange);color:#fff;border:none;border-radius:7px;padding:7px 14px;cursor:pointer;font-family:'Barlow Condensed',sans-serif;font-size:13px;font-weight:700;letter-spacing:0.5px;transition:opacity 0.15s;}
  .add-meet-photo-btn:hover{opacity:0.85;}
  .meet-photo-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(90px,1fr));gap:8px;}
  .meet-photo-grid.empty{display:flex;align-items:center;justify-content:center;min-height:90px;background:var(--color-background-secondary);border-radius:8px;border:2px dashed var(--color-border-tertiary);}
  .meet-empty-msg{font-size:12px;color:var(--color-text-secondary);text-align:center;padding:16px;}
  .meet-thumb{position:relative;width:100%;padding-bottom:100%;border-radius:7px;overflow:hidden;border:2px solid transparent;transition:border-color 0.15s;cursor:pointer;}
  .meet-thumb:hover{border-color:var(--orange);}
  .meet-thumb img{position:absolute;inset:0;width:100%;height:100%;object-fit:cover;}
  .meet-thumb .del-btn{position:absolute;top:3px;right:3px;background:rgba(0,0,0,0.65);border:none;border-radius:50%;width:22px;height:22px;cursor:pointer;display:flex;align-items:center;justify-content:center;opacity:0;transition:opacity 0.15s;z-index:2;}
  .meet-thumb:hover .del-btn{opacity:1;}

  .lday-hdr{display:flex;align-items:center;gap:10px;padding:10px 14px 7px;border-bottom:0.5px solid var(--color-border-tertiary);background:var(--color-background-secondary);}
  .ldpill{font-family:'Barlow Condensed',sans-serif;font-size:12px;font-weight:700;letter-spacing:1px;text-transform:uppercase;padding:3px 9px;border-radius:3px;}
  .ldfri{background:var(--orange);color:#fff;}
  .ldsat{background:var(--black);color:#fff;}
  .ldtitle{font-family:'Barlow Condensed',sans-serif;font-size:13px;font-weight:700;letter-spacing:1px;text-transform:uppercase;color:var(--color-text-secondary);}
  .lrow{border-bottom:0.5px solid var(--color-border-tertiary);}
  .lrow.q{background:rgba(212,96,10,0.04);}
  .lrow-main{display:grid;grid-template-columns:76px 1fr auto;gap:0;padding:8px 14px;align-items:center;}
  .lrow:hover .lrow-main{background:var(--color-background-secondary);}
  .ltime{font-family:'Barlow Condensed',sans-serif;font-size:15px;font-weight:700;white-space:nowrap;}
  .lrow-center{display:flex;flex-direction:column;gap:2px;}
  .levent{font-size:13px;font-weight:600;line-height:1.4;}
  .lathletes{font-size:12px;color:var(--color-text-secondary);line-height:1.5;}
  .photo-btn{display:flex;align-items:center;gap:5px;background:transparent;border:1.5px solid var(--color-border-tertiary);border-radius:6px;padding:5px 10px;cursor:pointer;font-family:'Barlow Condensed',sans-serif;font-size:12px;font-weight:700;color:var(--color-text-secondary);transition:all 0.15s;white-space:nowrap;margin-left:8px;}
  .photo-btn:hover{border-color:var(--orange);color:var(--orange);}
  .photo-btn.has-photos{border-color:var(--orange);color:var(--orange);background:rgba(212,96,10,0.07);}
  .photo-btn.open{border-color:var(--orange);color:var(--orange);background:rgba(212,96,10,0.12);}
  .photo-count{background:var(--orange);color:#fff;border-radius:10px;padding:0 5px;font-size:10px;line-height:16px;display:inline-block;}
  .chevron{transition:transform 0.2s;display:inline-flex;}
  .photo-btn.open .chevron{transform:rotate(180deg);}
  .photo-strip{display:none;padding:8px 14px 10px 90px;gap:8px;flex-wrap:wrap;background:var(--color-background-secondary);border-top:0.5px solid var(--color-border-tertiary);}
  .photo-strip.open{display:flex;}
  .photo-thumb{position:relative;width:80px;height:80px;border-radius:6px;overflow:hidden;flex-shrink:0;border:2px solid transparent;transition:border-color 0.15s;cursor:pointer;}
  .photo-thumb:hover{border-color:var(--orange);}
  .photo-thumb img{width:100%;height:100%;object-fit:cover;display:block;}
  .photo-thumb .del-btn{position:absolute;top:2px;right:2px;background:rgba(0,0,0,0.65);border:none;border-radius:50%;width:20px;height:20px;cursor:pointer;display:flex;align-items:center;justify-content:center;opacity:0;transition:opacity 0.15s;}
  .photo-thumb:hover .del-btn{opacity:1;}
  .photo-add-thumb{width:80px;height:80px;border-radius:6px;border:2px dashed var(--color-border-tertiary);display:flex;flex-direction:column;align-items:center;justify-content:center;cursor:pointer;gap:4px;transition:border-color 0.15s,background 0.15s;flex-shrink:0;}
  .photo-add-thumb:hover{border-color:var(--orange);background:rgba(212,96,10,0.05);}
  .photo-add-thumb span{font-size:10px;color:var(--color-text-secondary);font-family:'Barlow Condensed',sans-serif;font-weight:700;letter-spacing:0.5px;}
  .lightbox{position:fixed;inset:0;background:rgba(0,0,0,0.92);z-index:9999;display:none;align-items:center;justify-content:center;padding:16px;}
  .lightbox.open{display:flex;}
  .lightbox img{max-width:100%;max-height:90vh;border-radius:8px;object-fit:contain;}
  .lightbox-close{position:fixed;top:16px;right:16px;background:rgba(255,255,255,0.15);border:none;border-radius:50%;width:36px;height:36px;cursor:pointer;display:flex;align-items:center;justify-content:center;color:#fff;font-size:20px;}
  .ftr{background:var(--navy);color:rgba(255,255,255,0.7);font-size:12px;padding:10px 14px;line-height:1.6;border-radius:0 0 var(--border-radius-lg) var(--border-radius-lg);}
  .ftr strong{color:var(--gold);}
  .award-note{margin-top:10px;padding:9px;background:rgba(255,200,0,0.1);border-radius:var(--border-radius-md);border-left:3px solid var(--gold);}
  .award-title{font-size:12px;font-weight:600;margin-bottom:2px;}
  .award-sub{font-size:12px;color:var(--color-text-secondary);}
  @media(max-width:480px){
    .lrow-main{grid-template-columns:68px 1fr auto;}
    .photo-strip{padding-left:14px;}
    .pgrid{grid-template-columns:1fr 90px 90px;}
    .meet-photo-grid{grid-template-columns:repeat(auto-fill,minmax(75px,1fr));}
  }
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
    <div class="hdr-note">Schedule is a guide - events may run ahead without delay. Fri Session 1: 4A-5A-6A · Session 2: 1A-2A-3A · Sat: 1A-2A-3A-4A-5A-6A.</div>
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
        <div class="rst" style="margin-top:14px;"><span class="dfri">Fri</span> Prelims - 4A/5A/6A &amp; 1A/2A/3A</div>
        <div class="pgrid pgrid-hdr"><div>Event</div><div style="text-align:right;">4A/5A/6A</div><div style="text-align:right;">1A/2A/3A</div></div>
        <div class="pgrid" id="fpgrid"></div>
        <div style="font-size:12px;color:var(--color-text-secondary);padding:5px 0;font-style:italic;">Prelims concluded: 1:40 pm (4A/5A/6A) · 6:50 pm (1A/2A/3A)</div>
        <div class="rst" style="margin-top:14px;"><span class="dfri">Fri</span> 3200m Finals - 1A 2A 3A</div>
        <div class="r3row">
          <div class="r3item"><div class="r3ev">1A Girls &amp; Boys</div><div class="r3t">7:00-7:20 pm</div></div>
          <div class="r3item"><div class="r3ev">2A Girls &amp; Boys</div><div class="r3t">7:20-7:40 pm</div></div>
          <div class="r3item"><div class="r3ev">3A Girls &amp; Boys</div><div class="r3t">7:40-8:00 pm</div></div>
        </div>
        <div class="rst" style="margin-top:14px;"><span class="dsat">Sat</span> 100m Prelims - All Classes</div>
        <div class="r3row">
          <div class="r3item"><div class="r3ev">Girls 100m Dash</div><div class="r3t">8:30 am</div></div>
          <div class="r3item"><div class="r3ev">Boys 100m Dash</div><div class="r3t">9:00 am</div></div>
        </div>
        <div class="rst" style="margin-top:14px;"><span class="dsat">Sat</span> Finals</div>
        <div id="sfgrid"></div>
        <div class="award-note"><div class="award-title">Team Award Presentations</div><div class="award-sub">Following the last race. Only coaches &amp; athletes on the infield.</div></div>
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
        <div class="info-block" style="font-size:13px;color:var(--color-text-secondary);line-height:1.7;">With all six classes at the same site, classes 1A, 2A, and 3A will have the earlier sessions. Running events will not be held back if proceeding ahead of schedule.</div>
      </div>
    </div>

    <div id="panel-lyndon" class="panel">
      <div class="lhdr">
        <div style="flex:1;"><div class="lschool">Lyndon High School</div><div class="lsub">May 29-30, 2026 · State Track &amp; Field</div></div>
        <div class="lbadge">Tigers</div>
      </div>
      <div class="lnote">
        <span class="qbadge">* If Qualified</span>
        <span style="font-size:12px;color:var(--color-text-secondary);">Requires qualifying from Day 1 prelims</span>
        <span style="font-size:11px;color:var(--color-text-secondary);margin-left:auto;">📸 Photos shared with all viewers</span>
      </div>

      <!-- Auto-refresh status bar -->
      <div class="refresh-bar">
        <div class="refresh-left">
          <div class="refresh-dot live" id="refresh-dot"></div>
          <span id="refresh-status">Photos refresh in <span class="refresh-countdown" id="refresh-countdown">3:00</span></span>
        </div>
        <button class="refresh-now-btn" onclick="refreshNow()">Refresh now</button>
      </div>

      <!-- General meet gallery -->
      <div class="meet-gallery">
        <div class="meet-gallery-header">
          <div class="meet-gallery-title">
            <h3>Meet Photos</h3>
            <span class="count-pill" id="meet-count" style="display:none;">0</span>
          </div>
          <button class="add-meet-photo-btn" onclick="triggerMeetUpload()">
            <svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="3" width="18" height="18" rx="2"/><circle cx="8.5" cy="8.5" r="1.5"/><polyline points="21 15 16 10 5 21"/></svg>
            Add Photos
          </button>
        </div>
        <div class="meet-photo-grid empty" id="meet-grid">
          <div class="meet-empty-msg" id="meet-empty">No photos yet - be the first to add some!</div>
        </div>
      </div>

      <div class="lday-hdr"><span class="ldpill ldfri">Friday</span><span class="ldtitle">May 29 - Prelims &amp; Field Events</span></div>
      <div id="lfri"></div>
      <div class="lday-hdr" style="margin-top:4px;"><span class="ldpill ldsat">Saturday</span><span class="ldtitle">May 30 - Finals</span></div>
      <div id="lsat"></div>
    </div>
  </div>

  <div class="ftr"><strong>Field events</strong> run simultaneously across all venues. See the Field tab for full session assignments.</div>
</div>

<div class="lightbox" id="lightbox" onclick="closeLightbox()">
  <button class="lightbox-close" onclick="closeLightbox()">✕</button>
  <img id="lightbox-img" src="" alt="">
</div>
<input type="file" id="file-input" accept="image/*" multiple style="display:none;">
<input type="file" id="meet-file-input" accept="image/*" multiple style="display:none;">

<script>
const SUPA_URL = 'https://ayphnnlrhyyzbdskxris.supabase.co';
const SUPA_KEY = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6ImF5cGhubmxyaHl5emJkc2t4cmlzIiwicm9sZSI6ImFub24iLCJpYXQiOjE3Nzk5ODQ2MzIsImV4cCI6MjA5NTU2MDYzMn0.FtHZFgUW5rggdhJjONSyruhdivhMHZyyc4hzhl3_nTc';
const BUCKET = 'event-photos';
const MEET_ROW_ID = 'general-meet';
const REFRESH_SECS = 180;
const hdrs = { 'apikey': SUPA_KEY, 'Authorization': `Bearer ${SUPA_KEY}` };

async function fetchPhotos(rowId) {
  const res = await fetch(`${SUPA_URL}/rest/v1/event_photos?row_id=eq.${encodeURIComponent(rowId)}&order=uploaded_at.asc`, { headers:{...hdrs,'Content-Type':'application/json'} });
  return res.ok ? await res.json() : [];
}
async function insertPhotoRecord(rowId, path) {
  await fetch(`${SUPA_URL}/rest/v1/event_photos`, { method:'POST', headers:{...hdrs,'Content-Type':'application/json','Prefer':'return=minimal'}, body:JSON.stringify({row_id:rowId,storage_path:path}) });
}
async function deletePhotoRecord(id, path) {
  await fetch(`${SUPA_URL}/rest/v1/event_photos?id=eq.${id}`, { method:'DELETE', headers:hdrs });
  await fetch(`${SUPA_URL}/storage/v1/object/${BUCKET}/${encodeURIComponent(path)}`, { method:'DELETE', headers:hdrs });
}
function publicUrl(path) { return `${SUPA_URL}/storage/v1/object/public/${BUCKET}/${encodeURIComponent(path)}`; }

// ---- Field table ----
const cmap={'1A':'c1','2A':'c2','3A':'c3','4A':'c4','5A':'c5','6A':'c6'};
const fd=[[1,'Fri','7:45 am','5A B','6A G','4A B','5A G','4A G','6A B','5A G','6A B','4A G'],[2,'Fri','9:30 am','4A G','6A B','','','','','5A B','4A G','4A B'],[3,'Fri','11:15 am','4A B','5A B','6A G','4A G','6A G','5A B','4A B','6A G','5A G'],[4,'Fri','1:00 pm','1A B','5A G','','','','','1A G','3A B','5A B'],[5,'Fri','2:45 pm','1A G','3A G','1A B','2A G','1A G','2A B','2A G','1A B','3A B'],[6,'Fri','4:30 pm','2A B','3A B','','','','','3A G','2A B','1A B'],[7,'Fri','6:15 pm','3A G','2A G','3A B','1A G','2A G','1A B','3A B','1A G','2A B'],[8,'Sat','8:00 am','6A B','2A B','5A B','3A G','5A G','3A B','6A G','5A B','2A G'],[9,'Sat','9:45 am','6A G','1A G','','','','','6A B','5A G','1A G'],[10,'Sat','11:30 am','5A G','1A B','6A B','2A B','3A G','4A B','4A G','3A G','6A G'],[11,'Sat','1:15 pm','3A B','4A G','','','','','2A B','4A B','6A B'],[12,'Sat','3:00 pm','2A G','4A B','','','','','1A B','2A G','3A G']];
let activeFilter=null;
function makeChip(v){if(!v)return'<span style="color:var(--color-text-secondary);font-size:11px;">-</span>';const m=v.match(/^(\d+A)\s([BG])$/);if(!m)return v;return`<span class="cell-chip ${cmap[m[1]]}" data-class="${m[1]}">${m[1]} ${m[2]}</span>`;}
const tb=document.getElementById('ftbody');
fd.forEach(([s,d,t,...cells])=>{const db=d==='Fri'?`<span class="dfri">Fri</span>`:`<span class="dsat">Sat</span>`;const classes=[...new Set(cells.map(c=>{const m=c.match(/^(\d+A)/);return m?m[1]:'';}).filter(Boolean))].join(' ');tb.innerHTML+=`<tr data-classes="${classes}"><td class="sn">${s}</td><td>${db}</td><td style="white-space:nowrap;font-size:12px;">${t}</td>${cells.map(c=>`<td>${makeChip(c)}</td>`).join('')}</tr>`;});
function toggleFilter(cls,el){const table=document.getElementById('ftbl');if(activeFilter===cls){activeFilter=null;el.classList.remove('selected');table.classList.remove('has-filter');document.querySelectorAll('#ftbody tr').forEach(r=>r.classList.remove('has-match','no-match'));document.querySelectorAll('#ftbody .cell-chip').forEach(c=>c.classList.remove('lit'));}else{document.querySelectorAll('.lchip.selected').forEach(c=>c.classList.remove('selected'));activeFilter=cls;el.classList.add('selected');table.classList.add('has-filter');document.querySelectorAll('#ftbody tr').forEach(r=>{const match=(r.getAttribute('data-classes')||'').split(' ').includes(cls);r.classList.toggle('has-match',match);r.classList.toggle('no-match',!match);});document.querySelectorAll('#ftbody .cell-chip').forEach(c=>{c.classList.toggle('lit',c.getAttribute('data-class')===cls);});}}
const fp=[['Girls 100m High Hurdles','9:00 am','2:10 pm'],['Boys 110m High Hurdles','9:20 am','2:30 pm'],['Girls 4x100 Relay','9:45 am','2:55 pm'],['Boys 4x100 Relay','10:05 am','3:15 pm'],['Girls 400m Dash','10:25 am','3:35 pm'],['Boys 400m Dash','10:45 am','3:55 pm'],['Girls 300m Low Hurdles','11:10 am','4:20 pm'],['Boys 300m Int. Hurdles','11:35 am','4:45 pm'],['Girls 200m Dash','12:05 pm','5:15 pm'],['Boys 200m Dash','12:25 pm','5:35 pm'],['Girls 4x400 Relay','12:45 pm','5:55 pm'],['Boys 4x400 Relay','1:15 pm','6:25 pm']];
const fpg=document.getElementById('fpgrid');fp.forEach(([e,t1,t2])=>{fpg.innerHTML+=`<div class="prow"><div style="font-size:13px;font-weight:500;">${e}</div><div>${t1}</div><div>${t2}</div></div>`;});
const sf=[['Girls 100m High Hurdles','9:30 am'],['Boys 110m High Hurdles','10:00 am'],['Girls 4x800 Relay','10:30 am'],['Boys 4x800 Relay','11:40 am'],['* Hall of Fame Inductions',''],['Girls 100m Dash','12:45 pm'],['Boys 100m Dash','1:05 pm'],['Girls 1600m Run','1:25 pm'],['Boys 1600m Run','2:10 pm'],['Girls 4x100 Relay','3:00 pm'],['Boys 4x100 Relay','3:20 pm'],['Girls 400m Dash','3:45 pm'],['Boys 400m Dash','4:05 pm'],['Girls 300m Low Hurdles','4:30 pm'],['Boys 300m Int. Hurdles','4:50 pm'],['Girls 800m Run','5:10 pm'],['Boys 800m Run','5:35 pm'],['Girls 200m Dash','5:55 pm'],['Boys 200m Dash','6:15 pm'],['Girls 4x400 Relay','6:35 pm'],['Boys 4x400 Relay','7:00 pm']];
const sfg=document.getElementById('sfgrid');sf.forEach(([e,t])=>{if(e.startsWith('*')){sfg.innerHTML+=`<div style="text-align:center;padding:6px;font-size:12px;color:var(--color-text-secondary);font-style:italic;border-bottom:0.5px solid var(--color-border-tertiary);">${e}</div>`;}else{sfg.innerHTML+=`<div style="display:flex;justify-content:space-between;align-items:center;padding:6px 0;border-bottom:0.5px solid var(--color-border-tertiary);"><span style="font-size:13px;font-weight:500;">${e}</span><span style="font-family:'Barlow Condensed',sans-serif;font-size:15px;font-weight:700;">${t}</span></div>`;}});

// ---- Auto-refresh countdown ----
let countdownSecs = REFRESH_SECS;
let countdownInterval = null;
let refreshInterval = null;

function startCountdown() {
  countdownSecs = REFRESH_SECS;
  updateCountdownDisplay();
  clearInterval(countdownInterval);
  countdownInterval = setInterval(() => {
    countdownSecs--;
    updateCountdownDisplay();
    if (countdownSecs <= 0) {
      clearInterval(countdownInterval);
    }
  }, 1000);
}

function updateCountdownDisplay() {
  const m = Math.floor(countdownSecs / 60);
  const s = countdownSecs % 60;
  const el = document.getElementById('refresh-countdown');
  if (el) el.textContent = `${m}:${String(s).padStart(2,'0')}`;
}

function setSyncing(on) {
  const dot = document.getElementById('refresh-dot');
  const status = document.getElementById('refresh-status');
  if (!dot || !status) return;
  if (on) {
    dot.className = 'refresh-dot syncing';
    status.innerHTML = 'Checking for new photos...';
  } else {
    dot.className = 'refresh-dot live';
    status.innerHTML = `Photos refresh in <span class="refresh-countdown" id="refresh-countdown">${Math.floor(countdownSecs/60)}:${String(countdownSecs%60).padStart(2,'0')}</span>`;
  }
}

async function refreshNow() {
  setSyncing(true);
  await reloadAllPhotos();
  setSyncing(false);
  startCountdown();
}

function startAutoRefresh() {
  clearInterval(refreshInterval);
  startCountdown();
  refreshInterval = setInterval(async () => {
    setSyncing(true);
    await reloadAllPhotos();
    setSyncing(false);
    startCountdown();
  }, REFRESH_SECS * 1000);
}

// ---- Photo reload (diff-based — only adds new, doesn't disturb existing) ----
const knownPhotos = {}; // rowId -> Set of record IDs already rendered

async function reloadAllPhotos() {
  // Meet gallery
  await reloadRowPhotos(MEET_ROW_ID, 'meet');
  // Event rows
  const allRows = [...lfi.map((_,i)=>`fri-${i}`), ...lsa.map((_,i)=>`sat-${i}`)];
  for (const rowId of allRows) {
    await reloadRowPhotos(rowId, 'event');
  }
}

async function reloadRowPhotos(rowId, type) {
  if (!knownPhotos[rowId]) knownPhotos[rowId] = new Set();
  const records = await fetchPhotos(rowId);
  // Add only genuinely new photos
  for (const rec of records) {
    if (!knownPhotos[rowId].has(rec.id)) {
      knownPhotos[rowId].add(rec.id);
      if (type === 'meet') {
        addMeetThumb(rec.storage_path, rec.id);
      } else {
        addThumb(rowId, rec.storage_path, rec.id);
        updateBtn(rowId);
      }
    }
  }
  if (type === 'meet') updateMeetCount();
}

// ---- Meet gallery ----
function triggerMeetUpload() {
  document.getElementById('meet-file-input').value = '';
  document.getElementById('meet-file-input').click();
}
document.getElementById('meet-file-input').addEventListener('change', async function() {
  if (!this.files.length) return;
  for (const file of Array.from(this.files)) {
    const ext = file.name.split('.').pop();
    const path = `${MEET_ROW_ID}/${Date.now()}-${Math.random().toString(36).slice(2)}.${ext}`;
    const res = await fetch(`${SUPA_URL}/storage/v1/object/${BUCKET}/${encodeURIComponent(path)}`, { method:'POST', headers:{...hdrs,'Content-Type':file.type}, body:file });
    if (res.ok) {
      await insertPhotoRecord(MEET_ROW_ID, path);
      const recs = await fetchPhotos(MEET_ROW_ID);
      const newest = recs.find(r => r.storage_path === path);
      if (newest && !knownPhotos[MEET_ROW_ID]?.has(newest.id)) {
        if (!knownPhotos[MEET_ROW_ID]) knownPhotos[MEET_ROW_ID] = new Set();
        knownPhotos[MEET_ROW_ID].add(newest.id);
        addMeetThumb(path, newest.id);
      }
    }
  }
  updateMeetCount();
});

function addMeetThumb(storagePath, recordId) {
  const grid = document.getElementById('meet-grid');
  const empty = document.getElementById('meet-empty');
  if (empty) { grid.classList.remove('empty'); empty.remove(); }
  const url = publicUrl(storagePath);
  const thumb = document.createElement('div');
  thumb.className = 'meet-thumb';
  thumb.dataset.recordId = recordId;
  thumb.innerHTML = `<img src="${url}" alt="meet photo" onclick="openLightbox('${url}')"><button class="del-btn" onclick="removeMeetThumb('${recordId}','${storagePath}',this)" title="Remove"><svg width="10" height="10" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="3" stroke-linecap="round"><line x1="18" y1="6" x2="6" y2="18"/><line x1="6" y1="6" x2="18" y2="18"/></svg></button>`;
  grid.appendChild(thumb);
}
async function removeMeetThumb(recordId, path, btn) {
  const thumb = btn.closest('.meet-thumb');
  thumb.style.opacity = '0.4';
  await deletePhotoRecord(recordId, path);
  if (knownPhotos[MEET_ROW_ID]) knownPhotos[MEET_ROW_ID].delete(recordId);
  thumb.remove();
  const grid = document.getElementById('meet-grid');
  if (!grid.querySelectorAll('.meet-thumb').length) { grid.classList.add('empty'); grid.innerHTML='<div class="meet-empty-msg" id="meet-empty">No photos yet - be the first to add some!</div>'; }
  updateMeetCount();
}
function updateMeetCount() {
  const grid = document.getElementById('meet-grid');
  const count = grid.querySelectorAll('.meet-thumb').length;
  const pill = document.getElementById('meet-count');
  if (count > 0) { pill.textContent = count; pill.style.display = 'inline-block'; } else { pill.style.display = 'none'; }
}

// ---- Event rows ----
const lfi=[{t:'2:30 PM',e:'110m Hurdles',g:'Boys',q:false,a:'Lyric Medina'},{t:'2:45 PM',e:'High Jump',g:'Girls',q:false,a:'Phoebe Wright'},{t:'2:45 PM',e:'Pole Vault',g:'Boys',q:false,a:'Lucas Griffin'},{t:'2:55 PM',e:'4x100 Relay',g:'Girls',q:false,a:'Lexi Totty, Trysten Sowers, Jaedyn Segrist, Charleigh Bean'},{t:'3:15 PM',e:'4x100 Relay',g:'Boys',q:false,a:'Zach Criqui, Asher Edington, Lucas Griffin, James Marcotte'},{t:'3:35 PM',e:'400m Dash',g:'Girls',q:false,a:'Trysten Sowers, Charleigh Bean'},{t:'3:55 PM',e:'400m Dash',g:'Boys',q:false,a:'Zach Criqui, Cason Rhoads, Owen Edington'},{t:'4:45 PM',e:'300m Hurdles',g:'Boys',q:false,a:'Lyric Medina'},{t:'5:15 PM',e:'200m Dash',g:'Girls',q:false,a:'Trysten Sowers'},{t:'5:35 PM',e:'200m Dash',g:'Boys',q:false,a:'Asher Edington'},{t:'5:55 PM',e:'4x400 Relay',g:'Girls',q:false,a:'Lexi Totty, Trysten Sowers, Jaedyn Segrist, Charleigh Bean'},{t:'6:15 PM',e:'Pole Vault',g:'Girls',q:false,a:'Lexi Totty'},{t:'6:15 PM',e:'Javelin',g:'Boys',q:false,a:'Lyric Medina'},{t:'6:25 PM',e:'4x400 Relay',g:'Boys',q:false,a:'Zach Criqui, Owen Edington, Cason Rhoads, Lucas Griffin'}];
const lsa=[{t:'8:00 AM',e:'Triple Jump',g:'Boys',q:false,a:'James Marcotte, Cason Rhoads'},{t:'9:00 AM',e:'100m Prelims',g:'Boys',q:false,a:'Asher Edington'},{t:'10:00 AM',e:'110m Hurdles Finals',g:'Boys',q:true,a:'Lyric Medina'},{t:'11:30 AM',e:'High Jump',g:'Boys',q:false,a:'Cason Rhoads'},{t:'11:40 AM',e:'4x800 Relay',g:'Boys',q:false,a:'Owen Edington, Lawson Moon, Cameron Weston, Kendall Wine'},{t:'1:05 PM',e:'100m Finals',g:'Boys',q:true,a:'Asher Edington'},{t:'1:15 PM',e:'Shot Put',g:'Boys',q:false,a:'James Chauncey'},{t:'3:00 PM',e:'4x100 Relay',g:'Girls',q:true,a:'Lexi Totty, Trysten Sowers, Jaedyn Segrist, Charleigh Bean'},{t:'3:20 PM',e:'4x100 Relay',g:'Boys',q:true,a:'Zach Criqui, Asher Edington, Lucas Griffin, James Marcotte'},{t:'3:45 PM',e:'400m Dash',g:'Girls',q:true,a:'Trysten Sowers, Charleigh Bean'},{t:'4:05 PM',e:'400m Dash',g:'Boys',q:true,a:'Zach Criqui, Cason Rhoads, Owen Edington'},{t:'4:50 PM',e:'300m Hurdles',g:'Boys',q:true,a:'Lyric Medina'},{t:'5:35 PM',e:'800m Run',g:'Boys',q:false,a:'Kendall Wine'},{t:'5:55 PM',e:'200m Dash',g:'Girls',q:true,a:'Trysten Sowers'},{t:'6:15 PM',e:'200m Dash',g:'Boys',q:true,a:'Asher Edington'},{t:'6:35 PM',e:'4x400 Relay',g:'Girls',q:true,a:'Lexi Totty, Trysten Sowers, Jaedyn Segrist, Charleigh Bean'},{t:'7:00 PM',e:'4x400 Relay',g:'Boys',q:true,a:'Zach Criqui, Owen Edington, Cason Rhoads, Lucas Griffin'}];

let pendingRowId = null;

function renderLyndon(data, containerId, prefix) {
  const el = document.getElementById(containerId);
  data.forEach(({t,e,g,q,a}, i) => {
    const rowId = `${prefix}-${i}`;
    const gb = g==='Girls' ? `<span style="font-family:'Barlow Condensed',sans-serif;font-size:11px;font-weight:700;background:#FBEAF0;color:#72243E;padding:2px 5px;border-radius:3px;">G</span>` : `<span style="font-family:'Barlow Condensed',sans-serif;font-size:11px;font-weight:700;background:#E6F1FB;color:#0C447C;padding:2px 5px;border-radius:3px;">B</span>`;
    const ql = q ? `<div class="qbadge" style="margin-bottom:3px;">* If Qualified</div>` : '';
    el.innerHTML += `<div class="lrow${q?' q':''}" id="row-${rowId}"><div class="lrow-main"><div class="ltime">${t}</div><div class="lrow-center">${ql}<div class="levent">${e} ${gb}</div><div class="lathletes">${a}</div></div><button class="photo-btn" id="btn-${rowId}" onclick="toggleStrip('${rowId}')"><svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="3" width="18" height="18" rx="2"/><circle cx="8.5" cy="8.5" r="1.5"/><polyline points="21 15 16 10 5 21"/></svg><span class="btn-label">Photos</span><span class="chevron"><svg width="11" height="11" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="6 9 12 15 18 9"/></svg></span></button></div><div class="photo-strip" id="strip-${rowId}"><div class="photo-add-thumb" onclick="triggerUpload('${rowId}')"><svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="var(--color-text-secondary)" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="12" y1="5" x2="12" y2="19"/><line x1="5" y1="12" x2="19" y2="12"/></svg><span>Add</span></div></div></div>`;
  });
}
renderLyndon(lfi,'lfri','fri');
renderLyndon(lsa,'lsat','sat');

function toggleStrip(rowId) {
  const strip = document.getElementById(`strip-${rowId}`);
  const btn = document.getElementById(`btn-${rowId}`);
  const isOpen = strip.classList.contains('open');
  strip.classList.toggle('open',!isOpen);
  btn.classList.toggle('open',!isOpen);
}
function triggerUpload(rowId) {
  pendingRowId = rowId;
  document.getElementById('file-input').value = '';
  document.getElementById('file-input').click();
}
document.getElementById('file-input').addEventListener('change', async function() {
  if (!pendingRowId || !this.files.length) return;
  const rowId = pendingRowId;
  for (const file of Array.from(this.files)) {
    const ext = file.name.split('.').pop();
    const path = `${rowId}/${Date.now()}-${Math.random().toString(36).slice(2)}.${ext}`;
    const res = await fetch(`${SUPA_URL}/storage/v1/object/${BUCKET}/${encodeURIComponent(path)}`, { method:'POST', headers:{...hdrs,'Content-Type':file.type}, body:file });
    if (res.ok) {
      await insertPhotoRecord(rowId, path);
      const recs = await fetchPhotos(rowId);
      const newest = recs.find(r => r.storage_path === path);
      if (newest && !knownPhotos[rowId]?.has(newest.id)) {
        if (!knownPhotos[rowId]) knownPhotos[rowId] = new Set();
        knownPhotos[rowId].add(newest.id);
        addThumb(rowId, path, newest.id);
        updateBtn(rowId);
      }
    }
  }
});

function addThumb(rowId, storagePath, recordId) {
  const strip = document.getElementById(`strip-${rowId}`);
  if (!strip) return;
  const addBtn = strip.querySelector('.photo-add-thumb');
  const url = publicUrl(storagePath);
  const thumb = document.createElement('div');
  thumb.className = 'photo-thumb';
  thumb.dataset.recordId = recordId;
  thumb.innerHTML = `<img src="${url}" alt="event photo" onclick="openLightbox('${url}')"><button class="del-btn" onclick="removeThumb('${rowId}','${recordId}','${storagePath}',this)" title="Remove"><svg width="10" height="10" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="3" stroke-linecap="round"><line x1="18" y1="6" x2="6" y2="18"/><line x1="6" y1="6" x2="18" y2="18"/></svg></button>`;
  strip.insertBefore(thumb, addBtn);
}
async function removeThumb(rowId, recordId, path, btn) {
  const thumb = btn.closest('.photo-thumb');
  thumb.style.opacity = '0.4';
  await deletePhotoRecord(recordId, path);
  if (knownPhotos[rowId]) knownPhotos[rowId].delete(recordId);
  thumb.remove();
  updateBtn(rowId);
}
function updateBtn(rowId) {
  const strip = document.getElementById(`strip-${rowId}`);
  const count = strip.querySelectorAll('.photo-thumb').length;
  const btn = document.getElementById(`btn-${rowId}`);
  if (!btn) return;
  const chevron = `<span class="chevron"><svg width="11" height="11" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="6 9 12 15 18 9"/></svg></span>`;
  const cam = `<svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="3" width="18" height="18" rx="2"/><circle cx="8.5" cy="8.5" r="1.5"/><polyline points="21 15 16 10 5 21"/></svg>`;
  const isOpen = btn.classList.contains('open');
  btn.classList.toggle('has-photos', count > 0);
  btn.innerHTML = count > 0 ? `${cam} <span class="btn-label">Photos <span class="photo-count">${count}</span></span> ${chevron}` : `${cam} <span class="btn-label">Photos</span> ${chevron}`;
  btn.classList.toggle('open', isOpen);
}

function openLightbox(url) { document.getElementById('lightbox-img').src=url; document.getElementById('lightbox').classList.add('open'); }
function closeLightbox() { document.getElementById('lightbox').classList.remove('open'); document.getElementById('lightbox-img').src=''; }

// ---- Initial load + auto-refresh ----
let photosLoaded = false;
async function initialLoad() {
  setSyncing(true);
  await reloadAllPhotos();
  setSyncing(false);
  startAutoRefresh();
}

function showTab(n) {
  document.querySelectorAll('.tab').forEach((t,i)=>{t.classList.toggle('active',['field','running','scoring','lyndon'][i]===n);});
  document.querySelectorAll('.panel').forEach(p=>p.classList.remove('active'));
  document.getElementById('panel-'+n).classList.add('active');
  if (n==='lyndon' && !photosLoaded) { photosLoaded=true; initialLoad(); }
}
</script>
