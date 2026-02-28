# TourRadar SCOUT Design System

When building TourRadar frontend interfaces, always use the design tokens and component patterns documented below. These are sourced from the SCOUT Design System (Figma) and the live TourRadar website.

**Live reference**: https://tourradar-design-system.vercel.app
**GitHub**: https://github.com/ntrieb/tourradar-design-system
**Figma source**: https://www.figma.com/design/xbrz3u2rdry1LmCOz12dTh/SCOUT-Design-System

---

## Design Tokens (CSS Custom Properties)

Always use CSS custom properties from the `:root` scope. Never hardcode colors, spacing, or typography values.

### Colors

```css
/* Brand / UI Colors */
--color-primary: #177FA4;        /* Primary CTA, links, active states */
--color-primary-dark: #0E6D8D;   /* Primary hover */
--color-primary-light: #409CD1;  /* Secondary links */
--color-primary-bg: #E6F4FD;     /* Primary tinted backgrounds */
--color-accent: #7B61FF;         /* Accent/purple highlights */

/* Semantic Colors */
--color-info: #3B82F6;
--color-warning: #FCA336;
--color-error: #E22B2C;          /* Also used for discount badges */
--color-success: #10B981;

/* Neutrals (Grey scale 0-100) */
--color-grey-0: #FFFFFF;   --color-grey-10: #F4F5F5;
--color-grey-20: #E3E5E6;  --color-grey-30: #BBC0C2;
--color-grey-40: #A8ADAF;  --color-grey-50: #8B9194;
--color-grey-60: #616668;  --color-grey-70: #4A4F51;
--color-grey-80: #3D4142;  --color-grey-90: #323637;
--color-grey-100: #1A1D1E;

/* UI Aliases */
--text-primary: #323637;    /* Body text */
--text-secondary: #616668;  /* Descriptions, meta */
--text-muted: #A8ADAF;      /* Hints, placeholders */
--bg-page: #FFFFFF;
--bg-surface: #FFFFFF;
--bg-muted: #F4F5F5;        /* Card backgrounds, section fills */
--bg-subtle: #F1F2F3;       /* Footer background */
--border-default: #E3E5E6;  /* Card borders, dividers */
--border-light: #F4F5F5;    /* Table row borders */
```

#### Scout Spectrum (Full Palette)

Each color family has levels 10-100. Use format: `--color-{family}-{level}`

Available families: `violet`, `indigo`, `blue`, `teal`, `green`, `amber`, `orange`, `red`, `pink`

```css
/* Example: Teal spectrum */
--color-teal-10: #E6F4FD;  --color-teal-20: #CCE9FB;
--color-teal-30: #99D3F7;  --color-teal-40: #66BDF3;
--color-teal-50: #409CD1;  --color-teal-60: #177FA4;
--color-teal-70: #0E6D8D;  --color-teal-80: #0A5A75;
--color-teal-90: #07475D;  --color-teal-100: #043445;
```

### Typography

```css
--font-family: 'Helvetica Neue', Helvetica, Arial, FreeSans, sans-serif;
--font-family-display: 'Inter', var(--font-family); /* For headings/display */

/* Major Third scale (1.250), base 16px */
--font-size-h1: 2.441em;  /* 39px */
--font-size-h2: 1.953em;  /* 31px */
--font-size-h3: 1.563em;  /* 25px */
--font-size-h4: 1.25em;   /* 20px */
--font-size-h5: 1em;      /* 16px */
--font-size-h6: 0.75em;   /* 12px */
--font-size-body: 1em;    /* 16px */
--font-size-sm: 0.875em;  /* 14px */
--font-size-xs: 0.75em;   /* 12px */

--font-weight-regular: 400;
--font-weight-medium: 500;
--font-weight-semibold: 600;
--font-weight-bold: 700;

--line-height-tight: 1.25;
--line-height-normal: 1.5;
--line-height-relaxed: 1.75;
```

### Spacing

