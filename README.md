/* ===== FINTECH COMPACT SUMMARY ===== */

.dca24-wrap{
  border: 1px solid #d8dde6;
  border-radius: 8px;
  background: linear-gradient(180deg,#f8fafc,#f3f6f9);
  padding: 6px 10px 8px;
  box-shadow: 0 4px 10px rgba(15,23,42,.04);
}

/* header */
.dca24-header{
  display:flex;
  align-items:center;
  justify-content:space-between;
  padding: 2px 2px 6px;
}

.dca24-title{
  font-size: 16px;
  font-weight: 700;
  color:#1e293b; /* slate-800 */
}

.dca24-meta{
  display:flex;
  align-items:center;
  gap:8px;
  font-size: 12px;
  color:#64748b; /* slate-500 */
}

.dca24-settings,
.dca24-more{
  height: 26px;
  padding: 0 8px;
  border-radius: 6px;
  border: 1px solid #d1d7e0;
  background: #eef2f6;
  font-weight: 600;
  color:#334155;
}

/* summary bar */
.dca24-bar{
  display:flex;
  border-radius: 8px;
  overflow:hidden;
  border: 1px solid #d8dde6;
  background: linear-gradient(180deg,#eef2f6,#e8edf3);
}

/* segments */
.dca24-seg{
  flex:1;
  padding: 10px 14px 8px;
  position: relative;
  background: rgba(255,255,255,.85);
  border-right: 1px solid #d8dde6;
  min-height: 64px;
}
.dca24-seg:last-child{ border-right:none; }

.dca24-seg:after{
  content:"";
  position:absolute;
  right:-14px;
  top:0;
  width:28px;
  height:100%;
  background: radial-gradient(28px 64px at 0% 50%, rgba(255,255,255,.95), rgba(255,255,255,0));
  opacity:.8;
}

/* segment head */
.dca24-seg-head{
  display:flex;
  align-items:center;
  gap:8px;
  font-weight: 600;
  color:#1e293b;
}

.dca24-label{
  font-size: 13px;
  font-weight: 700;
  letter-spacing:.2px;
}

.dca24-icon{
  width:22px;
  height:22px;
  border-radius: 999px;
  display:inline-flex;
  align-items:center;
  justify-content:center;
  font-size:11px;
  border: 1px solid #cbd5e1;
  background: #f1f5f9;
  color:#475569;
}

/* FINTECH STATUS HINTS (very subtle) */
.seg-completed{
  background: linear-gradient(180deg, rgba(148,163,184,.10), rgba(255,255,255,.85));
}
.seg-completed .dca24-icon{ color:#166534; border-color:#cbd5e1; background:#f8fafc; }

.seg-pending{
  background: linear-gradient(180deg, rgba(148,163,184,.12), rgba(255,255,255,.85));
}
.seg-pending .dca24-icon{ color:#334155; }

.seg-current{
  background: linear-gradient(180deg, rgba(148,163,184,.14), rgba(255,255,255,.85));
}
.seg-current .dca24-icon{ color:#1e40af; }

.seg-last{
  background: linear-gradient(180deg, rgba(148,163,184,.16), rgba(255,255,255,.85));
}
.seg-last .dca24-icon{ color:#475569; }

/* dotted progress row */
.dca24-dots{
  display:flex;
  gap:4px;
  margin: 6px 0 4px;
}
.dca24-dots span{
  width:5px;
  height:5px;
  border-radius:999px;
  background: #cbd5e1;
}

/* values */
.dca24-value{
  display:flex;
  justify-content:flex-end;
  align-items:center;
}

.dca24-num{
  font-size: 24px;
  font-weight: 700;
  color:#0f172a;
}

.dca24-subline{
  margin-top: 6px;
  font-size: 11px;
  font-weight: 600;
  color:#64748b;
}

.dca24-txn{
  font-size: 14px;
  font-weight: 700;
  color:#0f172a;
}

/* footer */
.dca24-foot{
  display:flex;
  align-items:center;
  gap:10px;
  padding: 6px 2px 0;
  color:#64748b;
  font-size: 12px;
}

.dca24-dd{
  padding: 4px 8px;
  border-radius: 6px;
  border: 1px solid #d1d7e0;
  background: #eef2f6;
  color:#1e293b;
  font-weight: 600;
}

