/* ===== SUMMARY BLOCKS: BOFA-LIKE (NO COLOR PANELS) ===== */

/* base segment: clean white, square, subtle divider only */
.dca24-seg{
  background: #ffffff !important;
  border-right: 1px solid #c9d6e6;
  border-radius: 0;
  box-shadow: none;
}

/* remove any previous gradient/panel effect */
.dca24-seg:before,
.dca24-seg:after{
  display:none !important;
}

/* top accent line — only place where color shows */
.seg-completed{ border-top: 3px solid #1f4f9b; }  /* deep bank blue */
.seg-pending  { border-top: 3px solid #2a5fae; }  /* slightly lighter */
.seg-current  { border-top: 3px solid #0b1f3a; }  /* navy (most important) */
.seg-last     { border-top: 3px solid #6b7f9a; }  /* steel */

/* headings + numbers: bank navy */
.dca24-label{ color:#0b1f3a; }
.dca24-num{ color:#0b1f3a; }
.dca24-txn{ color:#0b1f3a; }

/* icons: no colored fill, only colored stroke/text */
.dca24-icon{
  background:#ffffff;
  border:1px solid #c9d6e6;
  color:#0b1f3a;
  border-radius:0;
}

/* optional: set per block icon color (subtle) */
.seg-completed .dca24-icon{ color:#1f4f9b; }
.seg-pending   .dca24-icon{ color:#2a5fae; }
.seg-current   .dca24-icon{ color:#0b1f3a; }
.seg-last      .dca24-icon{ color:#6b7f9a; }

/* dots: neutral by default; only executing gets darker */
.dca24-dots span{
  background:#c4d3e6;
  border-radius:0;
}
.seg-current .dca24-dots span{
  background:#8aa7d6;
}

/* subtle “live” mark for executing — NOT glowing, just a small square */
.seg-current::before{
  content:'';
  position:absolute;
  top:8px;
  right:10px;
  width:6px;
  height:6px;
  background:#0b1f3a;
  opacity:.75;
  border-radius:0;
}
