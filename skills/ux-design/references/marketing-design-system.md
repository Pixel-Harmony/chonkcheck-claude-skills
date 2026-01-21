# ChonkCheck Marketing Website Design System

## Overview

The ChonkCheck marketing website (`apps/marketing/`) uses Next.js with static export. This design system provides a visually rich, brand-heavy experience optimized for SEO and conversions. The focus is on animations, gradients, and scroll-triggered reveals to create an engaging first impression.

---

## 1. Component Structure

### Page Layout (Server Components)
- `layout.tsx` - Root layout with Inter font, metadata, viewport setup
- `page.tsx` - Home page structure: Header → Hero → Features → ComingSoon → Community → Pricing → FAQ → CTA → Footer

### Major Components (Mix of Server & Client)
- **Header.tsx** - Fixed navigation with logo and Sign In button (server component)
- **Hero.tsx** - Hero section with animated floating feature icons (client, uses framer-motion)
- **Features.tsx** - Six feature cards with alternating layout and gradient backgrounds
- **ComingSoon.tsx** - Four planned features in 2-column grid
- **Community.tsx** - Three community values with icons
- **Pricing.tsx** - Three pricing tiers (Free, Ad-Free, Premium) with beta status
- **FAQ.tsx** - Accordion-style FAQ with state management (client component)
- **CTA.tsx** - Green gradient call-to-action banner
- **Footer.tsx** - Minimal footer with logo, contact, copyright (server component)

### Utility Components (`ui/` folder)
- **GradientButton.tsx** - Primary/secondary buttons with animated gradient backgrounds
- **GradientIcon.tsx** - Icon containers with color schemes and optional scaling
- **GradientMesh.tsx** - Animated orb backgrounds for sections (hero, cta, features, subtle)
- **ScrollReveal.tsx** - Scroll-triggered reveal animations with 4 directions
- **FeatureCard.tsx** - Feature section template with visual + text layout
- **PhoneMockup.tsx**, **BarcodeScanner.tsx**, **NutritionLabel.tsx**, **WeightGraph.tsx**, **RecipeCardStack.tsx**, **LocationScenes.tsx**, **CookingPot.tsx** - Feature-specific visualizations

---

## 2. Tailwind Color Palette

### Brand Colors (Extended in `tailwind.config.mjs`)

| Color | 500 (Primary) | Usage |
|-------|---------------|-------|
| **Vivid** (Green) | `#22c55e` | Primary brand, CTAs, positive states, badges |
| **Teal** | `#14b8a6` | Gradient accents, secondary feature highlights |
| **Coral** | `#ff6347` | Warm accent, feature highlights |
| **Amber** | `#f59e0b` | Warm accent, feature highlights |
| **Purple** | `#a855f7` | Feature accents, "Coming Soon" badge |

Each color has a full scale from 50 (lightest) to 950 (darkest).

### Standard Palette
- Gray: 50-950 (neutral)
- White: backgrounds
- Red/Danger: not heavily used

### Gradient Combinations (Color Schemes)
```
coral-amber   → from-coral-400 via-amber-400 to-coral-500
vivid-teal    → from-vivid-400 via-teal-400 to-vivid-500
purple-coral  → from-purple-400 via-coral-400 to-purple-500
teal-vivid    → from-teal-400 via-vivid-400 to-teal-500
amber-vivid   → from-amber-400 via-vivid-400 to-amber-500
purple-teal   → from-purple-400 via-teal-400 to-purple-500
```

---

## 3. Typography

### Font Family
- **Font**: Inter (from Google Fonts, variable with `--font-inter` CSS variable)
- **Fallbacks**: -apple-system, BlinkMacSystemFont, Segoe UI, Roboto, sans-serif
- **Display**: swap (for web font loading)

### Type Scale (Tailwind defaults, custom variants)

