<!-- ===== LAST 24 HRS SUMMARY BAR (DUMMY DATA) ===== -->
<div class="dca24-wrap">
  <div class="dca24-header">
    <div class="dca24-title">DCA Live Status</div>

    <div class="dca24-meta">
      <span class="dca24-meta-label">Last updated:</span>
      <span class="dca24-meta-value">just now</span>
      <span class="dca24-dot">•</span>
      <button class="dca24-settings">Settings</button>
      <button class="dca24-more">•••</button>
    </div>
  </div>

  <div class="dca24-bar">
    <!-- Completed (24h) -->
    <div class="dca24-seg seg-completed">
      <div class="dca24-seg-head">
        <span class="dca24-icon ok">✓</span>
        <span class="dca24-label">Completed (24 hrs)</span>
      </div>

      <div class="dca24-dots">
        <span></span><span></span><span></span><span></span><span></span>
        <span></span><span></span><span></span><span></span><span></span>
      </div>

      <div class="dca24-value">
        <span class="dca24-num">152</span>
      </div>
    </div>

    <!-- Pending (24h) -->
    <div class="dca24-seg seg-pending">
      <div class="dca24-seg-head">
        <span class="dca24-icon pending">⏳</span>
        <span class="dca24-label">Pending (24 hrs)</span>
      </div>

      <div class="dca24-dots">
        <span></span><span></span><span></span><span></span><span></span>
        <span></span><span></span><span></span><span></span><span></span>
      </div>

      <div class="dca24-value">
        <span class="dca24-num">27</span>
      </div>
    </div>

    <!-- Currently Executing -->
    <div class="dca24-seg seg-current">
      <div class="dca24-seg-head">
        <span class="dca24-icon run">↻</span>
        <span class="dca24-label">Currently Executing</span>
      </div>

      <div class="dca24-subline">
        Transaction #
      </div>

      <div class="dca24-value">
        <span class="dca24-txn">2025111114171</span>
      </div>
    </div>

    <!-- Last Executed -->
    <div class="dca24-seg seg-last">
      <div class="dca24-seg-head">
        <span class="dca24-icon last">⟲</span>
        <span class="dca24-label">Last Executed</span>
      </div>

      <div class="dca24-subline">
        Transaction #
      </div>

      <div class="dca24-value">
        <span class="dca24-txn">2025111115115</span>
      </div>
    </div>
  </div>

  <div class="dca24-foot">
    <span class="dca24-foot-label">Metrics show activity for:</span>
    <span class="dca24-dd">Last 24 hrs <span class="dca24-caret">▾</span></span>
  </div>
</div>




