# Note-Taker App - Wireframes

## Screen Inventory

Based on the requirements analysis, the Note-Taker App requires these primary screens:

1. **Main Note List View** - Primary interface (90% of user time)
2. **Note Creation Modal** - Overlay for new note entry
3. **Note Edit Modal** - Overlay for editing existing notes
4. **Empty State View** - First-time user interface
5. **Error State Views** - Error handling interfaces

## Wireframe 1: Main Note List View (Desktop)

```
┌─────────────────────────────────────────────────────────────────────┐
│                        Note-Taker App                                  │
├─────────────────────────────────────────────────────────────────────┤
│                                                               [+ Add] │
│ Sort: [Chronological ▼] [Due Date]                                    │
├─────────────────────────────────────────────────────────────────────┤
│                                                                       │
│ ┌─────────────────────────────────────────────────────────────────┐ │
│ │ [!] Project Presentation Prep                              [⋯] │ │
│ │     Finalize slides and practice presentation                   │ │
│ │     📅 Due in 2 days (Nov 21, 2025)                           │ │
│ └─────────────────────────────────────────────────────────────────┘ │
│                                                                       │
│ ┌─────────────────────────────────────────────────────────────────┐ │
│ │ 🔴 Review Budget Report                                     [⋯] │ │
│ │     Check Q4 expenses and revenue                               │ │
│ │     📅 Overdue by 1 day (Nov 18, 2025)                        │ │
│ └─────────────────────────────────────────────────────────────────┘ │
│                                                                       │
│ ┌─────────────────────────────────────────────────────────────────┐ │
│ │ Meeting with Design Team                                    [⋯] │ │
│ │     Discuss new app features and timeline                       │ │
│ │     📅 Due today (Nov 19, 2025)                               │ │
│ └─────────────────────────────────────────────────────────────────┘ │
│                                                                       │
│ ┌─────────────────────────────────────────────────────────────────┐ │
│ │ Order Office Supplies                                       [⋯] │ │
│ │     Notebooks, pens, and whiteboard markers                     │ │
│ │     📅 Due in 5 days (Nov 24, 2025)                           │ │
│ └─────────────────────────────────────────────────────────────────┘ │
│                                                                       │
└─────────────────────────────────────────────────────────────────────┘
```

**Key Elements:**
- App header with title
- Add button prominently placed (top-right)
- Sort controls (toggle between chronological/due date)
- Note cards with visual hierarchy:
  - Status indicator (left edge color/icon)
  - Heading (primary text)
  - Sub-heading (secondary text)
  - Due date with calculated status
  - Actions menu (three dots)

## Wireframe 2: Main Note List View (Mobile)

```
┌─────────────────────────────┐
│    📝 Note-Taker App    [+] │
├─────────────────────────────┤
│ Sort: [Chronological ▼]     │
├─────────────────────────────┤
│                             │
│ ┌─────────────────────────┐ │
│ │ 🔴 Budget Report    [⋯] │ │
│ │   Check Q4 expenses     │ │
│ │   📅 Overdue by 1 day  │ │
│ └─────────────────────────┘ │
│                             │
│ ┌─────────────────────────┐ │
│ │ [!] Presentation    [⋯] │ │
│ │    Finalize slides      │ │
│ │    📅 Due in 2 days    │ │
│ └─────────────────────────┘ │
│                             │
│ ┌─────────────────────────┐ │
│ │ Design Meeting      [⋯] │ │
│ │   App features talk     │ │
│ │   📅 Due today         │ │
│ └─────────────────────────┘ │
│                             │
│ ┌─────────────────────────┐ │
│ │ Office Supplies     [⋯] │ │
│ │   Order notebooks       │ │
│ │   📅 Due in 5 days     │ │
│ └─────────────────────────┘ │
│                             │
└─────────────────────────────┘
```

**Mobile Adaptations:**
- Condensed header with icon
- Single-column layout
- Shorter text in note cards
- Touch-optimized button sizes
- Simplified sort controls

## Wireframe 3: Note Creation Modal

```
                    ┌───────────────────────────────────┐
                    │        Create New Note        [×] │
                    ├───────────────────────────────────┤
                    │                                   │
                    │  Heading *                        │
                    │  ┌─────────────────────────────┐  │
                    │  │ Enter note heading...       │  │
                    │  └─────────────────────────────┘  │
                    │                                   │
                    │  Sub-heading *                    │
                    │  ┌─────────────────────────────┐  │
                    │  │ Enter additional details... │  │
                    │  └─────────────────────────────┘  │
                    │                                   │
                    │  Due Date *                       │
                    │  ┌─────────────────────────────┐  │
                    │  │ 📅 Nov 20, 2025        [▼] │  │
                    │  └─────────────────────────────┘  │
                    │                                   │
                    │     [Cancel]        [Save Note]   │
                    │                                   │
                    └───────────────────────────────────┘
```

**Form Elements:**
- Modal overlay with backdrop
- Three required fields clearly labeled
- Input validation indicators (* required)
- Date picker with tomorrow's date as default
- Clear action buttons (Cancel/Save)
- Close button (×) in header

## Wireframe 4: Note Edit Modal