| Element | Styles | Example |
|---------|--------|---------|
| **H1 (Headlines)** | `text-3xl sm:text-4xl md:text-5xl lg:text-6xl font-extrabold tracking-tight` | Hero "Spend less time logging" |
| **H2 (Section Titles)** | `text-3xl sm:text-4xl lg:text-5xl font-bold tracking-tight` | "Tracking that fits around your meals" |
| **H3 (Feature Headlines)** | `text-2xl sm:text-3xl font-bold` | "Cook Twice? Log Once." |
| **Body Large** | `text-base sm:text-lg lg:text-xl text-gray-600` | Subheadlines/descriptions |
| **Body Regular** | `text-base text-gray-600` | Feature descriptions |
| **Body Small** | `text-sm text-gray-600` | Fine print, metadata |

### Text Colors
- **Primary text**: `text-gray-900`
- **Secondary text**: `text-gray-600`
- **Muted text**: `text-gray-500`
- **Accent text**: Uses gradient `bg-gradient-to-r from-vivid-500 to-teal-500 bg-clip-text text-transparent`

---

## 4. Animation Patterns

### Scroll-Triggered Reveal (`ScrollReveal.tsx`)

```typescript
- Initial: opacity 0, offset by 40px (up/down/left/right)
- Duration: 0.6s
- Easing: [0.25, 0.1, 0.25, 1] (cubic-bezier for smooth deceleration)
- Viewport trigger: once=true, margin=-50px
- Direction options: up (default), down, left, right, none
- Delay: 0-0.3s for staggered effects
- Respects prefers-reduced-motion
```

### Custom CSS Animations (`globals.css`)

```css
.animate-gradient      → gradient-shift 8s ease infinite
.animate-gradient-x    → gradient-x 4s ease infinite
.animate-mesh-1/2/3/4  → mesh-move-{n} 20-28s ease-in-out infinite
.animate-float         → float 6s ease-in-out infinite
.animate-float-delayed → float 6s with 2s delay
.animate-shimmer       → shimmer 2s linear infinite
```

### Framer-motion (Hero section)
- Floating feature icons: 6-9s animations with rotation, staggered delays
- Container variants: staggerChildren with 0.12s delay
- Item variants: fade-in-up with custom easing
- Reduced motion: removes animations and y-offset, keeps scale

### Interactive States
- **Buttons**: `hover:scale-105 motion-reduce:hover:scale-100` (smooth scale on hover)
- **Cards**: `hover:-translate-y-1 hover:shadow-lg` (lift effect)
- **Icons**: `transition-transform duration-500 ease-out`

---

## 5. Layout Patterns

### Spacing & Container

```css
.section-container → mx-auto max-w-7xl px-4 sm:px-6 lg:px-8
```

### Responsive Breakpoints (Tailwind)
- `sm`: 640px
- `md`: 768px
- `lg`: 1024px
- `xl`: 1280px (not explicitly used)

### Grid Layouts
- **Features**: `grid-cols-1 lg:grid-cols-2` (text + visual side-by-side on desktop)
- **Coming Soon**: `sm:grid-cols-2` (2 columns on tablet+)
- **Community/Pricing**: `lg:grid-cols-3` (3 columns on desktop)
- **Features section**: alternating `lg:flex-row` with `lg:flex-row-reverse`

### Padding & Gaps
- **Section padding**: `py-20 sm:py-32` (80px mobile, 128px desktop)
- **Component padding**: `p-6 sm:p-8` to `p-16`
- **Gaps**: `gap-8 lg:gap-12` or `gap-16` (large feature sections)
- **Vertical spacing**: `mt-6`, `mt-8`, `mt-10`, `mt-12`, `mt-16` (incremental)

---

## 6. Mobile-First Responsive Design

### Strategy
- Default styles are mobile
- `sm:`, `lg:` prefixes for breakpoint-specific overrides
- Hide/show classes: `hidden sm:block` (hide on mobile), `hidden lg:block` (hide on desktop)

### Key Responsive Patterns

