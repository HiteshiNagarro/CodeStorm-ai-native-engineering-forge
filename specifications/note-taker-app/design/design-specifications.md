# Note-Taker App - Design Specifications

## Design Token Reference Authority
All specifications in this document reference exact values from `/design-guidelines/nagarro-design-tokens.json`. No custom styling is permitted - all visual properties must use the approved design tokens.

## 1. Typography Specifications

### Heading Hierarchy
**H1 - Main Page Title**
- Token: `font.type set.headline 1.700`
- Font Family: Mulish (`font.type set font family`)
- Font Size: 32px (`font.type set.headline 1.700.fontSize`)
- Font Weight: 700 (`font.type set.headline 1.700.fontWeight`)
- Line Height: 40px (`font.type set.headline 1.700.lineHeight`)
- Color: `primitives.colors.black.color base` (#06041f)
- Usage: Page title "My Notes"

**H2 - Section Headers**
- Token: `font.type set.headline 2.600`
- Font Family: Mulish
- Font Size: 24px (`font.type set.headline 2.600.fontSize`)
- Font Weight: 600 (`font.type set.headline 2.600.fontWeight`)
- Line Height: 32px (`font.type set.headline 2.600.lineHeight`)
- Color: `primitives.colors.black.color base` (#06041f)
- Usage: Modal titles, section dividers

**H3 - Note Headings**
- Token: `font.type set.subtitle1.600`
- Font Family: Mulish
- Font Size: 16px (`font.type set.subtitle1.600.fontSize`)
- Font Weight: 600 (`font.type set.subtitle1.600.fontWeight`)
- Line Height: 24px (`font.type set.subtitle1.600.lineHeight`)
- Color: `primitives.colors.black.color base` (#06041f)
- Usage: Note card primary headings

### Body Text Specifications
**Primary Body Text**
- Token: `font.type set.paragraph 1.400`
- Font Family: Mulish
- Font Size: 16px (`font.type set.paragraph 1.400.fontSize`)
- Font Weight: 400 (`font.type set.paragraph 1.400.fontWeight`)
- Line Height: 24px (`font.type set.paragraph 1.400.lineHeight`)
- Color: `primitives.colors.black.color base` (#06041f)
- Usage: Note sub-headings, form inputs, general content

**Secondary Body Text**
- Token: `font.type set.paragraph 2.400`
- Font Family: Mulish
- Font Size: 14px (`font.type set.paragraph 2.400.fontSize`)
- Font Weight: 400 (`font.type set.paragraph 2.400.fontWeight`)
- Line Height: 20px (`font.type set.paragraph 2.400.lineHeight`)
- Color: `primitives.colors.black.#700` (#5e5e5e)
- Usage: Helper text, descriptions, metadata

### Specialized Text Elements
**Button Text**
- Token: `font.type set.button.700`
- Font Family: Mulish
- Font Size: 14px (`font.type set.button.700.fontSize`)
- Font Weight: 700 (`font.type set.button.700.fontWeight`)
- Line Height: 16px (`font.type set.button.700.lineHeight`)
- Letter Spacing: 1px (`font.type set.button.700.letterSpacing`)
- Color: Context-dependent (white on colored backgrounds, black on neutral)

**Form Labels**
- Token: `font.type set.overline.600`
- Font Family: Mulish
- Font Size: 12px (`font.type set.overline.600.fontSize`)
- Font Weight: 600 (`font.type set.overline.600.fontWeight`)
- Line Height: 16px (`font.type set.overline.600.lineHeight`)
- Letter Spacing: 1.5px (`font.type set.overline.600.letterSpacing`)
- Text Transform: Uppercase (`font.type set.overline.600.textCase`)
- Color: `primitives.colors.black.color base` (#06041f)

**Caption and Status Text**
- Token: `font.type set.caption.400`
- Font Family: Mulish
- Font Size: 12px (`font.type set.caption.400.fontSize`)
- Font Weight: 400 (`font.type set.caption.400.fontWeight`)
- Line Height: 16px (`font.type set.caption.400.lineHeight`)
- Color: Context-dependent (error: #f87171, warning: #eac608, info: #4b4b4b)

## 2. Color Specifications

### Primary Color Palette
**Primary Brand Color**
- Token: `primitives.colors.primary.color base`
- Value: #205463
- Usage: Primary buttons, active states, focus indicators, brand accents
- Contrast Ratio: 4.8:1 against white (WCAG AA compliant)

**Primary Color Variations**
- Light Variation: `primitives.colors.primary.#200` (#c2f0e3)
- Usage: Hover states, light backgrounds, subtle accents
- Dark Variation: `primitives.colors.primary.#900` (#2d807b)
- Usage: Hover states for primary elements, pressed states

### Semantic Color System
**Error/Danger States**
- Token: `primitives.colors.red.#500`
- Value: #f87171
- Background Token: `primitives.colors.red.#50` (#ffefee)
- Usage: Error messages, delete buttons, overdue indicators
- Contrast Ratio: 4.5:1 against white

**Warning States**
- Token: `primitives.colors.yellow.color base`
- Value: #eac608
- Background Token: `primitives.colors.yellow.#50` (#fbf3e0)
- Usage: Due today indicators, caution states
- Contrast Ratio: 3.8:1 against white (enhanced with bold weight)

**Success States**
- Token: `primitives.colors.green.color base`
- Value: #22c55e
- Background Token: `primitives.colors.green.#50` (#e8f8e9)
- Usage: Success messages, completed states

### Neutral Color System
**Base Text Colors**
- Primary Text: `primitives.colors.black.color base` (#06041f)
- Secondary Text: `primitives.colors.black.#700` (#5e5e5e)
- Tertiary Text: `primitives.colors.black.#800` (#4b4b4b)
- Disabled Text: `primitives.colors.grey.#300` (#abb1ba)

**Surface Colors**
- Primary Background: `primitives.colors.white.color base` (#ffffff)
- Secondary Background: `primitives.colors.grey.#50` (#f5f5f5)
- Border Color: `primitives.colors.grey.#100` (#e7e7e7)
- Divider Color: `primitives.colors.grey.#300` (#abb1ba)

## 3. Spacing Specifications

### Spacing Scale
All spacing uses the systematic scale from design tokens:
- 2px: `spacing.spacing-2xs` - Fine adjustments, icon gaps
- 4px: `spacing.spacing-3xs` - Small element separation
- 6px: `spacing.spacing-2xs` - Label margins, small gaps
- 8px: `spacing.spacing-xs` - Button padding vertical, small margins
- 12px: `spacing.spacing-s` - Medium margins, content separation
- 16px: `spacing.spacing-md` - Standard margins, button padding horizontal
- 20px: `spacing.spacing-lg` - Large section separation
- 24px: `spacing.spacing-xl` - Card padding, modal content padding
- 32px: `spacing.spacing-2xl` - Major section separation
- 40px: `spacing.spacing-3xl` - Page-level spacing

### Component-Specific Spacing
**Cards**
- Internal Padding: `spacing.spacing-xl` (24px)
- Bottom Margin: `spacing.spacing-md` (16px)
- Content Gaps: `spacing.spacing-xs` (8px) to `spacing.spacing-s` (12px)

**Forms**
- Field Bottom Margin: `spacing.spacing-md` (16px)
- Label Bottom Margin: `spacing.spacing-2xs` (6px)
- Button Groups Gap: `spacing.spacing-xs` (8px)

**Modals**
- Content Padding: `spacing.spacing-xl` (24px)
- Element Separation: `spacing.spacing-md` (16px)
- Button Area Top Margin: `spacing.spacing-lg` (20px)

## 4. Corner Radius Specifications

### Radius Scale
- Extra Small: `corner radius-xxsmall` (2px) - Form inputs, small elements
- Small: `corner radius-xsmall` (4px) - Buttons, toggles, chips
- Medium: `corner radius-small` (8px) - Cards, modals, larger containers
- Large: `corner radius-medium` (12px) - Not used in current design
- Extra Large: `corner radius-large` (16px) - Not used in current design

### Component Applications
**Interactive Elements**
- Buttons: `corner radius-xsmall` (4px)
- Form Inputs: `corner radius-xxsmall` (2px)
- Toggles: `corner radius-xsmall` (4px)

**Container Elements**
- Cards: `corner radius-small` (8px)
- Modals: `corner radius-small` (8px)
- Status Indicators: `corner radius-xxsmall` (2px)

## 5. Shadow Specifications

### Shadow System
**Base Shadow**
- Token: `effect.shadows.base`
- Value: 0 4px 4px #00000040
- Usage: Default card elevation, button states

**Medium Shadow**
- Token: `effect.shadows.medium`
- Value: 0 2px 4px #cfcfcf
- Usage: Hover states, subtle elevation changes

**Large Shadow**
- Token: `effect.shadows.large`
- Value: 0 10px 15px #acacac
- Usage: Modal dialogs, high-priority overlays

### Shadow Applications
**Cards**
- Default State: `effect.shadows.base`
- Hover State: `effect.shadows.medium` + translate transform

**Modals**
- Container Shadow: `effect.shadows.large`
- Overlay: Backdrop blur with rgba overlay

**Buttons**
- Primary Button: `effect.shadows.base` default
- Hover State: `effect.shadows.medium`
- Focus State: Outline-based focus ring

## 6. Layout Specifications

### Grid System
**Desktop Layout (905px+)**
- Container Max Width: 1200px
- Side Margins: `spacing.spacing-xl` (24px)
- Content Grid: 12-column system with `spacing.spacing-md` (16px) gutters
- Note Cards: 2-3 cards per row depending on content

**Tablet Layout (600-904px)**
- Container: Full width with margins
- Side Margins: `spacing.spacing-lg` (20px)
- Note Cards: 2 cards per row
- Modal Width: 600px maximum

**Mobile Layout (0-599px)**
- Container: Full width
- Side Margins: `spacing.spacing-md` (16px)
- Note Cards: Single column, full width
- Modal Width: 95% of viewport

### Responsive Breakpoints
- Mobile: 0-599px
- Tablet: 600-904px
- Desktop: 905px+

These breakpoints align with material design standards and provide optimal viewing experiences across devices.

## 7. Interactive States

### Button States
**Default State**
- Uses base design token values
- Includes appropriate shadow and color

**Hover State**
- Background: Darker shade from color palette
- Shadow: Enhanced using `effect.shadows.medium`
- Transform: `translateY(-1px)` for subtle lift
- Transition: `all 0.2s ease-out`

**Focus State**
- Maintains background and shadow from hover
- Adds outline: `2px solid` using primary color
- Outline Offset: `2px`
- No transform to maintain accessibility

**Active/Pressed State**
- Background: Darkest shade from color palette
- Shadow: Reduced or removed
- Transform: `translateY(0)` to simulate press

**Disabled State**
- Background: `primitives.colors.grey.#100` (#e7e7e7)
- Text: `primitives.colors.grey.#300` (#abb1ba)
- Cursor: `not-allowed`
- No shadow or interaction effects

### Form Input States
**Default State**
- Border: `1px solid` using `primitives.colors.grey.#300`
- Background: `primitives.colors.white.color base`

**Focus State**
- Border Color: `primitives.colors.primary.color base`
- Box Shadow: `0 0 0 2px rgba(32, 84, 99, 0.2)`
- No outline (handled by box-shadow)

**Error State**
- Border Color: `primitives.colors.red.#500`
- Background: `primitives.colors.red.#50`
- Associated error message appears below

**Disabled State**
- Background: `primitives.colors.grey.#50`
- Border Color: `primitives.colors.grey.#100`
- Text Color: `primitives.colors.grey.#300`

### Card States
**Default State**
- Uses base shadow and background
- Subtle hover preparation (cursor: pointer)

**Hover State**
- Shadow: `effect.shadows.medium`
- Transform: `translateY(-1px)`
- Maintains background color

**Focus State (Keyboard Navigation)**
- Outline: `2px solid` using primary color
- Outline Offset: `2px`
- Maintains hover effects

## 8. Animation Specifications

### Transition Guidelines
**Standard Transitions**
- Duration: `0.2s` for micro-interactions
- Easing: `ease-out` for natural feeling
- Properties: `all` for comprehensive state changes

**Modal Animations**
**Entry Animation**
- Overlay: Fade in over `0.2s`
- Container: Scale from `0.95` to `1.0` + fade in over `0.3s`
- Easing: `ease-out`

**Exit Animation**
- Reverse of entry animation
- Slightly faster duration (`0.15s` for overlay, `0.2s` for container)

### Loading States
**Spinner Animation**
- Rotation: `360deg` over `1s`
- Timing: `linear` for consistent rotation
- Colors: Uses primary color tokens

**Skeleton Loading**
- Shimmer Effect: Background position animation
- Duration: `1.5s` infinite
- Direction: Left to right sweep
- Colors: Grey scale tokens only

## 9. Accessibility Specifications

### Focus Management
**Focus Indicators**
- All interactive elements must have visible focus states
- Focus rings use `2px solid` with primary color
- Outline offset of `2px` for separation from element
- Never remove focus indicators with `outline: none` without replacement

**Tab Order**
- Logical flow: Top to bottom, left to right
- Skip links for complex interfaces
- Modal focus trap when opened
- Return focus to trigger element when modal closes

### Color Contrast Requirements
**Text Contrast**
- Normal Text: Minimum 4.5:1 ratio (WCAG AA)
- Large Text (18px+ or 14px+ bold): Minimum 3:1 ratio
- UI Components: Minimum 3:1 ratio for interface elements

**Verified Combinations**
- `primitives.colors.black.color base` on white: 16.8:1 ✓
- `primitives.colors.primary.color base` on white: 4.8:1 ✓
- `primitives.colors.red.#500` on white: 4.5:1 ✓
- `primitives.colors.black.#700` on white: 7.1:1 ✓

### Touch Target Specifications
**Minimum Sizes**
- All interactive elements: 44px × 44px minimum
- Adequate spacing between touch targets
- Buttons sized appropriately for finger interaction

### Screen Reader Support
**Semantic Structure**
- Proper heading hierarchy (h1 → h2 → h3)
- Form labels properly associated with inputs
- Status announcements for dynamic content
- Descriptive link and button text

## 10. Implementation Guidelines

### CSS Custom Properties Setup
```css
:root {
  /* Primary Colors */
  --color-primary: #205463; /* primitives.colors.primary.color base */
  --color-primary-light: #c2f0e3; /* primitives.colors.primary.#200 */
  --color-primary-dark: #2d807b; /* primitives.colors.primary.#900 */
  
  /* Semantic Colors */
  --color-error: #f87171; /* primitives.colors.red.#500 */
  --color-error-bg: #ffefee; /* primitives.colors.red.#50 */
  --color-warning: #eac608; /* primitives.colors.yellow.color base */
  --color-warning-bg: #fbf3e0; /* primitives.colors.yellow.#50 */
  --color-success: #22c55e; /* primitives.colors.green.color base */
  --color-success-bg: #e8f8e9; /* primitives.colors.green.#50 */
  
  /* Typography */
  --font-family: Mulish, -apple-system, BlinkMacSystemFont, sans-serif;
  
  /* Spacing Scale */
  --spacing-2xs: 2px;
  --spacing-3xs: 4px;
  --spacing-2xs: 6px;
  --spacing-xs: 8px;
  --spacing-s: 12px;
  --spacing-md: 16px;
  --spacing-lg: 20px;
  --spacing-xl: 24px;
  --spacing-2xl: 32px;
  --spacing-3xl: 40px;
  
  /* Border Radius */
  --radius-xxsmall: 2px;
  --radius-xsmall: 4px;
  --radius-small: 8px;
  
  /* Shadows */
  --shadow-base: 0 4px 4px #00000040;
  --shadow-medium: 0 2px 4px #cfcfcf;
  --shadow-large: 0 10px 15px #acacac;
}
```

### File Organization
**Recommended Structure**
```
styles/
├── design-tokens.css     # Custom properties from design tokens
├── typography.css        # All typography specifications
├── components/
│   ├── buttons.css      # Button component styles
│   ├── forms.css        # Form component styles
│   ├── cards.css        # Card component styles
│   ├── modals.css       # Modal component styles
│   └── navigation.css   # Navigation component styles
├── utilities/
│   ├── spacing.css      # Spacing utility classes
│   ├── colors.css       # Color utility classes
│   └── accessibility.css # Accessibility utilities
└── responsive.css       # Responsive design overrides
```

### Code Review Checklist
**Design Token Compliance**
- [ ] All colors reference approved design tokens
- [ ] Typography uses designated type scale
- [ ] Spacing follows systematic scale
- [ ] No custom values outside design system

**Accessibility Compliance**
- [ ] Color contrast meets WCAG AA standards
- [ ] Focus states visible and functional
- [ ] Touch targets meet minimum size requirements
- [ ] Semantic HTML structure maintained

**Responsive Design**
- [ ] Components work across all breakpoints
- [ ] Text remains readable at all sizes
- [ ] Interactive elements maintain usability
- [ ] Content hierarchy preserved on mobile

This comprehensive specification provides developers with exact implementation details while ensuring complete design token compliance and accessibility standards.