```
                    ┌───────────────────────────────────┐
                    │         Edit Note             [×] │
                    ├───────────────────────────────────┤
                    │                                   │
                    │  Heading *                        │
                    │  ┌─────────────────────────────┐  │
                    │  │ Project Presentation Prep   │  │
                    │  └─────────────────────────────┘  │
                    │                                   │
                    │  Sub-heading *                    │
                    │  ┌─────────────────────────────┐  │
                    │  │ Finalize slides and practice│  │
                    │  └─────────────────────────────┘  │
                    │                                   │
                    │  Due Date *                       │
                    │  ┌─────────────────────────────┐  │
                    │  │ 📅 Nov 21, 2025        [▼] │  │
                    │  └─────────────────────────────┘  │
                    │                                   │
                    │  [Delete Note]                    │
                    │                                   │
                    │     [Cancel]      [Update Note]   │
                    │                                   │
                    └───────────────────────────────────┘
```

**Edit Features:**
- Same form structure as creation
- Pre-populated with existing values
- Delete option available
- Update button instead of Save
- Maintains validation requirements

## Wireframe 5: Empty State View

```
┌─────────────────────────────────────────────────────────────────────┐
│                        Note-Taker App                                  │
├─────────────────────────────────────────────────────────────────────┤
│                                                                       │
│                                                                       │
│                           📝                                         │
│                                                                       │
│                  No notes yet. Let's get started!                    │
│                                                                       │
│            Capture your thoughts and never miss a deadline           │
│                                                                       │
│                       [Create Your First Note]                       │
│                                                                       │
│                                                                       │
│   ┌─────────────────────────────────────────────────────────────┐   │
│   │                     Quick Tips:                             │   │
│   │   • Each note needs a heading, details, and due date       │   │
│   │   • Red highlighting shows overdue items                   │   │
│   │   • Sort by creation date or due date                      │   │
│   │   • No login required - start immediately                  │   │
│   └─────────────────────────────────────────────────────────────┘   │
│                                                                       │
└─────────────────────────────────────────────────────────────────────┘
```

**Empty State Components:**
- Large, friendly icon
- Clear value proposition
- Prominent call-to-action
- Helpful tips for new users
- Welcoming, encouraging tone

## Wireframe 6: Date Picker Component

```
                    ┌─────────────────────────────┐
                    │    📅 Select Due Date      │
                    ├─────────────────────────────┤
                    │   « November 2025 »         │
                    ├─────────────────────────────┤
                    │ Su Mo Tu We Th Fr Sa        │
                    │                 1  2        │
                    │  3  4  5  6  7  8  9        │
                    │ 10 11 12 13 14 15 16        │
                    │ 17 18 [19] 20 21 22 23      │
                    │ 24 25 26 27 28 29 30        │
                    ├─────────────────────────────┤
                    │        [Cancel] [Select]    │
                    └─────────────────────────────┘
```

**Date Picker Features:**
- Current date highlighted
- Tomorrow pre-selected (default)
- Month navigation
- Clear action buttons
- Keyboard navigation support

## Wireframe 7: Error State View

```
┌─────────────────────────────────────────────────────────────────────┐
│                        Note-Taker App                                  │
├─────────────────────────────────────────────────────────────────────┤
│                                                                       │
│                                                                       │
│                           ⚠️                                         │
│                                                                       │
│                    Oops! Something went wrong                        │
│                                                                       │
│              Unable to load your notes. Please try again.            │
│                                                                       │
│                         [Try Again]                                  │
│                                                                       │
│                                                                       │
│   If the problem persists, your notes are safely stored locally      │
│   and will reappear when the issue is resolved.                      │
│                                                                       │
└─────────────────────────────────────────────────────────────────────┘
```

**Error Handling:**
- Clear problem identification
- Recovery action provided
- Reassurance about data safety
- Consistent visual design

## Wireframe 8: Confirmation Dialog

```
                    ┌───────────────────────────────────┐
                    │        Confirm Deletion           │
                    ├───────────────────────────────────┤
                    │                                   │
                    │  Are you sure you want to delete  │
                    │  this note?                       │
                    │                                   │
                    │  "Project Presentation Prep"      │
                    │                                   │
                    │  This action cannot be undone.    │
                    │                                   │
                    │     [Cancel]        [Delete]      │
                    │                                   │
                    └───────────────────────────────────┘
```

**Confirmation Features:**
- Clear action description
- Note identification
- Warning about permanence
- Safe default (Cancel)

## Responsive Breakpoints

### Mobile (320px - 599px)
- Single column layout
- Stacked sort controls
- Simplified note cards
- Full-width modals
- Touch-optimized spacing

### Tablet (600px - 904px)
- Wider note cards
- Side-by-side sort controls
- Modal dialogs centered
- Improved typography scale

### Desktop (905px+)
- Multi-column potential
- Hover states activated
- Enhanced sort controls
- Larger modal dialogs
- Mouse-optimized interactions

## Design Token Application

### Layout Structure
- **Container Max Width**: Based on grid system tokens
- **Gutters**: `grid.{breakpoint}.gutterSize` values
- **Padding**: `spacing.spacing-*` scale

### Card Components
- **Border Radius**: `corner radius-small` (8px)
- **Shadow**: `effect.shadows.base`
- **Padding**: `spacing.spacing-lg` (20px)

### Typography Hierarchy
- **App Title**: `font.type set.headline.h3.600`
- **Note Heading**: `font.type set.subtitle1.600`
- **Note Sub-heading**: `font.type set.paragraph 1.400`
- **Due Date**: `font.type set.caption.400`

### Color Applications
- **Primary Actions**: `colors tokens.colors.brand.primary.main`
- **Overdue Status**: `colors tokens.colors.error.main`
- **Background**: `colors tokens.colors.surface.surface`
- **Text**: `colors tokens.colors.type.primary`

These wireframes provide the structural foundation for the high-fidelity designs, ensuring all user flows are supported with clear, accessible interfaces that align with design token specifications.