```tsx
// Text sizing
text-3xl sm:text-4xl md:text-5xl lg:text-6xl

// Grid columns
grid-cols-1 sm:grid-cols-2 lg:grid-cols-3

// Layout direction
flex-col lg:flex-row

// Visibility
hidden sm:block (hide mobile, show tablet+)
hidden lg:block (hide mobile/tablet, show desktop)
sm:hidden (hide tablet+, show mobile)

// Padding/Spacing
px-4 sm:px-6 lg:px-8
py-16 sm:py-20 lg:py-32
```

### Mobile-Specific Considerations
- Logo shown on mobile hero, hidden on desktop (space-saving)
- Phone mockups: different sizes for mobile vs desktop
- Feature visuals: stack vertically on mobile, side-by-side on desktop
- Section backgrounds: simpler gradient meshes on mobile (mobileHidden: true)

---

## 7. Brand Voice & Tone

### Personality Traits
- Casual, conversational, irreverent (contrasts with typical fitness apps)
- Relatable, anti-hype (admits problems with other apps)
- Food-focused, humorous (puns: "Cook Twice? Log Once", "See what's cooking")
- Honest, judgment-free ("No judgment, just honest numbers")
- British English (£ pricing, "scran", "sausage roll", "chonky" theme)
- First-person, human-centric ("we" language, acknowledge users as people)

### Sample Headlines
- "Spend less time logging, more time eating"
- "Scan your scran" (UK slang for food)
- "Watch the trend, not the wobble"
- "Track from the kitchen. Or the cafe. Or the sofa"
- "Made by people who actually use it"
- "No nasty surprises on the bill"

### Key Messaging Patterns
1. Problem statement (what other apps do wrong)
2. Simple solution (what ChonkCheck does)
3. Benefit (what you get)

**Example**: "You've tried the apps with endless menus... ChonkCheck keeps it simple—so you can get back to the good stuff."

---

## 8. Component Design Patterns

### Buttons

```tsx
// Primary (gradient animated)
from-vivid-500 via-teal-500 to-vivid-500
bg-gradient-x animate-gradient-x
shadow-lg shadow-vivid-500/25
hover:shadow-xl hover:scale-105

// Secondary (gradient outline)
Similar structure with after::pseudo-element for border effect

// Sizes: sm (px-4 py-2), md (px-6 py-3), lg (px-8 py-4)
```

### Icon Containers

```tsx
rounded-2xl bg-gradient-to-br {colorScheme}
sizes: sm (h-10 w-10), md (h-14 w-14), lg (h-20 w-20)
Animate gradient, optional scale-110 when active
```

### Cards

```tsx
rounded-2xl or rounded-3xl
bg-white
shadow-sm (default) → shadow-lg (hover)
border-gray-100 (optional)
transition-all duration-300 for smooth interactions
```

### Badges/Pills

```tsx
inline-flex items-center gap-2
rounded-full
bg-{color}-100 px-4 py-1.5
text-sm font-medium
text-{color}-700
```

---

## 9. Accessibility Features

### Implemented
- Skip to content link (sr-only, focusable)
- `aria-label`, `aria-hidden` on decorative elements
- Semantic HTML (button, nav, section, h1-h3)
- `aria-expanded` on accordion buttons
- Proper color contrast (gray-900 on white, white on colored backgrounds)
- Focus rings: `focus:ring-2 focus:ring-vivid-500 focus:ring-offset-2`

### Reduced Motion Support
- Framer-motion: `useReducedMotion()` hook
- CSS: `motion-reduce:animate-none`, `motion-reduce:scale-100`
- All animations have non-animated fallbacks

---

## 10. Visual Hierarchy

### Section Backgrounds
- **Hero**: Gradient-to-br from white → vivid-100/40 → teal-100/30 + animated mesh orbs
- **Features**: White with gradient meshes, alternating colored backgrounds on every other feature
- **Coming Soon**: Gradient-to-b from gray-50 → white
- **Community**: bg-gray-50 (light gray)
- **Pricing**: Gradient-to-b from gray-50 → white
- **FAQ**: White
- **CTA**: Gradient-to-br from vivid-500 → teal-500 (solid color block)
- **Footer**: White with border-t

