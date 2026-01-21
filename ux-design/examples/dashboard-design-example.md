# Dashboard UX Design - Format Example

> Fictional example demonstrating dashboard layout patterns.

## Executive Summary

Home dashboard showing daily progress summary, quick actions, and recent activity. Mobile-first, single-column layout.

---

## User Flow

```
App Launch → Dashboard
              ├─ View Today's Summary (MacroSummary rings)
              ├─ Quick Log Food → Diary
              ├─ Quick Log Weight → Weight page
              └─ View Recent Activity → Full diary
```

---

## Wireframe

```
┌─────────────────────────────────────┐
│  ChonkCheck                         │  <- PageHeader
├─────────────────────────────────────┤
│                                     │
│  Hi, Scott!                         │  <- text-xl font-bold
│  Here's your day                    │  <- text-muted
│                                     │
│  ┌─────────────────────────────────┐│
│  │ Today's Summary                 ││
│  │ ┌─────┬─────┬─────┬─────┐      ││
│  │ │ Cal │ Pro │Carb │ Fat │      ││  <- MacroSummary
│  │ │ 68% │ 85% │ 42% │ 91% │      ││     (existing component)
│  │ └─────┴─────┴─────┴─────┘      ││
│  │ Remaining: 635 cal              ││
│  └─────────────────────────────────┘│
│                                     │
│  Quick Actions                      │
│  ┌───────────────┬─────────────────┐│
│  │ Log Food      │ Log Weight      ││  <- grid-cols-2
│  └───────────────┴─────────────────┘│
│                                     │
│  Recent Activity                    │
│  ┌─────────────────────────────────┐│
│  │ Chicken Breast · 165 cal        ││  <- FoodEntry (existing)
│  │ 150g · P: 31g · C: 0g · F: 4g   ││
│  └─────────────────────────────────┘│
│  [ View All → ]                     │
│                                     │
└─────────────────────────────────────┘
│  [Home] [Diary] [Weight] [Foods]    │  <- NavBar
└─────────────────────────────────────┘
```

---

## Components

| Component | Status | Notes |
|-----------|--------|-------|
| PageHeader | Existing | Logo + title |
| MacroSummary | Existing | Circular progress rings |
| FoodEntry | Existing | Recent activity items |
| QuickActionCard | New | Icon + label button card |
| NavBar | Existing | Bottom navigation |

---

## States

| State | Display |
|-------|---------|
| Loading | Centered spinner |
| Empty (no entries) | "No entries today. Start tracking!" + CTA |
| Over goal | Remaining shows negative in red |
| Error | Error card with retry button |

---

## Copy Inventory

| Element | Text [PLACEHOLDER] |
|---------|-------------------|
| Greeting | "Hi, {name}!" |
| Subheading | "Here's your day" |
| Summary heading | "Today's Summary" |
| Remaining | "Remaining: X cal" |
| Quick action 1 | "Log Food" |
| Quick action 2 | "Log Weight" |
| Activity heading | "Recent Activity" |
| Empty state | "No entries today. Start tracking!" |
| View all link | "View All" |

---

## Technical Requirements

**New Files:**
- `pages/Dashboard.tsx` - Main page
- `components/QuickActionCard.tsx` - Action button cards
- `hooks/useDashboardData.ts` - Data fetching

**API:**
- `GET /api/diary/summary?date={today}` - Today's totals
- `GET /api/diary/recent?limit=3` - Recent entries

---

## Accessibility

- Quick actions: 44x44px tap targets, semantic buttons
- Summary: Screen reader announces totals
- Recent activity: List with proper semantics
