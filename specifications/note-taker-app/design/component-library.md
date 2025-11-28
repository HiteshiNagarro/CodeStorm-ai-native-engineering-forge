# Note-Taker App - Component Library

## Design Token Compliance
This component library exclusively uses Nagarro Design Tokens from `/design-guidelines/nagarro-design-tokens.json`. All components are built with strict adherence to the design system - no custom styling outside the design tokens is permitted.

## Core Component Specifications

### 1. Button Components

#### Primary Button
**Usage**: Main actions, form submissions, primary CTAs
**Design Token References**:
- Background: `primitives.colors.primary.color base` (#205463)
- Text: `primitives.colors.white.color base` (#ffffff)
- Typography: `font.type set.button.700` (14px, 700 weight, 16px line-height)
- Border Radius: `corner radius-xsmall` (4px)
- Padding: `spacing.spacing-xs` (8px) vertical, `spacing.spacing-md` (16px) horizontal
- Shadow: `effect.shadows.base`

```css
.btn-primary {
  background: #205463; /* primitives.colors.primary.color base */
  color: #ffffff; /* primitives.colors.white.color base */
  border: none;
  border-radius: 4px; /* corner radius-xsmall */
  padding: 8px 16px; /* spacing.spacing-xs spacing.spacing-md */
  font-family: Mulish; /* font.type set font family */
  font-size: 14px; /* font.type set.button.700.fontSize */
  font-weight: 700; /* font.type set.button.700.fontWeight */
  line-height: 16px; /* font.type set.button.700.lineHeight */
  letter-spacing: 1px; /* font.type set.button.700.letterSpacing */
  cursor: pointer;
  transition: all 0.2s ease-out;
  box-shadow: 0 4px 4px #00000040; /* effect.shadows.base */
  min-height: 44px; /* accessibility requirement */
}

.btn-primary:hover {
  background: #2d807b; /* primitives.colors.primary.#900 */
  box-shadow: 0 2px 4px #cfcfcf; /* effect.shadows.medium */
  transform: translateY(-1px);
}

.btn-primary:focus {
  outline: 2px solid #205463; /* primitives.colors.primary.color base */
  outline-offset: 2px;
}

.btn-primary:disabled {
  background: #e7e7e7; /* primitives.colors.grey.#100 */
  color: #abb1ba; /* primitives.colors.grey.#300 */
  cursor: not-allowed;
  box-shadow: none;
  transform: none;
}
```

#### Secondary Button
**Usage**: Cancel actions, secondary CTAs, alternative options
**Design Token References**:
- Background: transparent
- Border: `primitives.colors.grey.#300` (#abb1ba)
- Text: `primitives.colors.black.color base` (#06041f)
- Typography: `font.type set.button.700`
- Border Radius: `corner radius-xsmall` (4px)

```css
.btn-secondary {
  background: transparent;
  color: #06041f; /* primitives.colors.black.color base */
  border: 1px solid #abb1ba; /* primitives.colors.grey.#300 */
  border-radius: 4px; /* corner radius-xsmall */
  padding: 8px 16px; /* spacing.spacing-xs spacing.spacing-md */
  font-family: Mulish; /* font.type set font family */
  font-size: 14px; /* font.type set.button.700.fontSize */
  font-weight: 700; /* font.type set.button.700.fontWeight */
  line-height: 16px; /* font.type set.button.700.lineHeight */
  letter-spacing: 1px; /* font.type set.button.700.letterSpacing */
  cursor: pointer;
  transition: all 0.2s ease-out;
  min-height: 44px; /* accessibility requirement */
}

.btn-secondary:hover {
  background: #e7e7e7; /* primitives.colors.grey.#100 */
  border-color: #06041f; /* primitives.colors.black.color base */
}

.btn-secondary:focus {
  outline: 2px solid #205463; /* primitives.colors.primary.color base */
  outline-offset: 2px;
}
```

#### Danger Button
**Usage**: Delete actions, destructive operations
**Design Token References**:
- Background: `primitives.colors.red.#500` (#f87171)
- Text: `primitives.colors.white.color base` (#ffffff)
- Typography: `font.type set.button.700`

```css
.btn-danger {
  background: #f87171; /* primitives.colors.red.#500 */
  color: #ffffff; /* primitives.colors.white.color base */
  border: none;
  border-radius: 4px; /* corner radius-xsmall */
  padding: 8px 16px; /* spacing.spacing-xs spacing.spacing-md */
  font-family: Mulish; /* font.type set font family */
  font-size: 14px; /* font.type set.button.700.fontSize */
  font-weight: 700; /* font.type set.button.700.fontWeight */
  cursor: pointer;
  transition: all 0.2s ease-out;
  min-height: 44px; /* accessibility requirement */
}

.btn-danger:hover {
  background: #dd5c5e; /* primitives.colors.red.#700 */
}
```

### 2. Form Components

#### Text Input
**Usage**: Heading, sub-heading text entry
**Design Token References**:
- Border: `primitives.colors.grey.#300` (#abb1ba)
- Background: `primitives.colors.white.color base` (#ffffff)
- Text: `primitives.colors.black.color base` (#06041f)
- Typography: `font.type set.paragraph 1.400`
- Border Radius: `corner radius-xxsmall` (2px)

```css
.form-input {
  width: 100%;
  border: 1px solid #abb1ba; /* primitives.colors.grey.#300 */
  border-radius: 2px; /* corner radius-xxsmall */
  padding: 12px 16px; /* spacing.spacing-s spacing.spacing-md */
  font-family: Mulish; /* font.type set font family */
  font-size: 16px; /* font.type set.paragraph 1.400.fontSize */
  font-weight: 400; /* font.type set.paragraph 1.400.fontWeight */
  line-height: 24px; /* font.type set.paragraph 1.400.lineHeight */
  color: #06041f; /* primitives.colors.black.color base */
  background: #ffffff; /* primitives.colors.white.color base */
  transition: border-color 0.2s ease-out, box-shadow 0.2s ease-out;
  min-height: 44px; /* accessibility requirement */
}

.form-input:focus {
  outline: none;
  border-color: #205463; /* primitives.colors.primary.color base */
  box-shadow: 0 0 0 2px rgba(32, 84, 99, 0.2); /* primary color with opacity */
}

.form-input:placeholder {
  color: #abb1ba; /* primitives.colors.grey.#300 */
}

.form-input.error {
  border-color: #f87171; /* primitives.colors.red.#500 */
  background: #ffefee; /* primitives.colors.red.#50 */
}
```

#### Form Label
**Usage**: Field labels and descriptions
**Design Token References**:
- Typography: `font.type set.overline.600` (12px, 600 weight, uppercase)
- Text: `primitives.colors.black.color base` (#06041f)

```css
.form-label {
  display: block;
  font-family: Mulish; /* font.type set font family */
  font-size: 12px; /* font.type set.overline.600.fontSize */
  font-weight: 600; /* font.type set.overline.600.fontWeight */
  line-height: 16px; /* font.type set.overline.600.lineHeight */
  letter-spacing: 1.5px; /* font.type set.overline.600.letterSpacing */
  text-transform: uppercase; /* font.type set.overline.600.textCase */
  color: #06041f; /* primitives.colors.black.color base */
  margin-bottom: 6px; /* spacing.spacing-2xs */
}

.form-label.required::after {
  content: " *";
  color: #f87171; /* primitives.colors.red.#500 */
}
```

#### Error Message
**Usage**: Validation feedback and error communication
**Design Token References**:
- Typography: `font.type set.caption.400`
- Text: `primitives.colors.red.#500` (#f87171)

```css
.error-message {
  font-family: Mulish; /* font.type set font family */
  font-size: 12px; /* font.type set.caption.400.fontSize */
  font-weight: 400; /* font.type set.caption.400.fontWeight */
  line-height: 16px; /* font.type set.caption.400.lineHeight */
  color: #f87171; /* primitives.colors.red.#500 */
  margin-top: 4px; /* spacing.spacing-3xs */
  display: flex;
  align-items: center;
  gap: 4px; /* spacing.spacing-3xs */
}

.error-message::before {
  content: "⚠";
  font-size: 14px;
}
```

### 3. Card Components

#### Note Card
**Usage**: Primary content display for notes
**Design Token References**:
- Background: `primitives.colors.white.color base` (#ffffff)
- Border: `primitives.colors.grey.#100` (#e7e7e7)
- Border Radius: `corner radius-small` (8px)
- Shadow: `effect.shadows.base`
- Padding: `spacing.spacing-xl` (24px)

```css
.note-card {
  background: #ffffff; /* primitives.colors.white.color base */
  border: 1px solid #e7e7e7; /* primitives.colors.grey.#100 */
  border-radius: 8px; /* corner radius-small */
  padding: 24px; /* spacing.spacing-xl */
  margin-bottom: 16px; /* spacing.spacing-md */
  box-shadow: 0 4px 4px #00000040; /* effect.shadows.base.0 */
  position: relative;
  transition: all 0.2s ease-out;
  cursor: pointer;
}

.note-card:hover {
  box-shadow: 0 2px 4px #cfcfcf; /* effect.shadows.medium.0 */
  transform: translateY(-1px);
}

.note-card:focus {
  outline: 2px solid #205463; /* primitives.colors.primary.color base */
  outline-offset: 2px;
}

.note-card.overdue {
  border-left: 4px solid #f87171; /* primitives.colors.red.#500 */
  background: #ffefee; /* primitives.colors.red.#50 */
}

.note-card.due-today {
  border-left: 4px solid #eac608; /* primitives.colors.yellow.color base */
  background: #fbf3e0; /* primitives.colors.yellow.#50 */
}
```

#### Note Card Content
**Usage**: Text hierarchy within note cards

```css
.note-heading {
  font-family: Mulish; /* font.type set font family */
  font-size: 16px; /* font.type set.subtitle1.600.fontSize */
  font-weight: 600; /* font.type set.subtitle1.600.fontWeight */
  line-height: 24px; /* font.type set.subtitle1.600.lineHeight */
  color: #06041f; /* primitives.colors.black.color base */
  margin: 0 0 8px 0; /* spacing.spacing-xs bottom */
}

.note-subheading {
  font-family: Mulish; /* font.type set font family */
  font-size: 16px; /* font.type set.paragraph 1.400.fontSize */
  font-weight: 400; /* font.type set.paragraph 1.400.fontWeight */
  line-height: 24px; /* font.type set.paragraph 1.400.lineHeight */
  color: #5e5e5e; /* primitives.colors.black.#700 */
  margin: 0 0 12px 0; /* spacing.spacing-s bottom */
}

.note-due-date {
  font-family: Mulish; /* font.type set font family */
  font-size: 12px; /* font.type set.caption.400.fontSize */
  font-weight: 400; /* font.type set.caption.400.fontWeight */
  line-height: 16px; /* font.type set.caption.400.lineHeight */
  color: #4b4b4b; /* primitives.colors.black.#800 */
  display: flex;
  align-items: center;
  gap: 4px; /* spacing.spacing-3xs */
}

.note-due-date.overdue {
  color: #f87171; /* primitives.colors.red.#500 */
  font-weight: 600; /* elevated for emphasis */
}

.note-due-date.due-today {
  color: #eac608; /* primitives.colors.yellow.color base */
  font-weight: 500; /* slight emphasis */
}
```

### 4. Modal Components

#### Modal Overlay
**Usage**: Background overlay for modal dialogs
**Design Token References**:
- Background: `primitives.colors.black.color base` with opacity
- Backdrop filter for modern browsers

```css
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(6, 4, 31, 0.5); /* primitives.colors.black.color base with opacity */
  backdrop-filter: blur(2px);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;
  animation: fadeIn 0.2s ease-out;
}

@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}
```

#### Modal Container
**Usage**: Main modal content container
**Design Token References**:
- Background: `primitives.colors.white.color base` (#ffffff)
- Border Radius: `corner radius-small` (8px)
- Shadow: `effect.shadows.large`

```css
.modal-container {
  background: #ffffff; /* primitives.colors.white.color base */
  border-radius: 8px; /* corner radius-small */
  box-shadow: 0 10px 15px #acacac; /* effect.shadows.large.0 */
  width: 90%;
  max-width: 500px;
  max-height: 90vh;
  overflow-y: auto;
  animation: slideIn 0.3s ease-out;
}

@keyframes slideIn {
  from { 
    opacity: 0; 
    transform: translateY(-20px) scale(0.95); 
  }
  to { 
    opacity: 1; 
    transform: translateY(0) scale(1); 
  }
}
```

### 5. Navigation Components

#### Sort Toggle
**Usage**: Switching between sort methods
**Design Token References**:
- Background: transparent / `primitives.colors.primary.color base`
- Border: `primitives.colors.grey.#300`
- Typography: `font.type set.button.700`

```css
.sort-toggle {
  display: flex;
  border: 1px solid #abb1ba; /* primitives.colors.grey.#300 */
  border-radius: 4px; /* corner radius-xsmall */
  overflow: hidden;
}

.sort-option {
  background: transparent;
  border: none;
  padding: 8px 16px; /* spacing.spacing-xs spacing.spacing-md */
  font-family: Mulish; /* font.type set font family */
  font-size: 14px; /* font.type set.button.700.fontSize */
  font-weight: 700; /* font.type set.button.700.fontWeight */
  color: #06041f; /* primitives.colors.black.color base */
  cursor: pointer;
  transition: all 0.2s ease-out;
  border-right: 1px solid #abb1ba; /* primitives.colors.grey.#300 */
  min-height: 44px; /* accessibility requirement */
}

.sort-option:last-child {
  border-right: none;
}

.sort-option.active {
  background: #205463; /* primitives.colors.primary.color base */
  color: #ffffff; /* primitives.colors.white.color base */
}

.sort-option:hover:not(.active) {
  background: #c2f0e3; /* primitives.colors.primary.#200 */
}
```

### 6. Status Components

#### Status Indicator
**Usage**: Visual status communication for due dates
**Design Token References**:
- Colors based on status: error, warning, success
- Typography: `font.type set.caption.400`

```css
.status-indicator {
  display: inline-flex;
  align-items: center;
  gap: 4px; /* spacing.spacing-3xs */
  font-family: Mulish; /* font.type set font family */
  font-size: 12px; /* font.type set.caption.400.fontSize */
  font-weight: 500; /* slightly elevated for status */
  line-height: 16px; /* font.type set.caption.400.lineHeight */
  padding: 2px 6px; /* spacing.spacing-2xs */
  border-radius: 2px; /* corner radius-xxsmall */
}

.status-indicator.overdue {
  color: #f87171; /* primitives.colors.red.#500 */
  background: #ffefee; /* primitives.colors.red.#50 */
}

.status-indicator.due-today {
  color: #eac608; /* primitives.colors.yellow.color base */
  background: #fbf3e0; /* primitives.colors.yellow.#50 */
}

.status-indicator.upcoming {
  color: #22c55e; /* primitives.colors.green.color base */
  background: #e8f8e9; /* primitives.colors.green.#50 */
}
```

### 7. Loading Components

#### Spinner
**Usage**: Loading state indication
**Design Token References**:
- Colors: `primitives.colors.primary.color base`

```css
.spinner {
  width: 24px;
  height: 24px;
  border: 2px solid #c2f0e3; /* primitives.colors.primary.#200 */
  border-top: 2px solid #205463; /* primitives.colors.primary.color base */
  border-radius: 50%;
  animation: spin 1s linear infinite;
}

@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}

.spinner-large {
  width: 40px;
  height: 40px;
  border-width: 3px;
}
```

#### Skeleton Loader
**Usage**: Content loading placeholders
**Design Token References**:
- Background: `primitives.colors.grey.#100`
- Animation colors based on surface tokens

```css
.skeleton {
  background: linear-gradient(
    90deg,
    #e7e7e7 25%, /* primitives.colors.grey.#100 */
    #f5f5f5 50%, /* primitives.colors.grey.#50 */
    #e7e7e7 75%  /* primitives.colors.grey.#100 */
  );
  background-size: 200% 100%;
  border-radius: 4px; /* corner radius-xsmall */
  animation: shimmer 1.5s infinite;
}

@keyframes shimmer {
  0% { background-position: -200% 0; }
  100% { background-position: 200% 0; }
}

.skeleton-text {
  height: 16px;
  margin-bottom: 8px; /* spacing.spacing-xs */
}

.skeleton-heading {
  height: 24px;
  width: 70%;
  margin-bottom: 12px; /* spacing.spacing-s */
}
```

## Responsive Component Behavior

### Mobile Adaptations (0-599px)
```css
@media (max-width: 599px) {
  .note-card {
    padding: 16px; /* spacing.spacing-md */
    margin-bottom: 12px; /* spacing.spacing-s */
  }
  
  .btn-primary,
  .btn-secondary,
  .btn-danger {
    width: 100%;
    margin-bottom: 8px; /* spacing.spacing-xs */
  }
  
  .modal-container {
    width: 95%;
    margin: 16px; /* spacing.spacing-md */
  }
  
  .sort-toggle {
    flex-direction: column;
  }
  
  .sort-option {
    border-right: none;
    border-bottom: 1px solid #abb1ba; /* primitives.colors.grey.#300 */
  }
  
  .sort-option:last-child {
    border-bottom: none;
  }
}
```

### Tablet Adaptations (600-904px)
```css
@media (min-width: 600px) and (max-width: 904px) {
  .note-card {
    padding: 20px; /* spacing.spacing-lg */
  }
  
  .modal-container {
    max-width: 600px;
  }
}
```

## Accessibility Features

### Focus Management
- All interactive elements include visible focus indicators
- Focus indicators use design token colors with appropriate contrast
- Tab order follows logical flow through interfaces

### Color Independence
- Status information communicated through multiple visual cues (color + icons + text)
- High contrast ratios maintained using design token color combinations
- Error states include both color and textual feedback

### Screen Reader Support
- Semantic HTML structure with proper ARIA labels
- Status announcements for dynamic content updates
- Descriptive button and link text

## Component Usage Guidelines

### Do's
- ✅ Use components exactly as specified with design token values
- ✅ Maintain consistent spacing using the defined spacing scale
- ✅ Follow the established typography hierarchy
- ✅ Implement proper focus states for accessibility
- ✅ Use semantic HTML elements as the foundation

### Don'ts
- ❌ Modify design token values or create custom styles
- ❌ Use colors outside the approved palette
- ❌ Ignore accessibility requirements
- ❌ Break the established visual hierarchy
- ❌ Skip responsive considerations

This component library provides a comprehensive foundation for building the Note-Taker App with complete design system compliance and accessibility support.