### Emphasis Techniques
1. **Gradient text** (important phrases)
2. **Icon placement** (reinforces message)
3. **Background color changes** (section distinction)
4. **Animation** (attracts attention)
5. **Size variation** (headline hierarchy)

---

## 11. Key CSS Utilities & Custom Classes

### Custom Component Classes
```css
.btn-primary, .btn-secondary
.section-container
```

### Custom Animations
```css
.animate-gradient, .animate-gradient-x
.animate-mesh-1/2/3/4
.animate-float, .animate-float-delayed
.animate-shimmer
.animate-draw-line
```

### Motion Support
```css
motion-reduce:animate-none
motion-reduce:scale-100
motion-reduce:hover:scale-100
```

---

## 12. Design System Principles

### Established Patterns
1. **Consistency**: Color schemes paired across components
2. **Hierarchy**: Clear visual distinction between sections
3. **Whitespace**: Generous padding between sections (80-128px)
4. **Movement**: Scroll reveals for engagement without distraction
5. **Accessibility**: Motion respect, semantic HTML, ARIA labels
6. **Simplicity**: Minimal, focused layouts (no clutter)
7. **Branding**: Vivid green primary color, gradient accents throughout
8. **Typography**: Large, bold headlines with readable body text
9. **Interactivity**: Hover states, smooth transitions, feedback on action

---

## 13. Key Files Reference

| File | Purpose |
|------|---------|
| `/apps/marketing/tailwind.config.mjs` | Color palette, font configuration |
| `/apps/marketing/src/app/globals.css` | Custom animations, keyframes, utilities |
| `/apps/marketing/src/components/Hero.tsx` | Framer-motion animation patterns |
| `/apps/marketing/src/components/ScrollReveal.tsx` | Scroll trigger implementation |
| `/apps/marketing/src/components/ui/GradientButton.tsx` | Button component pattern |
| `/apps/marketing/src/components/ui/GradientIcon.tsx` | Icon component pattern |
| `/apps/marketing/src/components/ui/GradientMesh.tsx` | Background animation pattern |
| `/apps/marketing/src/components/Features.tsx` | Layout pattern for feature sections |
| `/apps/marketing/src/components/Pricing.tsx` | Card-based layout pattern |
| `/apps/marketing/src/app/layout.tsx` | Metadata, font setup, viewport config |

---

## 14. SEO Best Practices

### Avoid `'use client'` Where Possible

The `'use client'` directive forces a component to render on the client, which **hurts SEO** because:
- Content isn't included in the initial HTML
- Search engine crawlers may not execute JavaScript
- Increases client-side JavaScript bundle size
- Slower initial page load (hydration overhead)

### Rules
1. **Only use `'use client'` when absolutely necessary** - Components that use React hooks (`useState`, `useEffect`, `useRef`), browser APIs, or event handlers that require client-side interactivity
2. **Prefer CSS over JavaScript for animations** - Use Tailwind's `motion-reduce:` variant instead of `useReducedMotion()` hook
3. **Server components can import client components** - A parent doesn't need `'use client'` just because it renders a client component child
4. **Composing components doesn't require `'use client'`** - If a component only renders other components and static JSX, it should be a server component

### Valid Reasons for `'use client'`
- Using hooks like `useState`, `useEffect`, `useRef`, `useContext`
- Using browser APIs like `window`, `document`, `IntersectionObserver`
- Using framer-motion's `motion` components with `animate`, `whileInView` props
- Event handlers that modify state (onClick that updates state)

### NOT Valid Reasons
- Importing a client component (parent can stay server)
- Using Tailwind classes (CSS is server-compatible)
- Conditional rendering based on props (server can do this)
- Using `useReducedMotion` just to toggle CSS classes (use `motion-reduce:` instead)

---

This is the complete design DNA of the ChonkCheck marketing website. Use these patterns to maintain consistency across new pages or components.
