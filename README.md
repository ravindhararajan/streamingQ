/* =========================================================
   DCA Live Status - Bank Blue (Square / No Panels)
   Applies to: Summary strip + grid toolbar filter row
   ========================================================= */

/* ---------- TOKENS (Bank Blue family) ---------- */
:root{
  --boa-navy: #0b1f3a;          /* deep bank navy */
  --boa-navy-2: #0e2a4b;        /* slightly lighter */
  --boa-steel: #2a3f57;         /* steel blue-gray */
  --boa-ink: #0a1626;           /* text dark */
  --boa-muted: #5b6f86;         /* secondary text */
  --boa-line: #c9d6e6;          /* separators */
  --boa-line-2: #dbe6f2;        /* soft separators */
  --boa-bg: #f4f7fb;            /* page bg */
  --boa-chip: #e8f0fa;          /* light button bg */
  --boa-focus: #2f69c7;         /* focus blue */
}

/* ---------- BASE ---------- */
.dca24,
.dca-toolbar{
  font-family: "Segoe UI", Roboto, Arial, sans-serif;
  color: var(--boa-ink);
}

/* =========================================================
   SUMMARY STRIP (NO OUTER PANEL)
   ========================================================= */

/* remove wrapper/panel look */
.dca24-wrap{
  background: transparent;
  border: none;
  padding: 0;
  margin: 0 0 10px 0; /* slight space before grid toolbar */
  box-shadow: none;
}

/* header line above summary (optional) */
.dca24-header{
  display:flex;
  align-items:center;
  justify-content:space-between;
  gap:12px;
  padding: 0 0 6px 0;
  border-bottom: 1px solid var(--boa-line-2);
}

.dca24-title{
  font-size: 14px;
  font-weight: 700;
  letter-spacing: .2px;
  color: var(--boa-navy);
  text-transform: none;
}

.dca24-meta{
  display:flex;
  align-items:center;
  gap:10px;
  font-size: 12px;
  color: var(--boa-muted);
}

.dca24-settings,
.dca24-more{
  height: 26px;
  padding: 0 10px;
  border: 1px solid var(--boa-line);
  background: #ffffff;
  color: var(--boa-navy);
  font-weight: 700;
  letter-spacing: .2px;
  cursor:pointer;
  border-radius: 0; /* square */
}

.dca24-more{
  width: 36px;
  padding: 0;
}

/* the summary "strip" container */
.dca24-bar{
  display:flex;
  overflow:hidden;
  border: none;                 /* no border around strip */
  background: transparent;       /* no panel */
}

