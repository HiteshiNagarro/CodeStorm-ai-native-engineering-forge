# Note-Taker App - User Flows & Journey Maps

## Primary User Flows

### 1. First-Time User Journey
```
App Launch → Landing Screen → Create First Note → View Note List → Success
```

**Flow Details:**
1. **App Launch (Entry Point)**
   - User opens application URL
   - No authentication required - immediate access
   - Landing displays empty state with create note CTA

2. **Create First Note**
   - User clicks "Create Note" button
   - Modal/form opens with three required fields:
     - Heading (text input)
     - Sub-heading (text input)  
     - Due date (date picker, defaults to tomorrow)
   - Real-time validation feedback
   - Auto-save on completion

3. **View Note List**
   - Note appears as card in chronological list
   - Card displays: heading, sub-heading, due date status
   - Sort toggle visible (chronological/due date)

4. **Success State**
   - User understands core functionality
   - Ready for continued use

### 2. Daily Note Management Flow
```
App Launch → Scan Notes → Create/Edit/Delete → Sort/Organize → Exit
```

**Flow Details:**
1. **Quick Review**
   - User opens app to review existing notes
   - Visual scanning for overdue items (red highlights)
   - Priority assessment based on due date status

2. **Note Actions**
   - **Create**: Add new note with structured fields
   - **Edit**: In-place editing of existing notes
   - **Delete**: Remove completed/irrelevant notes

3. **Organization**
   - Toggle between chronological and due date sorting
   - Overdue items automatically prioritized at top

### 3. Note Creation Flow (Detailed)
```
Entry Point → Form Display → Field Entry → Validation → Save → List Update
```

**Detailed Steps:**
1. **Trigger Creation**
   - Click "+" button or "Add Note" CTA
   - Modal overlay appears with form

2. **Form Interaction**
   - **Heading Field**: 
     - Focus indicator using design tokens
     - Real-time character feedback
     - Required field validation
   
   - **Sub-heading Field**:
     - Secondary information input
     - Same validation patterns as heading
   
   - **Due Date Field**:
     - Date picker component
     - Default: tomorrow's date
     - Visual calendar with navigation

3. **Validation & Save**
   - All fields required - progressive validation
   - Save button activates when all fields complete
   - Success feedback on save completion

4. **Return to List**
   - Modal closes automatically
   - New note appears in appropriate position
   - Smooth transition animation

### 4. Note Editing Flow
```
Note Selection → Edit Mode → Field Updates → Save → List Refresh
```

**Interaction Pattern:**
1. **Edit Trigger**
   - Click/tap on note card
   - Edit icon/button within card
   - Modal opens with pre-populated fields

2. **Field Modification**
   - Same form interface as creation
   - Pre-filled with existing values
   - Live validation maintains integrity

3. **Save & Update**
   - Changes persist immediately
   - Position maintained unless sorting changes
   - Visual feedback confirms update

### 5. Sorting & Organization Flow
```
Default View → Sort Toggle → List Reorder → Status Recognition
```

**Sorting Behavior:**
1. **Default State**: Chronological order (newest first)
2. **Due Date Toggle**: Earliest due dates first
3. **Overdue Priority**: Always at top regardless of sort method
4. **Visual Indicators**: Clear indication of current sort method

## User Journey Maps

### Journey Map 1: New User Onboarding
**Persona**: Quick Note Taker - First time user

| Phase | User Actions | Thoughts | Emotions | Pain Points | Opportunities |
|-------|-------------|----------|-----------|-------------|---------------|
| **Discovery** | Opens app link | "Is this simple to use?" | Curious, Skeptical | Unclear value proposition | Clear, immediate value demonstration |
| **First Impression** | Sees empty state | "How do I start?" | Tentative | No obvious next step | Prominent, clear CTA |
| **Initial Use** | Creates first note | "This is straightforward" | Confident | Form complexity concerns | Streamlined 3-field form |
| **Understanding** | Sees note appear | "I get how this works" | Satisfied | Due date calculation unclear | Clear status indicators |
| **Adoption** | Creates 2-3 more notes | "This fits my workflow" | Engaged | None significant | Reinforcement of simplicity |

**Key Insights:**
- Empty state must immediately communicate value
- First note creation is critical success moment
- Due date awareness needs immediate demonstration