```css
--space-xxxs: 2px;   --space-xxs: 4px;    --space-xs: 8px;
--space-s: 12px;     --space-m: 16px;     --space-l: 24px;
--space-xl: 32px;    --space-xxl: 48px;   --space-xxxl: 64px;
--space-xxxxl: 80px; --space-xxxxxl: 96px;
```

### Border Radius (from Figma Variables)

```css
--radius-xs: 5px;    --radius-s: 7px;     --radius-m: 9px;
--radius-l: 11px;    --radius-xl: 13px;   --radius-xxl: 15px;
--radius-xxxl: 19px; --radius-pill: 9999px;
```

### Elevation (Box Shadow)

```css
--shadow-xs: 0 1px 2px rgba(50,54,55,0.05);
--shadow-sm: 0 1px 3px rgba(50,54,55,0.08), 0 1px 2px rgba(50,54,55,0.06);
--shadow-md: 0 4px 6px rgba(50,54,55,0.07), 0 2px 4px rgba(50,54,55,0.06);
--shadow-lg: 0 10px 15px rgba(50,54,55,0.07), 0 4px 6px rgba(50,54,55,0.05);
--shadow-xl: 0 20px 25px rgba(50,54,55,0.08), 0 8px 10px rgba(50,54,55,0.04);
```

### Transitions

```css
--transition-fast: 150ms ease;
--transition-normal: 250ms ease;
--transition-slow: 350ms ease;
```

---

## Component Reference

### Buttons

```html
<!-- Variants -->
<button class="btn btn-md btn-primary">Primary</button>
<button class="btn btn-md btn-secondary">Secondary</button>
<button class="btn btn-md btn-outline">Outline</button>
<button class="btn btn-md btn-text">Text</button>
<button class="btn btn-md btn-danger">Danger</button>

<!-- Sizes: btn-sm, btn-md, btn-lg -->
<button class="btn btn-sm btn-primary">Small</button>
<button class="btn btn-lg btn-primary">Large</button>

<!-- States -->
<button class="btn btn-md btn-primary" disabled>Disabled</button>
<button class="btn btn-md btn-primary btn-loading">Loading</button>
```

```css
.btn {
  display: inline-flex; align-items: center; gap: var(--space-xs);
  font-family: var(--font-family); font-weight: 700; cursor: pointer;
  border: 2px solid transparent; border-radius: var(--radius-pill);
  transition: all var(--transition-fast); line-height: 1; white-space: nowrap;
}
.btn-sm { padding: 8px 16px; font-size: var(--font-size-xs); }
.btn-md { padding: 12px 16px; font-size: var(--font-size-sm); }
.btn-lg { padding: 14px 28px; font-size: 1em; }
.btn-primary { background: var(--color-primary); color: white; }
.btn-primary:hover { background: var(--color-primary-dark); }
.btn-secondary { background: var(--color-primary-bg); color: var(--color-primary-dark); }
.btn-outline { background: transparent; color: var(--color-primary); border-color: var(--color-primary); }
.btn-text { background: transparent; color: var(--color-primary); border: none; }
.btn-danger { background: var(--color-error); color: white; }
```

### Badges & Tags

```html
<!-- Status badges -->
<span class="badge-el badge-primary">Primary</span>
<span class="badge-el badge-success">Success</span>
<span class="badge-el badge-warning">Warning</span>
<span class="badge-el badge-danger">Error</span>
<span class="badge-el badge-info">Info</span>
<span class="badge-el badge-neutral">Neutral</span>

<!-- Discount badge -->
<span class="badge-discount">-25%</span>

<!-- Tags (removable, clickable) -->
<span class="tag">Italy</span>
<span class="tag tag-active">Europe</span>
<span class="tag">Spain <span class="tag-remove">&#10005;</span></span>
```

