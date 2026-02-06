/* Toolbar shell */
.dca-toolbar{
  display:flex;
  align-items:center;
  justify-content:space-between;
  gap:12px;
  padding:10px 10px;
  border:1px solid rgba(0,0,0,.10);
  border-radius:8px;
  background: linear-gradient(180deg, #fafafa, #f5f6f8);
}

.dca-toolbar-left, .dca-toolbar-right{
  display:flex;
  align-items:center;
  gap:10px;
  flex-wrap:wrap;
}

/* Search */
.dca-search{
  display:flex;
  align-items:center;
  gap:8px;
  padding:6px 10px;
  border-radius:8px;
  border:1px solid rgba(0,0,0,.12);
  background:#fff;
  min-width:420px;
}
.dca-search-icon{
  opacity:.7;
}
.dca-search-input{
  width:100%;
}
.dca-search .k-input-inner{
  border:none !important;
  box-shadow:none !important;
}

/* Chips */
.dca-chip{
  display:inline-flex;
  align-items:center;
  gap:6px;
  height:34px;
  padding:0 12px;
  border-radius:8px;
  border:1px solid rgba(0,0,0,.12);
  background:#fff;
  font-weight:600;
  cursor:pointer;
}
.dca-chip:hover{ filter:brightness(.99); box-shadow:0 6px 12px rgba(0,0,0,.06); }
.dca-chip.is-active{
  box-shadow: inset 0 0 0 2px rgba(0,0,0,.08);
}

/* Failed */
.dca-chip-failed{
  background: linear-gradient(180deg, #ffffff, #f7f7f7);
}
.dca-chip-failed.is-active{
  border-color: rgba(220,38,38,.35);
  background: linear-gradient(180deg, rgba(220,38,38,.10), rgba(220,38,38,.04));
}

/* In progress */
.dca-chip-progress.is-active{
  border-color: rgba(59,130,246,.35);
  background: linear-gradient(180deg, rgba(59,130,246,.12), rgba(59,130,246,.05));
}

.dca-chip-count{
  display:inline-flex;
  align-items:center;
  justify-content:center;
  min-width:22px;
  height:18px;
  padding:0 6px;
  border-radius:999px;
  font-size:12px;
  background: rgba(0,0,0,.08);
}

/* Segmented UI/API */
.dca-seg{
  display:inline-flex;
  border:1px solid rgba(0,0,0,.12);
  border-radius:8px;
  overflow:hidden;
  background:#fff;
}
.dca-seg-btn{
  height:34px;
  padding:0 14px;
  border:none;
  background:transparent;
  cursor:pointer;
  font-weight:700;
}
.dca-seg-btn.is-active{
  background: rgba(0,0,0,.08);
}

/* Switch + label */
.dca-switch{
  display:flex;
  align-items:center;
  gap:8px;
  padding:0 6px;
}
.dca-switch-label{
  font-size:13px;
  font-weight:600;
  color:#374151;
}

/* Buttons */
.dca-btn{
  height:34px;
  padding:0 12px;
  border-radius:8px;
  border:1px solid rgba(0,0,0,.12);
  background:#fff;
  font-weight:700;
  cursor:pointer;
}
.dca-btn-ghost:hover{ box-shadow:0 6px 12px rgba(0,0,0,.06); }

/* Make it responsive */
@media (max-width: 1100px){
  .dca-search{ min-width: 260px; }
}