### Journey Map 2: Daily User Experience
**Persona**: Quick Note Taker - Regular user

| Phase | User Actions | Thoughts | Emotions | Pain Points | Opportunities |
|-------|-------------|----------|-----------|-------------|---------------|
| **App Open** | Reviews note list | "What needs attention?" | Focused | Information overload | Clear visual hierarchy |
| **Priority Assessment** | Scans for overdue items | "Red items are urgent" | Alert | Too many overdue items | Proactive notifications |
| **Task Creation** | Adds new note | "Quick capture needed" | Efficient | Form friction | Optimized input flow |
| **Organization** | Sorts by due date | "Need to prioritize" | Methodical | Sort state unclear | Persistent sort preference |
| **Completion** | Deletes finished items | "Clean up completed tasks" | Satisfied | Accidental deletion risk | Confirmation patterns |

**Key Insights:**
- Visual priority system critical for quick scanning
- Sort persistence improves workflow efficiency
- Deletion needs safety mechanisms

### Journey Map 3: Time-Pressure Scenario
**Persona**: Quick Note Taker - Under time pressure

| Phase | User Actions | Thoughts | Emotions | Pain Points | Opportunities |
|-------|-------------|----------|-----------|-------------|---------------|
| **Urgent Entry** | Opens app quickly | "Need to capture this fast" | Rushed | App load time | Instant availability |
| **Speed Input** | Enters note details rapidly | "Must be quick" | Pressured | Field switching friction | Keyboard optimization |
| **Quick Save** | Saves and moves on | "Done, can focus elsewhere" | Relieved | Save uncertainty | Immediate feedback |
| **Later Review** | Returns to check status | "What did I capture?" | Methodical | Information retrieval | Effective search/sort |

**Key Insights:**
- Performance critical for time-pressure scenarios
- Input efficiency paramount
- Immediate feedback reduces anxiety

## Interaction Patterns

### Primary Interactions
1. **Note Creation**: Modal-based form interaction
2. **Note Editing**: In-place or modal editing
3. **List Navigation**: Scroll-based browsing
4. **Sorting**: Toggle-based organization
5. **Status Recognition**: Visual scanning pattern

### Secondary Interactions
1. **Note Deletion**: Confirmation-based removal
2. **Date Selection**: Calendar-based picking
3. **Field Validation**: Real-time feedback
4. **Sort Indication**: State visualization

### Touch/Click Targets
- **Primary Actions**: 44px minimum (mobile)
- **Secondary Actions**: 32px minimum
- **Text Inputs**: Full-width with adequate padding
- **Navigation Elements**: Consistent positioning

## User Flow Validation

### Success Metrics per Flow
1. **First Note Creation**: <30 seconds completion time
2. **Note Editing**: <20 seconds modification time
3. **List Navigation**: Instant status recognition
4. **Sorting**: <5 seconds to understand current state

### Error Recovery Flows
1. **Validation Errors**: Clear guidance to resolution
2. **Network Issues**: Graceful degradation
3. **Data Loss**: Auto-save protection
4. **Accidental Actions**: Undo mechanisms

## Design Token Integration Points

### Color Usage in Flows
- **Primary Green** (`primitives.colors.primary.color base`): Main CTAs and focus states
- **Error Red** (`primitives.colors.red.#500`): Overdue status and validation errors
- **Success Green** (`primitives.colors.green.color base`): Confirmation feedback
- **Text Colors** (`primitives.colors.black.*`): Content hierarchy

### Typography in Flows
- **Headings**: `font.type set.headline.h3.600` for note titles
- **Body Text**: `font.type set.paragraph 1.400` for sub-headings
- **Labels**: `font.type set.caption.400` for form labels
- **Status Text**: `font.type set.subtitle2.500` for due date status

### Spacing in Flows
- **Modal Padding**: `spacing.spacing-xl` (24px)
- **Card Spacing**: `spacing.spacing-md` (16px)
- **Form Fields**: `spacing.spacing-s` (12px) between elements
- **Button Padding**: `spacing.spacing-lg` horizontal, `spacing.spacing-xs` vertical

These user flows provide comprehensive guidance for creating an intuitive, efficient note-taking experience that leverages design tokens for consistent, accessible interactions.