```css
.badge-el {
  display: inline-flex; align-items: center; gap: 4px;
  padding: 3px 10px; border-radius: var(--radius-pill);
  font-size: var(--font-size-xs); font-weight: 600;
}
.badge-primary { background: var(--color-primary-bg); color: var(--color-primary-dark); }
.badge-success { background: var(--color-green-10); color: var(--color-green-70); }
.badge-warning { background: var(--color-amber-10); color: var(--color-amber-80); }
.badge-danger { background: var(--color-red-10); color: var(--color-red-70); }
.badge-discount { background: var(--color-error); color: white; font-weight: 700; padding: 3px 8px; border-radius: var(--radius-xs); }

.tag {
  display: inline-flex; align-items: center; gap: 4px;
  padding: 4px 12px; border-radius: var(--radius-pill);
  font-size: var(--font-size-xs); border: 1px solid var(--border-default);
  color: var(--text-secondary); cursor: pointer;
}
.tag-active { background: var(--color-primary-bg); border-color: var(--color-primary); color: var(--color-primary); }
```

### Input Fields

```html
<!-- Standard input -->
<div class="form-group">
  <label class="form-label">Label</label>
  <input type="text" class="form-input" placeholder="Placeholder...">
  <div class="form-hint">Helper text here.</div>
</div>

<!-- Error state -->
<input type="text" class="form-input error" value="Invalid">
<div class="form-error">Error message.</div>

<!-- Select -->
<select class="form-input form-select">
  <option>Choose...</option>
</select>

<!-- Textarea -->
<textarea class="form-input" rows="3"></textarea>
```

```css
.form-input {
  width: 100%; padding: 10px 14px; border: 1px solid var(--border-default);
  border-radius: var(--radius-m); font-size: var(--font-size-sm);
  font-family: var(--font-family); color: var(--text-primary);
}
.form-input:focus { border-color: var(--color-primary); box-shadow: 0 0 0 3px rgba(23,127,164,0.15); }
.form-input.error { border-color: var(--color-error); }
```

### Selection Controls

```html
<!-- Checkbox -->
<label class="form-check"><input type="checkbox" checked> Option</label>

<!-- Radio -->
<label class="form-check"><input type="radio" name="group"> Option</label>

<!-- Toggle -->
<label class="toggle">
  <input type="checkbox" checked>
  <span class="toggle-slider"></span>
</label>
```

### Ratings

```html
<div class="rating">
  <span class="star">&#9733;</span>      <!-- Full star -->
  <span class="star half">&#9733;</span>  <!-- Half star -->
  <span class="star empty">&#9733;</span> <!-- Empty star -->
  <span class="rating-text">4.5 (288 reviews)</span>
</div>

<!-- Large variant -->
<div class="rating rating-lg">...</div>
```

### Accordion

```html
<div class="accordion">
  <div class="accordion-item open">
    <div class="accordion-header" onclick="this.parentElement.classList.toggle('open')">
      Title <span class="accordion-icon">&#9662;</span>
    </div>
    <div class="accordion-body">
      <div class="accordion-body-inner">Content here.</div>
    </div>
  </div>
</div>
```

### Tabs

```html
<div class="tabs">
  <button class="tab-btn active" data-tab="panel1">Tab 1</button>
  <button class="tab-btn" data-tab="panel2">Tab 2</button>
</div>
<div class="tab-panel active" id="panel1">Content 1</div>
<div class="tab-panel" id="panel2">Content 2</div>
```

JS for tab switching:
```js
document.querySelectorAll('.tab-btn').forEach(btn => {
  btn.addEventListener('click', () => {
    const group = btn.closest('section');
    group.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
    group.querySelectorAll('.tab-panel').forEach(p => p.classList.remove('active'));
    btn.classList.add('active');
    document.getElementById(btn.dataset.tab)?.classList.add('active');
  });
});
```

### Dropdown

```html
<div class="dropdown">
  <button class="btn btn-md btn-secondary dropdown-trigger"
          onclick="this.parentElement.classList.toggle('open')">
    Menu &#9662;
  </button>
  <div class="dropdown-menu">
    <div class="dropdown-item">Option 1</div>
    <div class="dropdown-divider"></div>
    <div class="dropdown-item">Option 2</div>
  </div>
</div>
```

