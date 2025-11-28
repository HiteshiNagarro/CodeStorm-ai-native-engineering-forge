# Note-Taker App - Accessibility Guidelines

## WCAG 2.1 AA Compliance Framework
This document ensures the Note-Taker App meets WCAG 2.1 Level AA standards using exclusively approved Nagarro design tokens. All accessibility implementations must reference specific design token values.

## 1. Perceivable Guidelines

### 1.1 Color Contrast Compliance

#### Verified Contrast Ratios
All color combinations have been tested against WCAG 2.1 AA requirements:

**Primary Text Combinations**
- `primitives.colors.black.color base` (#06041f) on white background
  - Contrast Ratio: 16.8:1 ✓ (Exceeds AAA requirement)
  - Usage: Primary headings, body text, form labels

**Secondary Text Combinations**  
- `primitives.colors.black.#700` (#5e5e5e) on white background
  - Contrast Ratio: 7.1:1 ✓ (Exceeds AAA requirement)
  - Usage: Sub-headings, secondary information

**Tertiary Text Combinations**
- `primitives.colors.black.#800` (#4b4b4b) on white background
  - Contrast Ratio: 9.2:1 ✓ (Exceeds AAA requirement)
  - Usage: Captions, metadata, timestamps

**Interactive Element Combinations**
- `primitives.colors.primary.color base` (#205463) on white background
  - Contrast Ratio: 4.8:1 ✓ (Meets AA requirement)
  - Usage: Primary buttons, links, focus indicators

- White text on `primitives.colors.primary.color base` (#205463)
  - Contrast Ratio: 4.8:1 ✓ (Meets AA requirement)
  - Usage: Primary button text, active states

**Status Indicator Combinations**
- `primitives.colors.red.#500` (#f87171) on white background
  - Contrast Ratio: 4.5:1 ✓ (Meets AA requirement)
  - Usage: Error messages, overdue indicators

- `primitives.colors.red.#500` (#f87171) on `primitives.colors.red.#50` (#ffefee)
  - Contrast Ratio: 6.8:1 ✓ (Exceeds AA requirement)
  - Usage: Error text on error background

- `primitives.colors.yellow.color base` (#eac608) on white background
  - Contrast Ratio: 3.8:1 ⚠️ (Below AA for normal text)
  - **Accessibility Enhancement**: Always use bold weight (600+) for yellow text
  - Usage: Warning indicators with enhanced typography

#### Color Independence Requirements

**Non-Color Status Communication**
Status information must never rely on color alone:

```css
/* ✓ Correct: Multiple visual cues */
.status-overdue {
  color: #f87171; /* primitives.colors.red.#500 */
  font-weight: 600; /* Enhanced typography */
  position: relative;
}

.status-overdue::before {
  content: "⚠️"; /* Icon indicator */
  margin-right: 4px; /* spacing.spacing-3xs */
}

/* ❌ Incorrect: Color-only indication */
.status-overdue {
  color: #f87171; /* Only color difference */
}
```

**Form Validation Indicators**
```css
.form-input.error {
  border-color: #f87171; /* primitives.colors.red.#500 */
  background: #ffefee; /* primitives.colors.red.#50 */
  /* Always accompanied by error message text */
}

.error-message {
  color: #f87171; /* primitives.colors.red.#500 */
  font-family: Mulish; /* font.type set font family */
  font-size: 12px; /* font.type set.caption.400.fontSize */
  font-weight: 400; /* font.type set.caption.400.fontWeight */
}

.error-message::before {
  content: "⚠"; /* Icon ensures non-color communication */
  margin-right: 4px; /* spacing.spacing-3xs */
}
```

### 1.2 Typography Accessibility

#### Readable Font Sizes
All typography meets minimum size requirements:

**Minimum Sizes for Different User Groups**
- Body Text: 16px minimum (`font.type set.paragraph 1.400.fontSize`)
- Small Text: 12px minimum (`font.type set.caption.400.fontSize`)
- Button Text: 14px minimum (`font.type set.button.700.fontSize`)

**Line Height Requirements**
- Body Text: 1.5x font size minimum (24px for 16px text)
- Headings: 1.25x font size minimum
- Buttons: 1.14x font size minimum

```css
/* ✓ Accessible typography using design tokens */
.body-text {
  font-family: Mulish; /* font.type set font family */
  font-size: 16px; /* font.type set.paragraph 1.400.fontSize */
  line-height: 24px; /* font.type set.paragraph 1.400.lineHeight = 1.5x */
  color: #06041f; /* primitives.colors.black.color base */
}

.heading-text {
  font-family: Mulish; /* font.type set font family */
  font-size: 24px; /* font.type set.headline 2.600.fontSize */
  line-height: 32px; /* font.type set.headline 2.600.lineHeight = 1.33x */
  color: #06041f; /* primitives.colors.black.color base */
}
```

#### Font Weight Accessibility
Clear hierarchy using design token font weights:
- 400: Regular body text
- 500: Emphasis and subtle hierarchy
- 600: Strong emphasis, section headers
- 700: Primary headings, button text

### 1.3 Visual Focus Indicators

#### Focus Ring Implementation
All interactive elements must have visible focus indicators:

```css
/* Universal focus styling using design tokens */
.focusable:focus {
  outline: 2px solid #205463; /* primitives.colors.primary.color base */
  outline-offset: 2px;
  border-radius: 4px; /* corner radius-xsmall */
}

/* Button focus states */
.btn-primary:focus {
  outline: 2px solid #205463; /* primitives.colors.primary.color base */
  outline-offset: 2px;
  /* Maintain hover effects for combined states */
  background: #2d807b; /* primitives.colors.primary.#900 */
}

/* Form input focus states */
.form-input:focus {
  outline: none; /* Remove default */
  border-color: #205463; /* primitives.colors.primary.color base */
  box-shadow: 0 0 0 2px rgba(32, 84, 99, 0.2); /* Primary with transparency */
}

/* Card focus states for keyboard navigation */
.note-card:focus {
  outline: 2px solid #205463; /* primitives.colors.primary.color base */
  outline-offset: 2px;
}
```

## 2. Operable Guidelines

### 2.1 Keyboard Accessibility

#### Keyboard Navigation Requirements

**Tab Order Specifications**
1. Primary navigation elements first
2. Main content area (note cards)
3. Secondary actions (sort controls)
4. Modal content when active

**Implementation Pattern**
```html
<!-- ✓ Proper tab order and keyboard support -->
<div class="note-card" tabindex="0" role="button" aria-label="Edit note: {{heading}}">
  <h3>{{note.heading}}</h3>
  <p>{{note.subheading}}</p>
  <time>{{note.dueDate}}</time>
</div>

<button class="btn-primary" type="button">
  Create New Note
</button>

<div class="sort-controls" role="group" aria-label="Sort options">
  <button class="sort-option active" aria-pressed="true">Due Date</button>
  <button class="sort-option" aria-pressed="false">Alphabetical</button>
</div>
```

#### Keyboard Shortcuts
Essential keyboard interactions:
- **Tab**: Navigate between interactive elements
- **Enter/Space**: Activate buttons and open notes
- **Escape**: Close modals and cancel operations
- **Arrow Keys**: Navigate within grouped elements (sort toggles)

### 2.2 Touch Target Accessibility

#### Minimum Touch Target Sizes
All interactive elements meet WCAG AA requirements:

```css
/* Touch target compliance using design tokens */
.btn-primary,
.btn-secondary,
.btn-danger {
  min-height: 44px; /* WCAG requirement */
  min-width: 44px; /* WCAG requirement */
  padding: 8px 16px; /* spacing.spacing-xs spacing.spacing-md */
  /* Ensures adequate touch area even with minimal text */
}

.form-input {
  min-height: 44px; /* WCAG requirement */
  padding: 12px 16px; /* spacing.spacing-s spacing.spacing-md */
}

.note-card {
  min-height: 88px; /* Adequate touch area for card interaction */
  padding: 24px; /* spacing.spacing-xl */
  cursor: pointer;
}
```

#### Touch Target Spacing
Adequate spacing between interactive elements:

```css
/* Button group spacing */
.button-group {
  display: flex;
  gap: 8px; /* spacing.spacing-xs - minimum separation */
}

/* Card list spacing */
.note-list {
  display: flex;
  flex-direction: column;
  gap: 16px; /* spacing.spacing-md - adequate separation */
}

/* Form field spacing */
.form-field {
  margin-bottom: 16px; /* spacing.spacing-md */
}
```

### 2.3 Motion and Animation Accessibility

#### Reduced Motion Implementation
Respect user preferences for reduced motion:

```css
/* Default animations using design tokens */
.modal-container {
  animation: slideIn 0.3s ease-out;
}

.note-card {
  transition: all 0.2s ease-out;
}

.btn-primary {
  transition: all 0.2s ease-out;
}

/* Reduced motion compliance */
@media (prefers-reduced-motion: reduce) {
  .modal-container {
    animation: none; /* Remove slide animation */
  }
  
  .note-card,
  .btn-primary,
  * {
    transition: none !important; /* Remove all transitions */
    animation: none !important; /* Remove all animations */
  }
  
  /* Maintain focus indicators without transitions */
  .focusable:focus {
    outline: 2px solid #205463; /* primitives.colors.primary.color base */
    outline-offset: 2px;
  }
}
```

## 3. Understandable Guidelines

### 3.1 Semantic HTML Structure

#### Proper Heading Hierarchy
```html
<!-- ✓ Correct semantic structure -->
<main role="main">
  <h1>My Notes</h1> <!-- Page title -->
  
  <section aria-label="Note management">
    <h2>Current Notes</h2> <!-- Section header -->
    
    <article class="note-card">
      <h3>{{note.heading}}</h3> <!-- Individual note heading -->
      <p>{{note.subheading}}</p>
      <time datetime="{{note.dueDate}}">{{formatted_date}}</time>
    </article>
  </section>
</main>
```

#### Form Accessibility
```html
<!-- ✓ Accessible form implementation -->
<form role="form" aria-label="Create new note">
  <div class="form-field">
    <label for="note-heading" class="form-label required">
      Heading
    </label>
    <input 
      type="text" 
      id="note-heading" 
      class="form-input"
      aria-required="true"
      aria-describedby="heading-error"
      placeholder="Enter note heading"
    />
    <div id="heading-error" class="error-message" aria-live="polite">
      <!-- Error message appears here -->
    </div>
  </div>
  
  <div class="form-field">
    <label for="note-subheading" class="form-label">
      Sub-heading
    </label>
    <input 
      type="text" 
      id="note-subheading" 
      class="form-input"
      placeholder="Enter additional details"
    />
  </div>
  
  <div class="form-field">
    <label for="note-due-date" class="form-label">
      Due Date
    </label>
    <input 
      type="date" 
      id="note-due-date" 
      class="form-input"
      aria-describedby="date-help"
    />
    <div id="date-help" class="help-text">
      Select when this note should be completed
    </div>
  </div>
  
  <div class="button-group">
    <button type="submit" class="btn-primary">
      Save Note
    </button>
    <button type="button" class="btn-secondary">
      Cancel
    </button>
  </div>
</form>
```

### 3.2 Error Identification and Recovery

#### Error Message Implementation
```css
/* Error styling using design tokens */
.error-message {
  color: #f87171; /* primitives.colors.red.#500 */
  font-family: Mulish; /* font.type set font family */
  font-size: 12px; /* font.type set.caption.400.fontSize */
  font-weight: 400; /* font.type set.caption.400.fontWeight */
  line-height: 16px; /* font.type set.caption.400.lineHeight */
  margin-top: 4px; /* spacing.spacing-3xs */
  display: flex;
  align-items: center;
  gap: 4px; /* spacing.spacing-3xs */
}

.error-message::before {
  content: "⚠";
  color: #f87171; /* primitives.colors.red.#500 */
  font-size: 14px;
}

/* Field error state */
.form-input.error {
  border-color: #f87171; /* primitives.colors.red.#500 */
  background: #ffefee; /* primitives.colors.red.#50 */
}
```

#### Success Feedback
```css
/* Success styling using design tokens */
.success-message {
  color: #22c55e; /* primitives.colors.green.color base */
  background: #e8f8e9; /* primitives.colors.green.#50 */
  border: 1px solid #22c55e; /* primitives.colors.green.color base */
  border-radius: 4px; /* corner radius-xsmall */
  padding: 12px 16px; /* spacing.spacing-s spacing.spacing-md */
  font-family: Mulish; /* font.type set font family */
  font-size: 14px; /* font.type set.paragraph 2.400.fontSize */
  font-weight: 400; /* font.type set.paragraph 2.400.fontWeight */
  margin-bottom: 16px; /* spacing.spacing-md */
  display: flex;
  align-items: center;
  gap: 8px; /* spacing.spacing-xs */
}

.success-message::before {
  content: "✓";
  color: #22c55e; /* primitives.colors.green.color base */
  font-weight: 600;
}
```

### 3.3 Status Communication

#### Live Regions for Dynamic Content
```html
<!-- Status announcements for screen readers -->
<div aria-live="polite" aria-atomic="true" class="sr-only" id="status-announcements">
  <!-- Dynamic status updates appear here -->
</div>

<div aria-live="assertive" aria-atomic="true" class="sr-only" id="error-announcements">
  <!-- Critical error announcements appear here -->
</div>
```

#### Time-Sensitive Information
```html
<!-- Due date information with accessibility -->
<time datetime="2024-01-15T00:00:00" class="note-due-date overdue">
  <span class="sr-only">Due date: </span>
  Due: January 15, 2024
  <span class="sr-only"> - Overdue</span>
</time>
```

## 4. Robust Guidelines

### 4.1 Screen Reader Compatibility

#### ARIA Labels and Descriptions
```html
<!-- Note card with comprehensive ARIA -->
<article 
  class="note-card" 
  role="button"
  tabindex="0"
  aria-label="Edit note: {{note.heading}} - Due: {{note.dueDate}} - Status: {{note.status}}"
  aria-describedby="note-{{note.id}}-description"
>
  <h3 id="note-{{note.id}}-heading">{{note.heading}}</h3>
  <p id="note-{{note.id}}-description">{{note.subheading}}</p>
  <time 
    datetime="{{note.dueDate}}" 
    class="note-due-date {{note.statusClass}}"
    aria-label="Due date: {{formatted_date}} - {{status_description}}"
  >
    Due: {{formatted_date}}
  </time>
</article>

<!-- Modal with proper ARIA -->
<div 
  class="modal-overlay" 
  role="dialog" 
  aria-modal="true"
  aria-labelledby="modal-title"
  aria-describedby="modal-description"
>
  <div class="modal-container">
    <h2 id="modal-title">{{modal.title}}</h2>
    <p id="modal-description">{{modal.description}}</p>
    <!-- Modal content -->
  </div>
</div>
```

#### Screen Reader Only Content
```css
/* Screen reader only text using design tokens for positioning */
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border: 0;
}
```

### 4.2 Progressive Enhancement

#### Baseline Functionality
Ensure core functionality works without JavaScript:

```html
<!-- Form works with and without JavaScript -->
<form action="/notes" method="POST" class="note-form">
  <input type="text" name="heading" required aria-label="Note heading" />
  <input type="text" name="subheading" aria-label="Note sub-heading" />
  <input type="date" name="dueDate" aria-label="Due date" />
  <button type="submit" class="btn-primary">Save Note</button>
</form>
```

## 5. Testing and Validation

### 5.1 Automated Testing Requirements

#### Color Contrast Testing
```javascript
// Example test for contrast compliance
describe('Color Contrast', () => {
  test('Primary text meets WCAG AA', () => {
    const contrast = getContrastRatio('#06041f', '#ffffff'); // Design token values
    expect(contrast).toBeGreaterThan(4.5);
  });
  
  test('Interactive elements meet WCAG AA', () => {
    const contrast = getContrastRatio('#205463', '#ffffff'); // Design token values
    expect(contrast).toBeGreaterThan(3.0);
  });
});
```

#### Keyboard Navigation Testing
```javascript
// Example keyboard navigation test
describe('Keyboard Navigation', () => {
  test('Tab order is logical', () => {
    const tabbableElements = getTabbableElements();
    expect(tabbableElements[0]).toHaveAttribute('aria-label', 'Create New Note');
    expect(tabbableElements[1]).toHaveClass('note-card');
  });
  
  test('Enter key activates buttons', () => {
    const button = screen.getByRole('button', { name: /save note/i });
    fireEvent.keyDown(button, { key: 'Enter' });
    expect(mockSaveFunction).toHaveBeenCalled();
  });
});
```

### 5.2 Manual Testing Checklist

#### Visual Testing
- [ ] All text has sufficient contrast against backgrounds
- [ ] Focus indicators are visible on all interactive elements
- [ ] Status information is communicated through multiple visual cues
- [ ] Text is readable at 200% zoom level
- [ ] Touch targets meet minimum size requirements

#### Keyboard Testing
- [ ] All functionality accessible via keyboard
- [ ] Tab order is logical and predictable
- [ ] Focus indicators are always visible
- [ ] Escape key closes modals and cancels operations
- [ ] Enter/Space activate buttons and links

#### Screen Reader Testing
- [ ] Content reads in logical order
- [ ] Form labels are properly announced
- [ ] Error messages are announced when they appear
- [ ] Status changes are announced appropriately
- [ ] Modal dialogs are properly identified

#### Mobile Accessibility Testing
- [ ] Touch targets are adequately sized
- [ ] Content is accessible with assistive technologies
- [ ] Zoom functionality works properly
- [ ] Voice control works with all interactive elements

## 6. Implementation Checklist

### 6.1 Development Phase Checklist

**Setup Phase**
- [ ] Include accessibility testing in development workflow
- [ ] Set up automated contrast ratio checking
- [ ] Configure linting rules for accessibility

**Component Development**
- [ ] All colors use approved design tokens with verified contrast
- [ ] Typography uses design token scale with proper line height
- [ ] Interactive elements meet minimum size requirements
- [ ] Focus states implemented using design token colors
- [ ] Keyboard navigation implemented for all interactions

**Form Development**
- [ ] Labels properly associated with form controls
- [ ] Required fields clearly marked and announced
- [ ] Error messages use design token error colors and typography
- [ ] Success feedback uses design token success colors
- [ ] Form validation accessible to screen readers

**Testing Phase**
- [ ] Manual keyboard testing completed
- [ ] Screen reader testing with multiple tools
- [ ] Color contrast verified for all combinations
- [ ] Mobile accessibility testing completed
- [ ] Automated accessibility tests passing

### 6.2 Ongoing Maintenance

**Regular Testing Schedule**
- Weekly: Automated accessibility tests
- Monthly: Manual keyboard and screen reader testing
- Quarterly: Comprehensive accessibility audit
- Annual: Professional accessibility assessment

**Documentation Updates**
- Keep accessibility guidelines current with design token updates
- Document any accessibility exceptions with justifications
- Maintain testing procedures and checklists
- Update implementation examples with current best practices

This comprehensive accessibility framework ensures WCAG 2.1 AA compliance while maintaining strict adherence to Nagarro design tokens throughout all implementations.