/* each block (square, with subtle bank gradient) */
.dca24-seg{
  flex:1;
  min-height: 60px;
  padding: 10px 14px 8px;
  position: relative;
  border-right: 1px solid var(--boa-line);
  background: linear-gradient(180deg, #ffffff 0%, #f3f7fc 100%);
  border-radius: 0;             /* square */
}

/* last block: no divider */
.dca24-seg:last-child{
  border-right:none;
}

/* subtle "angled" join removed (keep it clean) */
.dca24-seg:after{ display:none; }

/* segment head row */
.dca24-seg-head{
  display:flex;
  align-items:center;
  gap:8px;
  color: var(--boa-navy);
}

.dca24-label{
  font-size: 12px;
  font-weight: 800;
  letter-spacing: .3px;
  text-transform: none;
}

/* small icon circle but square-ish */
.dca24-icon{
  width: 20px;
  height: 20px;
  display:inline-flex;
  align-items:center;
  justify-content:center;
  font-size: 11px;
  font-weight: 900;
  border: 1px solid var(--boa-line);
  background: #ffffff;
  color: var(--boa-navy-2);
  border-radius: 0; /* square */
}

/* dotted micro-indicator row */
.dca24-dots{
  display:flex;
  gap:4px;
  margin: 6px 0 4px;
}
.dca24-dots span{
  width:5px;
  height:5px;
  background: #bfd0e6;
  border-radius: 0; /* square dots */
}

/* values line */
.dca24-value{
  display:flex;
  align-items:center;
  justify-content:flex-end;
  height: 28px;
}

.dca24-num{
  font-size: 22px;
  font-weight: 800;
  letter-spacing: .2px;
  color: var(--boa-navy);
}

.dca24-subline{
  margin-top: 4px;
  font-size: 11px;
  font-weight: 700;
  color: var(--boa-muted);
}

.dca24-txn{
  font-size: 13px;
  font-weight: 900;
  letter-spacing: .35px;
  color: var(--boa-navy);
}

/* =========================================================
   BANK BLUE GRADIENTS (PER BLOCK) - subtle but "banky"
   ========================================================= */

/* Completed */
.seg-completed{
  background: linear-gradient(180deg, #ffffff 0%, #eef5ff 100%);
  border-top: 2px solid #9bb8e6;
}

/* Pending */
.seg-pending{
  background: linear-gradient(180deg, #ffffff 0%, #f0f4fb 100%);
  border-top: 2px solid #8ea7c9;
}

/* Currently Executing */
.seg-current{
  background: linear-gradient(180deg, #ffffff 0%, #e9f2ff 100%);
  border-top: 2px solid #2f69c7;
}

/* Last Executed */
.seg-last{
  background: linear-gradient(180deg, #ffffff 0%, #f2f5fa 100%);
  border-top: 2px solid #6b7f9a;
}

/* optional subtle live dot for executing */
.seg-current::before{
  content:'';
  position:absolute;
  top:8px;
  right:10px;
  width:6px;
  height:6px;
  background:#2f69c7;
  border-radius: 0; /* square */
  opacity:.85;
}

/* =========================================================
   METRICS FOOTER (TIME RANGE)
   ========================================================= */
.dca24-foot{
  display:flex;
  align-items:center;
  gap:10px;
  padding: 8px 0 0;
  border-top: 1px solid var(--boa-line-2);
  margin-top: 8px;
  color: var(--boa-muted);
  font-size: 12px;
}

.dca24-dd{
  padding: 4px 10px;
  border: 1px solid var(--boa-line);
  background: #ffffff;
  color: var(--boa-navy);
  font-weight: 800;
  letter-spacing:.2px;
  border-radius: 0; /* square */
}

/* =========================================================
   GRID TOOLBAR FILTER ROW (SEARCH + UI/API + AUTOREFRESH + CLEAR)
   ========================================================= */

.dca-toolbar{
  display:flex;
  align-items:center;
  gap:10px;
  padding: 8px 0;
  border-bottom: 1px solid var(--boa-line-2);
}

/* search box wrapper */
.dca-search{
  display:flex;
  align-items:center;
  gap:8px;
  border: 1px solid var(--boa-line);
  background:#ffffff;
  height: 30px;
  padding: 0 10px;
  min-width: 340px;
  border-radius: 0;
}

.dca-search .icon{
  color: var(--boa-muted);
  font-size: 13px;
}

.dca-search input{
  border: none;
  outline: none;
  width: 100%;
  font-size: 12px;
  font-weight: 600;
  color: var(--boa-ink);
  background: transparent;
}

/* small filter chips (Failed / In Progress count) */
.dca-chip{
  height: 30px;
  padding: 0 10px;
  display:inline-flex;
  align-items:center;
  gap:8px;
  border: 1px solid var(--boa-line);
  background: #ffffff;
  color: var(--boa-navy);
  font-size: 12px;
  font-weight: 800;
  letter-spacing: .2px;
  border-radius: 0;
}

.dca-chip .count{
  display:inline-flex;
  align-items:center;
  justify-content:center;
  min-width: 18px;
  height: 18px;
  padding: 0 6px;
  border: 1px solid var(--boa-line);
  background: #f3f7fd;
  color: var(--boa-navy);
  font-size: 11px;
  font-weight: 900;
  border-radius: 0;
}

/* UI / API segmented switch */
.dca-seg-toggle{
  display:inline-flex;
  height: 30px;
  border: 1px solid var(--boa-line);
  background: #ffffff;
  border-radius: 0;
  overflow:hidden;
}

.dca-seg-toggle button{
  height: 30px;
  padding: 0 12px;
  border: none;
  background: transparent;
  font-size: 12px;
  font-weight: 900;
  letter-spacing: .2px;
  color: var(--boa-steel);
  cursor:pointer;
}

.dca-seg-toggle button.active{
  background: linear-gradient(180deg,#2f69c7,#1f4f9b);
  color: #ffffff;
}

/* Auto-refresh switch + label */
.dca-autorefresh{
  display:flex;
  align-items:center;
  gap:8px;
  margin-left: 6px;
  color: var(--boa-navy);
  font-size: 12px;
  font-weight: 800;
}

.dca-autorefresh input[type="checkbox"]{
  width: 34px;
  height: 18px;
  appearance:none;
  border: 1px solid var(--boa-line);
  background: #ffffff;
  position: relative;
  cursor:pointer;
  border-radius: 0;
}

.dca-autorefresh input[type="checkbox"]::after{
  content:'';
  position:absolute;
  top:2px;
  left:2px;
  width: 12px;
  height: 12px;
  background: #9fb4cf;
  border-radius: 0;
  transition: transform .15s ease;
}

.dca-autorefresh input[type="checkbox"]:checked{
  background: #e9f2ff;
  border-color: #93b3e6;
}

.dca-autorefresh input[type="checkbox"]:checked::after{
  background: #2f69c7;
  transform: translateX(16px);
}

/* buttons: Columns / Clear */
.dca-btn{
  height: 30px;
  padding: 0 12px;
  border: 1px solid var(--boa-line);
  background: #ffffff;
  color: var(--boa-navy);
  font-size: 12px;
  font-weight: 900;
  letter-spacing:.2px;
  cursor:pointer;
  border-radius: 0;
}

.dca-btn:hover{
  background: #f3f7fd;
}

.dca-btn:active{
  background: #e9f2ff;
}

/* focus states */
.dca-search:focus-within,
.dca-btn:focus,
.dca24-settings:focus,
.dca24-more:focus,
.dca-seg-toggle button:focus{
  outline: 2px solid rgba(47,105,199,.25);
  outline-offset: 1px;
}