### Alerts

```html
<div class="alert alert-info">
  <span class="alert-icon">&#8505;</span>
  <div>Info message text.</div>
  <button class="alert-close" onclick="this.parentElement.remove()">&#10005;</button>
</div>
<!-- Variants: alert-info, alert-success, alert-warning, alert-error -->
```

### Tooltips

```html
<span class="tooltip-wrap tooltip-top">
  <button class="btn btn-sm btn-secondary">Hover me</button>
  <span class="tooltip-content">Tooltip text</span>
</span>
<!-- Positions: tooltip-top, tooltip-bottom -->
```

### Breadcrumbs

```html
<nav class="breadcrumb">
  <a href="#">Home</a>
  <span class="sep">&#8250;</span>
  <a href="#">Europe Tours</a>
  <span class="sep">&#8250;</span>
  <span class="current">Classic Europe</span>
</nav>
```

### Lists

```html
<div class="list">
  <div class="list-item selected">Selected item</div>
  <div class="list-item">Regular item</div>
</div>
```

### Modal

```html
<div class="modal-overlay" id="my-modal">
  <div class="modal">
    <div class="modal-header">
      <h3 class="modal-title">Title</h3>
      <button class="modal-close" onclick="document.getElementById('my-modal').classList.remove('open')">&#10005;</button>
    </div>
    <div class="modal-body">Content</div>
    <div class="modal-footer">
      <button class="btn btn-md btn-secondary">Cancel</button>
      <button class="btn btn-md btn-primary">Confirm</button>
    </div>
  </div>
</div>

<!-- Open: document.getElementById('my-modal').classList.add('open') -->
```

---

## Composite Components

### Tour Card

```html
<div class="tour-card">
  <div class="tour-card-img">
    <img src="..." alt="Tour">
    <span class="badge-discount">-25%</span>
  </div>
  <div class="tour-card-body">
    <div class="tour-card-rating">
      <div class="rating">
        <span class="star">&#9733;</span><span class="star">&#9733;</span>
        <span class="star">&#9733;</span><span class="star">&#9733;</span>
        <span class="star half">&#9733;</span>
      </div>
      <span class="text-xs text-muted">288 reviews</span>
    </div>
    <div class="tour-card-title"><a href="#">Tour Name - Duration</a></div>
    <div class="tour-card-meta">
      <span class="tag">Explorer</span>
      <span class="tag">14 days</span>
    </div>
    <div class="tour-card-operator">by Operator Name</div>
    <div class="tour-card-pricing">
      <span class="original">&euro;3,545</span>
      <span class="current">&euro;2,645</span>
      <span class="per-person">per person</span>
    </div>
    <div class="tour-card-actions">
      <button class="btn btn-sm btn-secondary">Brochure</button>
      <button class="btn btn-sm btn-primary">View Tour</button>
    </div>
  </div>
</div>
```

### Navigation Bar

```html
<nav class="site-nav">
  <a href="#" class="site-nav-logo">tourradar</a>
  <div class="site-nav-links">
    <a href="#">Destinations</a>
    <a href="#">Adventure Styles</a>
    <a href="#">Deals</a>
  </div>
  <div class="site-nav-trust">
    <span class="trust-badge">2,500 operators</span>
    <span class="trust-badge">&#9733; 4.6 (9,913 reviews)</span>
  </div>
</nav>
```

### Search Bar

```html
<div class="search-bar">
  <input type="text" placeholder="Where do you want to go?">
  <button class="btn btn-md btn-primary">Search</button>
</div>
```

### Booking Panel (BCP)

```html
<div class="booking-panel">
  <div class="booking-price">
    <div class="flex-center"><span class="original">&euro;3,545</span><span class="badge-discount">-25%</span></div>
    <div class="current">&euro;2,645</div>
    <div class="per">per person</div>
  </div>
  <div class="room-selector">
    <div class="room-option">Cheapest</div>
    <div class="room-option active">Shared</div>
    <div class="room-option">Private</div>
  </div>
  <div class="form-group">
    <label class="form-label">Departure Date</label>
    <input type="date" class="form-input">
  </div>
  <button class="btn btn-lg btn-primary" style="width:100%;justify-content:center">Check Availability</button>
</div>
```

