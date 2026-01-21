# Onboarding UX Design - Format Example

> This is a condensed example showing the expected format and structure for UX designs. Your actual designs should follow this structure with appropriate detail for the feature complexity.

## Executive Summary

3-step mandatory onboarding flow collecting profile data (units, body measurements, macro goals) before users access the main app. Mobile-first, no skip option.

---

## User Flow

```
Auth0 Login → Activate Account → /onboarding → Dashboard
                                      │
                         Step 1 → Step 2 → Step 3
                         (Units)  (Body)   (Goals)
```

---

## Wireframes

### Step 1: Welcome & Units

```
┌─────────────────────────────────────┐
│  ○ ○ ○  (1 of 3)                    │
├─────────────────────────────────────┤
│                                     │
│  Welcome to ChonkCheck!             │  <- text-xl font-bold
│  Let's personalize your experience  │  <- text-muted
│                                     │
│  ┌───────────────────────────────┐  │
│  │ Weight Unit                   │  │
│  │ [ Kilograms (kg)      ▼ ]    │  │
│  │                               │  │
│  │ Height Unit                   │  │
│  │ [ Centimeters (cm)    ▼ ]    │  │
│  └───────────────────────────────┘  │
│                                     │
│  [ Continue → ]                     │  <- Primary button
│                                     │
└─────────────────────────────────────┘
```

### Step 2: Body Profile

```
┌─────────────────────────────────────┐
│  ← Back       ● ○ ○  (2 of 3)       │
├─────────────────────────────────────┤
│                                     │
│  About You                          │
│  For personalized calorie goals     │
│                                     │
│  Height: [ 175 ] cm                 │
│  Weight: [ 75 ] kg                  │
│  Age: [ 30 ] years                  │
│  Sex: ○ Male  ○ Female              │
│  Activity: [ Moderately Active ▼ ]  │
│                                     │
│  [ Continue → ]                     │
└─────────────────────────────────────┘
```

### Step 3: Goals

```
┌─────────────────────────────────────┐
│  ← Back       ● ● ○  (3 of 3)       │
├─────────────────────────────────────┤
│                                     │
│  Your Daily Goals                   │
│                                     │
│  ┌─────────────────────────────┐    │
│  │ Your TDEE: 2,450 cal/day    │    │  <- Calculated display
│  └─────────────────────────────┘    │
│                                     │
│  [ Lose Weight ] 1,950 cal          │  <- Goal buttons
│  [ Maintain   ] 2,450 cal  ✓        │
│  [ Gain Weight ] 2,950 cal          │
│                                     │
│  Daily Targets:                     │
│  Cal: 2,450 | P: 150g | C: 245g | F: 82g │
│                                     │
│  ⚙️ Customize Macros ▼              │  <- Expandable
│                                     │
│  [ Start Tracking → ]               │
└─────────────────────────────────────┘
```

---

## Components

| Component | Status | Key Props/Notes |
|-----------|--------|-----------------|
| OnboardingLayout | New | progress (1-3), onBack, children |
| ProgressIndicator | New | current, total (dots display) |
| Step1Welcome | New | Form: weightUnit, heightUnit |
| Step2BodyProfile | New | Form: height, weight, age, sex, activityLevel |
| Step3Goals | New | Displays TDEE, goal buttons, macro inputs |
| Tooltip | New | Mobile-friendly info modal (tap to show) |

**Reused**: Form inputs, buttons, dropdowns from existing design system

---

## Validation Rules

| Field | Rules |
|-------|-------|
| Height | Required, 1-300 (cm) or valid ft/in |
| Weight | Required, 1-1000 |
| Age | Required, 13-120 |
| Sex | Required (male/female) |
| Activity | Required (5 levels) |
| Macros | All > 0 if customizing |

---

## Copy Inventory

| Screen | Element | Text [PLACEHOLDER] |
|--------|---------|-------------------|
| Step 1 | Heading | "Welcome to ChonkCheck!" |
| Step 1 | Subheading | "Let's personalize your experience" |
| Step 1 | Button | "Continue" |
| Step 2 | Heading | "About You" |
| Step 2 | Subheading | "For personalized calorie goals" |
| Step 3 | Heading | "Your Daily Goals" |
| Step 3 | Button | "Start Tracking" |
| Success | Toast | "Welcome! Your profile is set up." |

**Tooltips**: Weight unit, Height, Sex (BMR formula), Activity level (descriptions)

---

## Technical Requirements

**New Files:**
- `pages/Onboarding.tsx` - 3-step state machine
- `components/onboarding/` - Step components, ProgressIndicator
- `components/Tooltip.tsx` - Mobile info modal

**Modified:**
- `ProtectedRoute.tsx` - Redirect incomplete profiles to /onboarding
- `App.tsx` - Add /onboarding route

**API:** Uses existing `POST /api/profile` (batch update on final step)

**State:** Local form state for 3 steps, single API call on completion

---

## Accessibility

- Progress indicator: aria-label="Step X of 3"
- Tooltips: Tap to show modal (no hover dependency)
- Form inputs: Visible labels, aria-describedby for errors
- Focus: Auto-focus first field on each step
- Validation errors: aria-live region announcements

---

## Responsive Notes

- Mobile (375px+): Full-width cards, 16px padding
- Max width: 480px centered on larger screens
- All inputs stack vertically
- Touch targets: 44px minimum height
