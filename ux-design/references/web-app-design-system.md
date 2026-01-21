# ChonkCheck Web Application Design System

## Overview

The ChonkCheck web application (`apps/web/`) uses React + Vite + Tailwind CSS with a mobile-first approach. This design system provides functional, accessible UI components optimized for food tracking workflows. The focus is on clarity, efficiency, and touch-friendly interfaces.

---

## 1. Color Palette

### Custom Tailwind Colors (defined in `tailwind.config.js`)
- **Coral** (#ff6347) - Vibrant red-orange accent
- **Amber** (#f59e0b) - Warm orange accent
- **Vivid/Primary** (#22c55e) - Primary brand green (success, positive actions)
- **Teal** (#14b8a6) - Teal/cyan accent
- **Purple** (#a855f7) - Vibrant purple accent
- **Danger** (#ef4444) - Error/destructive actions

Each color has a full scale from 50 (lightest) to 950 (darkest).

### Semantic Colors (using CSS variables in `index.css`)

**Light Mode:**
- Surface: `#fafafc` (very light gray)
- Surface Card: `#ffffff` (pure white)
- Default Text: `#0f172a` (slate-900, deep blue-gray)
- Muted Text: `#64748b` (slate-500)
- Subtle Text: `#94a3b8` (slate-400)
- Border: `#e2e8f0` (slate-200)
- Border Muted: `#f1f5f9` (slate-100)

**Dark Mode:**
- Surface: `#0f172a` (slate-900)
- Surface Card: `#1e293b` (slate-800)
- Default Text: `#f8fafc` (slate-50)
- Muted Text: `#94a3b8` (slate-400)
- Borders adjust for dark theme contrast

---

## 2. Typography

### Font Family
**Font**: Inter (400, 500, 600, 700 weights)
- Fallback: `-apple-system`, `BlinkMacSystemFont`, `Segoe UI`, `Roboto`

### Heading Hierarchy
- **Page titles**: `text-xl font-bold text-default`
- **Section headers**: `text-lg font-bold text-default`
- **Card titles**: `font-semibold text-default`
- **Labels**: `text-sm font-medium text-muted`
- **Body text**: `text-default` (no explicit size = 16px)
- **Small text**: `text-sm text-muted`
- **Extra small**: `text-xs text-muted`

---

## 3. Layout Patterns

### Main Container (Layout.tsx)

```
min-h-screen bg-surface pb-20   // pb-20 for bottom nav space
├─ <main> max-w-lg mx-auto px-4 pt-4
│  └─ <Outlet> (page content)
└─ <NavBar> fixed bottom-0
```

### Mobile-First
- Max width 512px (max-w-lg) for content
- Padding: 4px horizontal, 4px top
- Bottom padding: 80px to avoid fixed navigation
- Safe area bottom padding via `.safe-bottom` utility

---

## 4. Core UI Components

### Modal.tsx - Generic modal wrapper
**Props**: `isOpen`, `onClose`, `title`, `children`, `footer`, `size` (normal/large/fullscreen)

- Uses portals for z-index management
- Sizes: normal (max-w-lg), large (max-w-2xl), fullscreen
- Header with close button, content area, optional footer
- Styling: `bg-surface-card rounded-3xl shadow-2xl border border-border-muted`

### ConfirmModal.tsx - Action confirmation
**Props**: `title`, `message`, `confirmText`, `cancelText`, `confirmStyle` (danger/primary)

- Optional typed confirmation (requires user to type confirmation text)
- Loading state with disabled buttons
- Danger button: `bg-gradient-to-r from-coral-500 to-coral-600`
- Primary button: `bg-gradient-to-r from-vivid-500 to-vivid-600`

### MessageModal.tsx - Notification modal
- Types: success (green), error (red), info (blue)
- Shows icon based on type
- Single OK button
- Styled with icon and message

### PageHeader.tsx - Page title bar
- Logo + title display
- `flex items-center gap-3 mb-4`

### NavBar.tsx - Bottom fixed navigation
5 nav items with unique colors:
- **Home**: Amber
- **Diary**: Vivid (green)
- **Weight**: Purple
- **Foods**: Coral
- **Settings**: Teal

NavLink styling with active/inactive states
Fixed bottom with `safe-bottom` padding for notched devices

### MacroDisplay.tsx - Inline macro line
- Compact format: `P: Xg · C: Yg · F: Zg`
- Semantic dots as separators
- `text-sm text-muted`
- Optional label and custom className

### MacroSummary.tsx - Circular progress rings
- 4 circular progress indicators (Cal, Pro, Carb, Fat)
- SVG-based with color-coded rings
- Shows percentage, value, and goal
- Red indicator when over goal
- Grid layout: `grid grid-cols-4 gap-4`

### ItemQuantityList.tsx - Food/recipe quantity editor
- List of added items with quantity controls
- Shows: name, type indicator (dot), macros, calories, delete button
- Quantity input with mode toggle (servings vs amount)
- Type indicators: orange for food, vivid green for recipes
- `p-3 bg-surface rounded-lg` cards

### FoodEntry.tsx - Single diary entry display
- Displays food or recipe with quantity
- Shows: name, brand (if food), serving info, calories, delete button
- Type indicator dot (orange/green)
- Hover effect on parent button
- Delete icon: `text-subtle hover:text-coral-500`
- Styling: `bg-surface-card rounded-2xl p-4 shadow-md hover:shadow-lg border border-border-muted`

### MealGroup.tsx - Collapsible meal section
- Header shows meal name, item count, type indicator, macros, total calories
- Expandable to show individual items
- Purple type indicator for meals
- Shadow and border styling matches FoodEntry

### FoodSearch.tsx - Search with results dropdown
- Search input with barcode and loading icons
- Results grouped by type (Meals, Recipes, Foods)
- Each section has colored header bar (purple, vivid, orange)
- Hover effect on results
- Max height with scroll: `max-h-64 overflow-y-auto`

### Combobox.tsx - Dropdown select
- Editable text input with dropdown options
- Click-outside detection
- Selected option highlighted: `bg-primary-50 dark:bg-primary-900/20`
- Chevron icon

---

## 5. Form Patterns

### Input Styling
```css
.w-full px-4 py-3 rounded-lg border border-border
focus:ring-2 focus:ring-primary-500 focus:border-transparent
```

### Number Inputs (ItemQuantityList.tsx)
- `w-20 px-2 py-1.5 text-center rounded-lg`
- Step value depends on mode (0.25 for servings)

### Buttons

**Primary:**
```css
bg-gradient-to-r from-vivid-500 to-vivid-600 text-white
hover:from-vivid-600 hover:to-vivid-700
```

**Danger:**
```css
bg-gradient-to-r from-coral-500 to-coral-600 text-white
hover:from-coral-600 hover:to-coral-700
```

**Secondary:**
```css
border-2 border-border rounded-xl text-default
hover:bg-border-muted
```

All buttons: `font-semibold transition-all disabled:opacity-50`

### Text Links/Buttons
- Small text buttons: `text-xs text-primary-600 hover:text-primary-700`
- Muted hover: `text-subtle hover:text-coral-500 transition-colors`

---

## 6. Spacing & Sizing

### Gaps/Spacing
- `gap-2` - Between inline items
- `gap-3` - Between sections
- `gap-4` - Between major blocks
- `mb-3`, `mb-4`, `mb-6` - Bottom margins
- `mt-1`, `mt-2` - Top margins

### Padding
- Cards: `p-3`, `p-4`, `p-5`, `p-6`
- Inputs: `px-3 py-2` or `px-4 py-3`
- Modals: `p-5` (header), `p-4` (content), `p-5` (footer)

### Border Radius
- `rounded-lg` - Inputs, small components
- `rounded-xl` - Buttons, dropdowns
- `rounded-2xl` - Cards, medium containers
- `rounded-3xl` - Modals, large components

### Shadows
- `shadow-md` - Cards, subtle elements
- `shadow-lg` - Hover states, emphasis
- `shadow-2xl` - Modals, overlays

---

## 7. Custom Hooks

### useModal.ts - Modal state management
```typescript
const modal = useModal<DataType>();
modal.open(data);      // Open with optional data
modal.close();         // Close modal
modal.isOpen          // Check state
modal.data            // Access associated data
```

### useInputMode.ts - Input mode toggling
```typescript
const { mode, setMode, toggle } = useInputMode('amount');
// mode: 'amount' | 'servings'
// toggle(): switches between modes
```

### useErrorModal.ts - Error display state
```typescript
const { error, hasError, showError, clearError } = useErrorModal();
showError('Error message');
clearError();
```

### useApi.ts - API initialization
- Used in Layout to initialize auth tokens

---

## 8. Responsive & Mobile

### Mobile-First Design
- Viewport: `width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no`
- No horizontal scroll
- Safe area padding for notched devices: `env(safe-area-inset-bottom)`

### Touch-Friendly
- Minimum tap target: 44x44px
- Remove tap highlight: `-webkit-tap-highlight-color: transparent`
- Hover states use `transition-` for smooth effects

### Dark Mode
- Uses CSS variable system for full theme support
- `.dark` class toggles dark colors
- Dark mode colors adjust scrollbars, inputs, dates

---

## 9. Icon Patterns

### All inline SVGs
Using Heroicons-style paths:
- Check circle: success states
- X circle: errors, close
- Info circle: information
- Trash: delete actions
- Barcode: barcode scan
- Chevron down: dropdowns
- Home, Diary, Weight, Foods, Settings: navigation

### Icon Sizing
- Nav icons: `w-6 h-6`
- Inline icons: `w-5 h-5`
- Small icons: `w-4 h-4`

### Icon Colors
- Default: `text-default` or `text-muted`
- Hover: `hover:text-coral-500`, `hover:text-primary-600`
- Error: `text-red-600`
- Success: `text-green-600`

---

## 10. Animation & Transitions

### Transitions
- `transition-colors` - Color changes
- `transition-opacity` - Opacity hover effects
- `transition-all` - Button interactions
- `transition-shadow` - Shadow on hover

### Loading Spinner (in index.css)
```css
@keyframes spin { to { transform: rotate(360deg); } }
.spinner { animation: spin 1s linear infinite; }
```

---

## 11. List Item Display Order

Per CLAUDE.md design spec:
```
[Name] [Labels/Badges] [Type Icon]     [Calories] [Delete]
[Brand]                                   cal
[Serving/Weight info]
[P: Xg · C: Yg · F: Zg]
```

**Implemented in:**
- **FoodEntry.tsx**: name, brand, serving info, calories, delete
- **ItemQuantityList.tsx**: name, type dot, quantity/unit, calories
- **MealGroup.tsx**: name, count, type dot, macros, calories

---

## 12. Common Patterns

### Card Container
```tsx
className="bg-surface-card rounded-2xl p-4 shadow-md hover:shadow-lg transition-shadow border border-border-muted"
```

### Type Indicator Dot
```tsx
<div className="w-3 h-3 rounded bg-vivid-500" />  // Recipe
<div className="w-3 h-3 rounded bg-orange-500" /> // Food
<div className="w-3 h-3 rounded bg-purple-500" /> // Meal
```

### Delete Button
```tsx
className="p-2 text-subtle hover:text-coral-500 transition-colors rounded-lg hover:bg-coral-50 dark:hover:bg-coral-950/20"
```

### Section Header
```tsx
className="px-4 py-2 text-xs font-medium text-white bg-COLOR-500 sticky top-0"
```

---

## 13. Accessibility Features

- `aria-label` on icon-only buttons
- Semantic HTML structure
- Focus rings: `focus:ring-2 focus:ring-primary-500`
- Keyboard navigation support
- Color contrast ratios meet WCAG standards

---

## 14. Files Location Reference

- **Components**: `/apps/web/src/components/`
- **Hooks**: `/apps/web/src/hooks/`
- **Tailwind Config**: `/apps/web/tailwind.config.js`
- **CSS Variables**: `/apps/web/src/index.css`
- **Pages**: `/apps/web/src/pages/`
- **Types**: `/apps/web/src/types/index.ts`

---

This design system provides a consistent, mobile-first, and accessible UI foundation. The use of semantic CSS variables, Tailwind utilities, and reusable components ensures consistency across new features while maintaining dark mode support throughout.
