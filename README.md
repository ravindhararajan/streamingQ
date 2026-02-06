public isSummaryCollapsed = false;

toggleSummary() {
  this.isSummaryCollapsed = !this.isSummaryCollapsed;
}


/* ===== Collapsible Wrapper ===== */
.dca24-wrap {
  border-bottom: 1px solid #c9d6e6;
}

/* Header */
.dca24-header {
  display:flex;
  justify-content:space-between;
  align-items:center;
  cursor:pointer;
  padding: 8px 0;
  user-select:none;
}

.dca24-title {
  font-size: 13px;
  font-weight: 800;
  color:#0b1f3a;
  display:flex;
  align-items:center;
  gap:8px;
}

/* Chevron */
.chevron {
  font-size: 12px;
  transition: transform .2s ease;
}

.chevron.rotate {
  transform: rotate(90deg);
}

/* Collapsible Body */
.dca24-body {
  overflow: hidden;
  transition: max-height .25s ease, opacity .2s ease;
  max-height: 200px;
  opacity: 1;
}

/* Collapsed state */
.dca24-wrap.collapsed .dca24-body {
  max-height: 0;
  opacity: 0;
}




<div class="dca24-wrap" [class.collapsed]="isSummaryCollapsed">

  <!-- Header / Toggle Bar -->
  <div class="dca24-header" (click)="toggleSummary()">
    <div class="dca24-title">
      <span class="chevron" [class.rotate]="!isSummaryCollapsed">▸</span>
      24 Hour Transaction Summary
    </div>

    <div class="dca24-meta">
      <span>Last updated: just now</span>
    </div>
  </div>

  <!-- Collapsible Body -->
  <div class="dca24-body">
    <div class="dca24-bar">

      <!-- Completed -->
      <div class="dca24-seg seg-completed">
        <div class="dca24-seg-head">
          <span class="dca24-icon">✔</span>
          <span class="dca24-label">Completed (24h)</span>
        </div>
        <div class="dca24-value">
          <span class="dca24-num">152</span>
        </div>
      </div>

      <!-- Pending -->
      <div class="dca24-seg seg-pending">
        <div class="dca24-seg-head">
          <span class="dca24-icon">⏳</span>
          <span class="dca24-label">Pending (24h)</span>
        </div>
        <div class="dca24-value">
          <span class="dca24-num">27</span>
        </div>
      </div>

      <!-- Currently Executing -->
      <div class="dca24-seg seg-current">
        <div class="dca24-seg-head">
          <span class="dca24-icon">▶</span>
          <span class="dca24-label">Currently Executing</span>
        </div>
        <div class="dca24-subline">Transaction #</div>
        <div class="dca24-value">
          <span class="dca24-txn">202511114171</span>
        </div>
      </div>

      <!-- Last Executed -->
      <div class="dca24-seg seg-last">
        <div class="dca24-seg-head">
          <span class="dca24-icon">↺</span>
          <span class="dca24-label">Last Executed</span>
        </div>
        <div class="dca24-subline">Transaction #</div>
        <div class="dca24-value">
          <span class="dca24-txn">202511115115</span>
        </div>
      </div>

    </div>
  </div>
</div>
