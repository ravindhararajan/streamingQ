<ng-template kendoGridToolbarTemplate>
  <div class="dca-toolbar">

    <!-- Left: Search -->
    <div class="dca-toolbar-left">
      <span class="dca-search">
        <span class="k-icon k-i-search dca-search-icon"></span>
        <kendo-textbox
          class="dca-search-input"
          [value]="toolbar.search"
          (valueChange)="onToolbarSearch($event)"
          placeholder="Search transactions, users,, templates, email..."
        >
        </kendo-textbox>
      </span>

      <!-- Status chips -->
      <button
        type="button"
        class="dca-chip dca-chip-failed"
        [class.is-active]="toolbar.status === 'failed'"
        (click)="toggleStatus('failed')"
      >
        <span class="k-icon k-i-warning"></span>
        Failed
      </button>

      <button
        type="button"
        class="dca-chip dca-chip-progress"
        [class.is-active]="toolbar.status === 'inprogress'"
        (click)="toggleStatus('inprogress')"
      >
        In Progress <span class="dca-chip-count">{{ summary?.inProgress || 0 }}</span>
      </button>

      <!-- UI / API segmented -->
      <div class="dca-seg">
        <button
          type="button"
          class="dca-seg-btn"
          [class.is-active]="toolbar.source === 'ui'"
          (click)="setSource('ui')"
        >
          UI
        </button>
        <button
          type="button"
          class="dca-seg-btn"
          [class.is-active]="toolbar.source === 'api'"
          (click)="setSource('api')"
        >
          API
        </button>
      </div>
    </div>

    <!-- Right: actions -->
    <div class="dca-toolbar-right">
      <div class="dca-switch">
        <kendo-switch
          [checked]="autoRefreshEnabled"
          (valueChange)="setAutoRefresh($event)"
        ></kendo-switch>
        <span class="dca-switch-label">Auto-refresh</span>
      </div>

      <!-- Columns dropdown (wire it later if you already have your own impl) -->
      <button type="button" class="dca-btn dca-btn-ghost" (click)="openColumns()">
        Columns <span class="k-icon k-i-arrow-s"></span>
      </button>

      <button type="button" class="dca-btn dca-btn-ghost" (click)="clearToolbar()">
        Clear
      </button>
    </div>
  </div>
</ng-template>

// Toolbar state
public toolbar = {
  search: '',
  status: null as null | 'failed' | 'inprogress',
  source: null as null | 'ui' | 'api'
};

// If your dataset array is named differently, update here:
private get rows(): any[] {
  return this.lstDCATransactionLiveStatus || [];
}

public onToolbarSearch(value: string): void {
  this.toolbar.search = value || '';
  this.applyToolbarFilters();
}

public toggleStatus(kind: 'failed' | 'inprogress'): void {
  this.toolbar.status = (this.toolbar.status === kind) ? null : kind;
  this.applyToolbarFilters();
}

public setSource(src: 'ui' | 'api'): void {
  this.toolbar.source = (this.toolbar.source === src) ? null : src;
  this.applyToolbarFilters();
}

public clearToolbar(): void {
  this.toolbar = { search: '', status: null, source: null };
  this.applyToolbarFilters(true);
}

/** Placeholder for your columns menu */
public openColumns(): void {
  // If you already have a Kendo ColumnChooser or custom dialog, open it here.
  // e.g. this.showColumnsDialog = true;
}

/** Build ONE composite filter that matches the toolbar UI */
private applyToolbarFilters(clearAll = false): void {
  // keep existing filters if you want; OR reset everything when clearAll
  const filters: any[] = [];

  if (!clearAll) {
    const q = (this.toolbar.search || '').trim();
    if (q) {
      filters.push({
        logic: 'or',
        filters: [
          { field: 'TransactionNumber', operator: 'contains', value: q },
          { field: 'CurrentStatus', operator: 'contains', value: q },
          { field: 'DebitCardNumber', operator: 'contains', value: q },
          { field: 'Pipeline', operator: 'contains', value: q },
          { field: 'Issuer', operator: 'contains', value: q },
          { field: 'TemplateName', operator: 'contains', value: q },
          { field: 'EmailAddress', operator: 'contains', value: q },
          { field: 'UserID', operator: 'contains', value: q },
          { field: 'IsFrom', operator: 'contains', value: q }
        ]
      });
    }

    if (this.toolbar.status === 'failed') {
      filters.push({ field: 'CurrentStatus', operator: 'contains', value: 'Fail' });
    } else if (this.toolbar.status === 'inprogress') {
      filters.push({ field: 'CurrentStatus', operator: 'contains', value: 'Progress' });
    }

    if (this.toolbar.source === 'ui') {
      filters.push({ field: 'IsFrom', operator: 'eq', value: 'UI' });
    } else if (this.toolbar.source === 'api') {
      filters.push({ field: 'IsFrom', operator: 'eq', value: 'API' });
    }
  }

  const newFilter: CompositeFilterDescriptor = {
    logic: 'and',
    filters
  };

  this.state = {
    ...this.state,
    skip: 0,
    filter: newFilter
  };

  // Rebind
  this.gridView = process(this.rows, this.state);
}





