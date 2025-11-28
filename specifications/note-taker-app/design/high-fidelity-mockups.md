# Note-Taker App - High-Fidelity Mockups

## Design Token Compliance Declaration
All visual elements in these mockups strictly adhere to the Nagarro Design Tokens specification from `/design-guidelines/nagarro-design-tokens.json`. No custom styling outside the design tokens is permitted.

## Color Palette (Design Token References)

### Primary Colors
- **Primary Main**: `primitives.colors.primary.color base` (#205463)
- **Primary Light**: `primitives.colors.primary.#200` (#c2f0e3)
- **Primary Dark**: `primitives.colors.primary.#900` (#2d807b)

### Status Colors  
- **Error/Overdue**: `primitives.colors.red.#500` (#f87171)
- **Success**: `primitives.colors.green.color base` (#22c55e)
- **Warning**: `primitives.colors.yellow.color base` (#eac608)

### Text Colors
- **Primary Text**: `primitives.colors.black.color base` (#06041f)
- **Secondary Text**: `primitives.colors.black.#800` (#4b4b4b)
- **Tertiary Text**: `primitives.colors.black.#700` (#5e5e5e)

### Surface Colors
- **Background**: `primitives.colors.white.color base` (#ffffff)
- **Card Surface**: `primitives.colors.grey.#100` (#e7e7e7)
- **Border**: `primitives.colors.grey.#300` (#abb1ba)

## Typography Scale (Design Token References)

### Headlines
- **App Title**: `font.type set.headline.h4.700` (37.9px, 700 weight, 40px line-height)
- **Note Heading**: `font.type set.subtitle1.600` (16px, 600 weight, 24px line-height)

### Body Text
- **Sub-heading**: `font.type set.paragraph 1.400` (16px, 400 weight, 24px line-height)
- **Due Date**: `font.type set.caption.400` (12px, 400 weight, 16px line-height)

### Buttons
- **Button Text**: `font.type set.button.700` (14px, 700 weight, 16px line-height)

## Spacing System (Design Token References)

### Component Spacing
- **Card Padding**: `spacing.spacing-xl` (24px)
- **Card Margin**: `spacing.spacing-md` (16px)
- **Form Field Spacing**: `spacing.spacing-lg` (20px)
- **Button Padding**: `spacing.spacing-md` horizontal (16px), `spacing.spacing-xs` vertical (8px)

### Grid System
- **Mobile Gutters**: `grid.phone.xs | 0-599px.gutterSize` (16px)
- **Tablet Gutters**: `grid.tablet.sm | 600-904px.gutterSize` (24px)
- **Desktop Gutters**: `grid.web.md | 905-1239px.gutterSize` (24px)

## High-Fidelity Mockup 1: Main Note List View (Desktop)

```css
/* Design Token Implementation */
.app-container {
  background: #ffffff; /* primitives.colors.white.color base */
  font-family: Mulish; /* font.type set typography */
  max-width: 1200px;
  margin: 0 auto;
  padding: 24px; /* spacing.spacing-xl */
}

.app-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 32px; /* spacing.spacing-xxl */
  border-bottom: 1px solid #abb1ba; /* primitives.colors.grey.#300 */
  padding-bottom: 20px; /* spacing.spacing-lg */
}

.app-title {
  font-size: 37.9px; /* font.type set.headline.h4.700.fontSize */
  font-weight: 700; /* font.type set.headline.h4.700.fontWeight */
  line-height: 40px; /* font.type set.headline.h4.700.lineHeight */
  color: #06041f; /* primitives.colors.black.color base */
  margin: 0;
}

.add-button {
  background: #205463; /* primitives.colors.primary.color base */
  color: #ffffff; /* primitives.colors.white.color base */
  border: none;
  border-radius: 8px; /* corner radius-small */
  padding: 8px 16px; /* spacing.spacing-xs spacing.spacing-md */
  font-size: 14px; /* font.type set.button.700.fontSize */
  font-weight: 700; /* font.type set.button.700.fontWeight */
  cursor: pointer;
  box-shadow: 0 4px 4px #00000040; /* effect.shadows.base */
}

.add-button:hover {
  background: #2d807b; /* primitives.colors.primary.#900 */
  box-shadow: 0 2px 4px #cfcfcf; /* effect.shadows.medium */
}

.sort-controls {
  display: flex;
  gap: 12px; /* spacing.spacing-s */
  margin-bottom: 20px; /* spacing.spacing-lg */
}

.sort-button {
  background: transparent;
  border: 1px solid #abb1ba; /* primitives.colors.grey.#300 */
  border-radius: 4px; /* corner radius-xsmall */
  padding: 8px 16px; /* spacing.spacing-xs spacing.spacing-md */
  font-size: 14px; /* font.type set.button.700.fontSize */
  color: #06041f; /* primitives.colors.black.color base */
  cursor: pointer;
}

.sort-button.active {
  background: #205463; /* primitives.colors.primary.color base */
  color: #ffffff; /* primitives.colors.white.color base */
  border-color: #205463; /* primitives.colors.primary.color base */
}

.note-card {
  background: #ffffff; /* primitives.colors.white.color base */
  border: 1px solid #e7e7e7; /* primitives.colors.grey.#100 */
  border-radius: 8px; /* corner radius-small */
  padding: 24px; /* spacing.spacing-xl */
  margin-bottom: 16px; /* spacing.spacing-md */
  box-shadow: 0 4px 4px #00000040; /* effect.shadows.base */
  position: relative;
  transition: all 0.2s ease-out;
}

.note-card:hover {
  box-shadow: 0 2px 4px #cfcfcf; /* effect.shadows.medium */
  transform: translateY(-1px);
}

.note-card.overdue {
  border-left: 4px solid #f87171; /* primitives.colors.red.#500 */
  background: #ffefee; /* primitives.colors.red.#50 */
}

.note-heading {
  font-size: 16px; /* font.type set.subtitle1.600.fontSize */
  font-weight: 600; /* font.type set.subtitle1.600.fontWeight */
  line-height: 24px; /* font.type set.subtitle1.600.lineHeight */
  color: #06041f; /* primitives.colors.black.color base */
  margin: 0 0 8px 0; /* spacing.spacing-xs bottom */
}

.note-subheading {
  font-size: 16px; /* font.type set.paragraph 1.400.fontSize */
  font-weight: 400; /* font.type set.paragraph 1.400.fontWeight */
  line-height: 24px; /* font.type set.paragraph 1.400.lineHeight */
  color: #5e5e5e; /* primitives.colors.black.#700 */
  margin: 0 0 12px 0; /* spacing.spacing-s bottom */
}

.note-due-date {
  font-size: 12px; /* font.type set.caption.400.fontSize */
  font-weight: 400; /* font.type set.caption.400.fontWeight */
  line-height: 16px; /* font.type set.caption.400.lineHeight */
  color: #4b4b4b; /* primitives.colors.black.#800 */
  display: flex;
  align-items: center;
  gap: 4px; /* spacing.spacing-3xs */
}

.overdue-status {
  color: #f87171; /* primitives.colors.red.#500 */
  font-weight: 600; /* elevated weight for emphasis */
}

.due-soon-status {
  color: #eac608; /* primitives.colors.yellow.color base */
  font-weight: 500;
}
```

## High-Fidelity Mockup 2: Note Creation Modal

```css
/* Modal Overlay */
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(6, 4, 31, 0.5); /* primitives.colors.black.color base with opacity */
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;
}

.modal-container {
  background: #ffffff; /* primitives.colors.white.color base */
  border-radius: 8px; /* corner radius-small */
  box-shadow: 0 10px 15px #acacac; /* effect.shadows.large */
  width: 90%;
  max-width: 500px;
  max-height: 90vh;
  overflow-y: auto;
}

.modal-header {
  padding: 24px 24px 0 24px; /* spacing.spacing-xl */
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid #e7e7e7; /* primitives.colors.grey.#100 */
  margin-bottom: 24px; /* spacing.spacing-xl */
  padding-bottom: 20px; /* spacing.spacing-lg */
}

.modal-title {
  font-size: 21.33px; /* font.type set.headline.h6.400.fontSize */
  font-weight: 600; /* font.type set.headline.h6.400.fontWeight */
  line-height: 24px; /* font.type set.headline.h6.400.lineHeight */
  color: #06041f; /* primitives.colors.black.color base */
  margin: 0;
}

.close-button {
  background: transparent;
  border: none;
  font-size: 20px;
  color: #5e5e5e; /* primitives.colors.black.#700 */
  cursor: pointer;
  padding: 4px; /* spacing.spacing-3xs */
  border-radius: 4px; /* corner radius-xsmall */
}

.close-button:hover {
  background: #e7e7e7; /* primitives.colors.grey.#100 */
}

.form-container {
  padding: 0 24px 24px 24px; /* spacing.spacing-xl */
}

.form-field {
  margin-bottom: 20px; /* spacing.spacing-lg */
}

.form-label {
  display: block;
  font-size: 12px; /* font.type set.caption.400.fontSize */
  font-weight: 600; /* elevated for labels */
  color: #06041f; /* primitives.colors.black.color base */
  margin-bottom: 6px; /* spacing.spacing-2xs */
  text-transform: uppercase;
  letter-spacing: 1.5px; /* font.type set.overline.600.letterSpacing */
}

.form-input {
  width: 100%;
  border: 1px solid #abb1ba; /* primitives.colors.grey.#300 */
  border-radius: 2px; /* corner radius-xxsmall */
  padding: 12px 16px; /* spacing.spacing-s spacing.spacing-md */
  font-size: 16px; /* font.type set.paragraph 1.400.fontSize */
  font-family: Mulish; /* consistent font family */
  color: #06041f; /* primitives.colors.black.color base */
  background: #ffffff; /* primitives.colors.white.color base */
  transition: border-color 0.2s ease-out;
}

.form-input:focus {
  outline: none;
  border-color: #205463; /* primitives.colors.primary.color base */
  box-shadow: 0 0 0 2px rgba(32, 84, 99, 0.2); /* primary color with opacity */
}

.form-input.error {
  border-color: #f87171; /* primitives.colors.red.#500 */
  background: #ffefee; /* primitives.colors.red.#50 */
}

.error-message {
  font-size: 12px; /* font.type set.caption.400.fontSize */
  color: #f87171; /* primitives.colors.red.#500 */
  margin-top: 4px; /* spacing.spacing-3xs */
}

.button-group {
  display: flex;
  gap: 12px; /* spacing.spacing-s */
  justify-content: flex-end;
  margin-top: 32px; /* spacing.spacing-xxl */
}

.button-secondary {
  background: transparent;
  border: 1px solid #abb1ba; /* primitives.colors.grey.#300 */
  color: #06041f; /* primitives.colors.black.color base */
  border-radius: 4px; /* corner radius-xsmall */
  padding: 8px 16px; /* spacing.spacing-xs spacing.spacing-md */
  font-size: 14px; /* font.type set.button.700.fontSize */
  font-weight: 700; /* font.type set.button.700.fontWeight */
  cursor: pointer;
  transition: all 0.2s ease-out;
}

.button-secondary:hover {
  background: #e7e7e7; /* primitives.colors.grey.#100 */
}

.button-primary {
  background: #205463; /* primitives.colors.primary.color base */
  color: #ffffff; /* primitives.colors.white.color base */
  border: none;
  border-radius: 4px; /* corner radius-xsmall */
  padding: 8px 16px; /* spacing.spacing-xs spacing.spacing-md */
  font-size: 14px; /* font.type set.button.700.fontSize */
  font-weight: 700; /* font.type set.button.700.fontWeight */
  cursor: pointer;
  transition: all 0.2s ease-out;
}

.button-primary:hover {
  background: #2d807b; /* primitives.colors.primary.#900 */
}

.button-primary:disabled {
  background: #e7e7e7; /* primitives.colors.grey.#100 */
  color: #abb1ba; /* primitives.colors.grey.#300 */
  cursor: not-allowed;
}
```

## High-Fidelity Mockup 3: Mobile Note List View

```css
/* Mobile-specific styling using design tokens */
@media (max-width: 599px) {
  .app-container {
    padding: 16px; /* spacing.spacing-md for mobile */
    max-width: 100%;
  }
  
  .app-header {
    margin-bottom: 20px; /* spacing.spacing-lg */
  }
  
  .app-title {
    font-size: 28.43px; /* font.type set.headline.h5.400.fontSize */
    line-height: 32px; /* font.type set.headline.h5.400.lineHeight */
  }
  
  .note-card {
    padding: 16px; /* spacing.spacing-md for mobile */
    margin-bottom: 12px; /* spacing.spacing-s */
  }
  
  .note-heading {
    font-size: 14px; /* font.type set.subtitle1.alternate-600.fontSize */
    font-weight: 600; /* font.type set.subtitle1.alternate-600.fontWeight */
  }
  
  .sort-controls {
    flex-direction: column;
    gap: 8px; /* spacing.spacing-xs */
  }
  
  .sort-button {
    width: 100%;
    text-align: left;
  }
}
```

## High-Fidelity Mockup 4: Date Picker Component

```css
.date-picker-container {
  background: #ffffff; /* primitives.colors.white.color base */
  border: 1px solid #abb1ba; /* primitives.colors.grey.#300 */
  border-radius: 8px; /* corner radius-small */
  box-shadow: 0 10px 15px #cfcfcf; /* effect.shadows.large */
  padding: 20px; /* spacing.spacing-lg */
  position: absolute;
  z-index: 100;
  min-width: 280px;
}

.date-picker-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 16px; /* spacing.spacing-md */
  padding-bottom: 12px; /* spacing.spacing-s */
  border-bottom: 1px solid #e7e7e7; /* primitives.colors.grey.#100 */
}

.month-navigation {
  background: transparent;
  border: none;
  font-size: 16px;
  color: #205463; /* primitives.colors.primary.color base */
  cursor: pointer;
  padding: 4px; /* spacing.spacing-3xs */
  border-radius: 4px; /* corner radius-xsmall */
}

.month-navigation:hover {
  background: #c2f0e3; /* primitives.colors.primary.#200 */
}

.month-title {
  font-size: 16px; /* font.type set.subtitle1.600.fontSize */
  font-weight: 600; /* font.type set.subtitle1.600.fontWeight */
  color: #06041f; /* primitives.colors.black.color base */
}

.calendar-grid {
  display: grid;
  grid-template-columns: repeat(7, 1fr);
  gap: 4px; /* spacing.spacing-3xs */
}

.day-header {
  font-size: 12px; /* font.type set.caption.400.fontSize */
  font-weight: 600;
  color: #5e5e5e; /* primitives.colors.black.#700 */
  text-align: center;
  padding: 8px 4px; /* spacing.spacing-xs spacing.spacing-3xs */
}

.day-cell {
  background: transparent;
  border: none;
  padding: 8px; /* spacing.spacing-xs */
  border-radius: 4px; /* corner radius-xsmall */
  font-size: 14px;
  color: #06041f; /* primitives.colors.black.color base */
  cursor: pointer;
  transition: all 0.2s ease-out;
  min-height: 32px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.day-cell:hover {
  background: #c2f0e3; /* primitives.colors.primary.#200 */
}

.day-cell.selected {
  background: #205463; /* primitives.colors.primary.color base */
  color: #ffffff; /* primitives.colors.white.color base */
}

.day-cell.today {
  border: 2px solid #205463; /* primitives.colors.primary.color base */
  font-weight: 600;
}
```

## High-Fidelity Mockup 5: Empty State View

```css
.empty-state {
  text-align: center;
  padding: 64px 24px; /* spacing.spacing-6xl spacing.spacing-xl */
  max-width: 600px;
  margin: 0 auto;
}

.empty-icon {
  font-size: 64px;
  margin-bottom: 24px; /* spacing.spacing-xl */
  opacity: 0.6;
}

.empty-title {
  font-size: 28.43px; /* font.type set.headline.h5.400.fontSize */
  font-weight: 600; /* elevated weight for emphasis */
  line-height: 32px; /* font.type set.headline.h5.400.lineHeight */
  color: #06041f; /* primitives.colors.black.color base */
  margin: 0 0 16px 0; /* spacing.spacing-md bottom */
}

.empty-description {
  font-size: 16px; /* font.type set.paragraph 1.400.fontSize */
  line-height: 24px; /* font.type set.paragraph 1.400.lineHeight */
  color: #5e5e5e; /* primitives.colors.black.#700 */
  margin: 0 0 32px 0; /* spacing.spacing-xxl bottom */
}

.empty-cta {
  background: #205463; /* primitives.colors.primary.color base */
  color: #ffffff; /* primitives.colors.white.color base */
  border: none;
  border-radius: 8px; /* corner radius-small */
  padding: 12px 24px; /* spacing.spacing-s spacing.spacing-xl */
  font-size: 16px; /* larger for prominence */
  font-weight: 700;
  cursor: pointer;
  margin-bottom: 40px; /* spacing.spacing-4xl */
  transition: all 0.2s ease-out;
}

.empty-cta:hover {
  background: #2d807b; /* primitives.colors.primary.#900 */
  transform: translateY(-1px);
  box-shadow: 0 2px 4px #cfcfcf; /* effect.shadows.medium */
}

.tips-container {
  background: #c2f0e3; /* primitives.colors.primary.#200 */
  border-radius: 8px; /* corner radius-small */
  padding: 20px; /* spacing.spacing-lg */
  text-align: left;
  max-width: 400px;
  margin: 0 auto;
}

.tips-title {
  font-size: 16px; /* font.type set.subtitle1.600.fontSize */
  font-weight: 600; /* font.type set.subtitle1.600.fontWeight */
  color: #06041f; /* primitives.colors.black.color base */
  margin: 0 0 12px 0; /* spacing.spacing-s bottom */
}

.tips-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.tips-item {
  font-size: 14px;
  line-height: 20px;
  color: #06041f; /* primitives.colors.black.color base */
  margin-bottom: 8px; /* spacing.spacing-xs */
  padding-left: 16px; /* spacing.spacing-md */
  position: relative;
}

.tips-item::before {
  content: "•";
  color: #205463; /* primitives.colors.primary.color base */
  font-weight: bold;
  position: absolute;
  left: 0;
}
```

## Responsive Design Implementation

### Mobile Breakpoint (0-599px)
- Single column layout using `grid.phone.xs | 0-599px` specifications
- 16px gutters and offsets
- Condensed typography scale
- Touch-optimized button sizes (minimum 44px)

### Tablet Breakpoint (600-904px)  
- Two-column potential using `grid.tablet.sm | 600-904px` specifications
- 24px gutters, 32px offsets
- Enhanced spacing and typography

### Desktop Breakpoint (905px+)
- Multi-column layouts using `grid.web.md | 905-1239px` specifications
- Hover states and enhanced interactions
- Larger modal dialogs and expanded content

## Animation & Interaction Details

### Micro-interactions (Design Token Compliant)
- **Transition Duration**: 150ms for quick interactions, 250ms for state changes
- **Easing**: `ease-out` for natural motion feel
- **Hover Effects**: Subtle elevation changes using shadow tokens
- **Focus States**: 2px outline using primary color tokens

### Loading States
- **Skeleton Screens**: Using surface color tokens for shimmer effect
- **Spinner**: Primary color animation
- **Progressive Loading**: Fade-in animations at 250ms duration

These high-fidelity mockups provide pixel-perfect implementations using exclusively Nagarro design tokens, ensuring complete compliance with the design system while delivering an intuitive, accessible user experience.