/* ===== LAST 24H SUMMARY BAR ===== */
.dca24-wrap{
  border: 1px solid rgba(0,0,0,.12);
  border-radius: 10px;
  background: linear-gradient(180deg,#ffffff,#fbfbfd);
  padding: 10px 12px 12px;
  box-shadow: 0 10px 30px rgba(0,0,0,.06);
}

/* top header line */
.dca24-header{
  display:flex;
  align-items:center;
  justify-content:space-between;
  gap:12px;
  padding: 4px 2px 10px;
}

.dca24-title{
  font-size: 18px;
  font-weight: 800;
  color:#111827;
  letter-spacing:.2px;
}

.dca24-meta{
  display:flex;
  align-items:center;
  gap:8px;
  font-size: 13px;
  color:#6b7280;
}

.dca24-meta-value{ color:#111827; font-weight:700; }
.dca24-dot{ opacity:.6; }

.dca24-settings,
.dca24-more{
  height: 30px;
  padding: 0 10px;
  border-radius: 8px;
  border: 1px solid rgba(0,0,0,.12);
  background: #f6f7f9;
  font-weight: 700;
  cursor:pointer;
}
.dca24-more{ width:42px; padding:0; }

/* summary bar */
.dca24-bar{
  display:flex;
  gap:0;
  border-radius: 10px;
  overflow:hidden;
  border: 1px solid rgba(0,0,0,.10);
  background: linear-gradient(180deg,#f6f7fb,#f2f3f7);
}

/* segments */
.dca24-seg{
  flex:1;
  padding: 16px 18px 14px;
  position: relative;
  background: rgba(255,255,255,.75);
  border-right: 1px solid rgba(0,0,0,.08);
  min-height: 92px;
}
.dca24-seg:last-child{ border-right:none; }

/* subtle curved separators like the design */
.dca24-seg:after{
  content:"";
  position:absolute;
  right:-18px;
  top:0;
  width:36px;
  height:100%;
  background: radial-gradient(40px 90px at 0% 50%, rgba(255,255,255,.95), rgba(255,255,255,0));
  pointer-events:none;
  opacity:.85;
}

/* segment head */
.dca24-seg-head{
  display:flex;
  align-items:center;
  gap:10px;
  font-weight: 800;
  color:#111827;
}

.dca24-label{
  font-size: 18px;
  font-weight: 800;
}

.dca24-icon{
  width:34px;
  height:34px;
  border-radius: 999px;
  display:inline-flex;
  align-items:center;
  justify-content:center;
  font-weight: 900;
  border: 1px solid rgba(0,0,0,.10);
  background: rgba(255,255,255,.9);
}

/* color cues */
.seg-completed{
  background: linear-gradient(180deg, rgba(34,197,94,.10), rgba(255,255,255,.70));
}
.seg-completed .dca24-icon.ok{ color:#15803d; background: rgba(34,197,94,.15); border-color: rgba(34,197,94,.25); }

.seg-pending{
  background: linear-gradient(180deg, rgba(99,102,241,.10), rgba(255,255,255,.70));
}
.seg-pending .dca24-icon.pending{ color:#4338ca; background: rgba(99,102,241,.14); border-color: rgba(99,102,241,.24); }

.seg-current{
  background: linear-gradient(180deg, rgba(59,130,246,.12), rgba(255,255,255,.70));
}
.seg-current .dca24-icon.run{ color:#1d4ed8; background: rgba(59,130,246,.14); border-color: rgba(59,130,246,.24); }

.seg-last{
  background: linear-gradient(180deg, rgba(148,163,184,.18), rgba(255,255,255,.70));
}
.seg-last .dca24-icon.last{ color:#334155; background: rgba(148,163,184,.20); border-color: rgba(148,163,184,.30); }

/* dotted progress row */
.dca24-dots{
  display:flex;
  gap:6px;
  margin: 12px 0 10px;
}
.dca24-dots span{
  width:8px;
  height:8px;
  border-radius:999px;
  background: rgba(0,0,0,.18);
}

/* values */
.dca24-value{
  display:flex;
  align-items:baseline;
  justify-content:flex-end;
  gap:10px;
}

.dca24-num{
  font-size: 44px;
  font-weight: 900;
  color:#0f172a;
  letter-spacing:.5px;
}

.dca24-subline{
  margin-top: 10px;
  font-size: 12px;
  font-weight: 700;
  color:#6b7280;
}

.dca24-txn{
  font-size: 24px;
  font-weight: 900;
  color:#0f172a;
}

/* footer dropdown line */
.dca24-foot{
  display:flex;
  align-items:center;
  gap:10px;
  padding: 10px 4px 0;
  color:#6b7280;
  font-size: 14px;
}

.dca24-dd{
  display:inline-flex;
  align-items:center;
  gap:8px;
  padding: 6px 10px;
  border-radius: 6px;
  border: 1px solid rgba(0,0,0,.12);
  background: #f6f7f9;
  color:#111827;
  font-weight: 800;
}
.dca24-caret{ opacity:.8; }

/* responsive */
@media (max-width: 1100px){
  .dca24-bar{ flex-direction:column; }
  .dca24-seg{ border-right:none; border-bottom:1px solid rgba(0,0,0,.08); }
  .dca24-seg:last-child{ border-bottom:none; }
  .dca24-seg:after{ display:none; }
}