### Footer

```html
<footer class="site-footer">
  <div class="footer-grid">
    <div class="footer-col">
      <h4>Category</h4>
      <a href="#">Link</a>
    </div>
    <!-- Repeat for each column -->
  </div>
  <div class="footer-bottom">
    <div class="footer-bottom-links"><a href="#">&copy; 2026 TourRadar</a></div>
    <div class="footer-social"><a href="#">f</a><a href="#">t</a></div>
  </div>
</footer>
```

### Review Card

```html
<div class="review-card">
  <div class="review-header">
    <div class="review-avatar">SK</div>
    <div>
      <div class="review-name">Sarah K.</div>
      <div class="review-date">February 2026</div>
    </div>
    <div style="margin-left:auto">
      <div class="rating">...</div>
    </div>
  </div>
  <div class="review-text">Review content here.</div>
</div>
```

### Operator Card

```html
<div class="operator-card">
  <div class="operator-logo">EE</div>
  <div class="operator-info">
    <h3>Operator Name</h3>
    <div class="rating">...</div>
    <div class="operator-badges">
      <span class="badge-el badge-primary">Platinum</span>
      <span class="badge-el badge-success">Traveller's Choice</span>
    </div>
  </div>
</div>
```

### Itinerary Day

```html
<div class="itinerary-day open">
  <div class="itinerary-header" onclick="this.parentElement.classList.toggle('open')">
    <span class="day-number">1</span>
    <div>
      <div class="day-title">London Arrival</div>
      <div class="day-subtitle">Welcome meeting</div>
    </div>
    <span class="accordion-icon">&#9662;</span>
  </div>
  <div class="itinerary-body">
    <div class="itinerary-body-inner">
      <div class="itinerary-meals">
        <span class="meal-badge">Breakfast</span>
        <span class="meal-badge">Dinner</span>
      </div>
      Day description text.
    </div>
  </div>
</div>
```

### Availability Table

```html
<table class="avail-table">
  <thead><tr><th>Departure</th><th>Price</th><th>Status</th><th>Action</th></tr></thead>
  <tbody>
    <tr>
      <td><strong>Mar 15, 2026</strong></td>
      <td><span class="fw-600">&euro;2,645</span> <span class="badge-discount">-25%</span></td>
      <td><span class="avail-status almost-sold">Almost Sold Out</span></td>
      <td><button class="btn btn-sm btn-primary">Book Now</button></td>
    </tr>
    <!-- Status classes: avail-status.available, .filling, .almost-sold -->
  </tbody>
</table>
```

### Hero Section

```html
<div class="hero">
  <nav class="breadcrumb">...</nav>
  <h2>Page Title</h2>
  <p>Subtitle description text.</p>
  <button class="btn btn-lg btn-primary" style="background:white;color:var(--color-primary)">CTA</button>
</div>
```

---

## Layout Breakpoints

| Width | Device |
|-------|--------|
| 320px | Small mobile |
| 375px | Mobile |
| 568px | Large mobile |
| 768px | Tablet |
| 1024px | Small desktop |
| 1280px | Desktop |
| 1440px | Large desktop |

Sidebar navigation hides at 768px. Grid layouts collapse to 2 columns on tablet.

---

## Usage Guidelines

1. **Semantic HTML** - Use proper heading hierarchy, landmarks, and ARIA labels
2. **WCAG Contrast** - All color combinations meet AA contrast requirements
3. **Responsive** - Test at all breakpoints; use grid utilities (`grid-2`, `grid-3`, `grid-4`)
4. **No Tailwind** - This is vanilla CSS only; use design tokens via custom properties
5. **Interactive states** - Always implement hover, focus, active, and disabled states
6. **Consistent spacing** - Use spacing tokens, never arbitrary pixel values
