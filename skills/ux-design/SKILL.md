---
name: ux-design
description: This skill should be used when the user asks to "design a UX", "design a UI", "design a feature", "create a user flow", "improve user experience", "design an onboarding", "design a page", "design a layout", or needs guidance on information architecture, visual design, interaction patterns, wireframing, or accessibility for ChonkCheck features. Provides comprehensive UX design thinking that maintains consistency with existing marketing and web app design systems.
version: 1.0.0
---

# ChonkCheck UX Design Skill

## Overview

Provide expert UX design guidance for ChonkCheck features across web, marketing, and mobile platforms. Apply design thinking methodologies, create comprehensive wireframes, and maintain consistency with established brand and design patterns.

## When This Skill Applies

Use this skill when:
- User asks to design a new feature, page, or component
- User requests UX improvements to existing functionality
- User needs design patterns, layout guidance, or interaction flows
- Discussion involves user experience, information architecture, or accessibility
- Feature requests require visual design specifications
- User asks for wireframes, mockups, or design documentation

## Core Design Philosophy

**ChonkCheck Design Principles:**
1. **Mobile-First**: Design for 375px minimum width, progressive enhancement
2. **Accessible by Default**: WCAG 2.1 AA compliance, touch-friendly (44px+ targets)
3. **Consistent Brand**: Vivid green primary, gradient accents, friendly tone
4. **User-Centered**: Solve real problems, reduce friction, respect user time
5. **Simple & Clear**: Avoid complexity, use familiar patterns, clear hierarchy
6. **Food-Focused Fun**: Conversational tone, food puns, judgment-free

## Design Process Workflow

### Phase 1: Discovery & Context
1. **Understand the Feature Request**
   - What problem does this solve?
   - Who are the users and what are their goals?
   - What are the constraints (technical, platform, scope)?
   - How does this fit into the overall product?

2. **Analyze Existing Patterns**
   - Reference marketing design system for brand-heavy pages
   - Reference web app design system for functional interfaces
   - Identify reusable components and patterns
   - Note any new patterns needed

3. **Ask Clarifying Questions**
   - Use AskUserQuestion tool to resolve ambiguities
   - Clarify user preferences (mandatory vs optional flows, skip options, etc.)
   - Confirm approach before detailed design work

### Phase 2: Design & Wireframing
1. **Create Information Architecture**
   - Define screen flow and navigation
   - Group related information logically
   - Establish visual hierarchy (what's most important?)
   - Plan progressive disclosure for complex features

2. **Design Wireframes**
   - Create ASCII wireframes for each screen/step
   - Show layout, components, spacing, and alignment
   - Include responsive breakpoints (mobile → tablet → desktop)
   - Annotate interaction patterns and states

3. **Specify Components**
   - List UI components needed (existing vs new)
   - Define props, states, and behaviors
   - Reference design system patterns
   - Note accessibility requirements

4. **Write Placeholder Copy**
   - Headlines, button labels, help text
   - Error messages and validation feedback
   - Success states and confirmations
   - Note: Mark as placeholder for copywriter refinement

### Phase 3: Documentation
1. **Create Comprehensive UX Spec**
   - Visual design with annotated wireframes
   - Interaction patterns and user flows
   - Component specifications
   - Validation rules and error handling
   - Accessibility requirements
   - Responsive design breakpoints
   - Copy inventory for copywriter
   - Technical requirements for developers

2. **Provide Implementation Guidance**
   - File structure and component organization
   - Reusable hooks and utilities
   - API integration points
   - Testing and validation approach

## Design Systems Reference

ChonkCheck has two primary design systems:

### Marketing Website Design System
**File**: `references/marketing-design-system.md`

Use for:
- Landing pages, promotional content
- Brand-heavy, animated, visually rich experiences
- Server-side rendered pages (Next.js)
- SEO-critical content

Key patterns: Gradient meshes, scroll reveals, hero sections, feature cards, gradient buttons

### Web App Design System
**File**: `references/web-app-design-system.md`

Use for:
- Functional application interfaces
- Forms, modals, lists, navigation
- Data entry and display
- Client-side React components

Key patterns: Modal system, form inputs, cards, navigation bars, macro displays, food entries

### Mobile App Design (Future)
Apply web app patterns with mobile-specific considerations:
- Native navigation patterns (tabs, stack navigation)
- Touch gestures (swipe, long-press)
- Native components (pickers, alerts)
- Platform-specific UI (iOS vs Android)

## Accessibility Guidelines

**File**: `references/accessibility-guidelines.md`

Every design must include:
- ✅ Minimum 44x44px touch targets
- ✅ Color contrast ratios (4.5:1 text, 3:1 UI)
- ✅ Keyboard navigation support
- ✅ Screen reader labels (aria-label, semantic HTML)
- ✅ Focus indicators (visible focus states)
- ✅ Error identification (inline, descriptive)
- ✅ Motion respect (prefers-reduced-motion)

## Output Format

Deliver a comprehensive UX design plan as a Markdown document containing:

### 1. Executive Summary
- Feature overview
- Design constraints
- Key decisions made

### 2. User Flow Diagrams
- ASCII flow charts showing user journey
- Decision points and edge cases
- Success and error paths

### 3. Wireframes (ASCII)
- Each screen/step visualized
- Component layout and spacing
- Responsive breakpoints noted
- Annotations for interactions

### 4. Component Specifications
- Existing components to reuse
- New components needed
- Props, states, validation rules
- Accessibility requirements

### 5. Design Patterns Applied
- Which design system patterns used
- New patterns introduced
- Rationale for choices

### 6. Copy Inventory
- All headlines, labels, messages
- Organized by screen/component
- Marked as placeholder for copywriter

### 7. Technical Requirements
- Files to create/modify
- API integrations
- Validation logic
- Testing approach

### 8. Responsive Design
- Mobile (375px+)
- Tablet (768px+)
- Desktop (1024px+)

## Example Projects

### Onboarding Example
**File**: `examples/onboarding-ux-design.md`

Multi-step flow example demonstrating: wireframes, component tables, validation rules, copy inventory, technical requirements. Shows the expected structure and format.

### Dashboard Example
**File**: `examples/dashboard-design-example.md`

Single-page example showing: layout wireframe, component reuse, states table, copy inventory. Demonstrates concise format for simpler features.

## Key Design Tokens

### Colors
- **Primary**: Vivid green (#22c55e) - CTAs, success, positive
- **Accents**: Coral, Amber, Teal, Purple - feature highlights
- **Neutrals**: Gray scale for text, borders, surfaces
- **Semantic**: Danger (red), Success (green), Info (blue)

### Typography
- **Font**: Inter (marketing + web app)
- **Scale**: text-xs → text-sm → text-base → text-lg → text-xl → text-2xl → text-3xl → text-4xl → text-5xl → text-6xl
- **Weights**: 400 (regular), 500 (medium), 600 (semibold), 700 (bold), 800 (extrabold)

### Spacing
- **Scale**: 4px base unit (0.25rem)
- **Common gaps**: gap-2, gap-3, gap-4, gap-6, gap-8, gap-12
- **Section padding**: py-20 (mobile), py-32 (desktop)
- **Component padding**: p-3, p-4, p-5, p-6

### Border Radius
- **Inputs**: rounded-lg (0.5rem)
- **Buttons**: rounded-xl (0.75rem)
- **Cards**: rounded-2xl (1rem)
- **Modals**: rounded-3xl (1.5rem)

### Shadows
- **Subtle**: shadow-sm
- **Default**: shadow-md
- **Elevated**: shadow-lg
- **Modals**: shadow-2xl

## Brand Voice & Tone

**Personality**: Friendly, conversational, irreverent, honest, food-focused

**Writing Style**:
- Casual but not unprofessional
- British English (£, kg, "scran")
- Food puns encouraged
- Judgment-free, supportive
- Honest about limitations

**Examples**:
- "Scan your scran" (not "Scan your food")
- "Watch the trend, not the wobble" (not "Track your weight")
- "No judgment, just honest numbers" (not "Accurate tracking")

## Common Patterns to Reuse

### Modal Flows
Use existing Modal, ConfirmModal, MessageModal components with:
- Title bar with close button
- Content area (scrollable if needed)
- Footer with action buttons
- Proper focus management

### Form Patterns
- Input labels above fields
- Inline validation on blur
- Error messages below fields (text-danger-500)
- Disabled submit until valid
- Loading states on submission

### List Items
Follow design spec from CLAUDE.md:
```
[Name] [Labels/Badges] [Type Icon]     [Calories] [Delete]
[Brand]                                   cal
[Serving/Weight info]
[P: Xg · C: Yg · F: Zg]
```

### Navigation Patterns
- **Marketing**: Fixed header with logo + CTA
- **Web App**: Bottom tab bar (5 items, colored icons)
- **Mobile (future)**: Stack navigation + bottom tabs

## Additional Resources

### Reference Files
- **`references/marketing-design-system.md`** - Marketing website patterns (gradients, animations, scroll reveals)
- **`references/web-app-design-system.md`** - Web app patterns (forms, modals, lists, navigation)
- **`references/accessibility-guidelines.md`** - WCAG 2.1 AA checklist

### Examples
- **`examples/onboarding-ux-design.md`** - Multi-step flow format
- **`examples/dashboard-design-example.md`** - Single-page format

### Project Context
- **`/docs/onboarding-ux-design.md`** - Recently completed onboarding design
- **`/CLAUDE.md`** - Project guidelines, code standards, design language
- **`/apps/marketing/tailwind.config.mjs`** - Marketing color palette
- **`/apps/web/tailwind.config.js`** - Web app color palette
- **`/apps/web/src/components/`** - Existing UI components

## Success Criteria

A complete UX design deliverable should:
- ✅ Solve the stated user problem clearly
- ✅ Maintain consistency with existing design systems
- ✅ Include comprehensive wireframes (ASCII)
- ✅ Specify all components, props, states
- ✅ Meet WCAG 2.1 AA accessibility standards
- ✅ Work on mobile-first (375px+)
- ✅ Include copy placeholders for all text
- ✅ Provide clear technical implementation guidance
- ✅ Reference existing patterns where possible
- ✅ Be detailed enough for a developer to implement
- ✅ Be comprehensive enough for a copywriter to refine

## Notes for Developers

When implementing UX designs from this skill:
1. Follow file organization in CLAUDE.md
2. Reuse existing components before creating new ones
3. Extract common patterns into hooks/utilities
4. Test on mobile devices (primary platform)
5. Validate accessibility with screen readers
6. Run linter (must pass with no warnings)
7. Match Tailwind patterns from design systems

## Notes for Copywriters

UX designs include placeholder copy marked as "[PLACEHOLDER]". When refining:
1. Review tone and voice guidelines
2. Simplify explanations where possible
3. Add personality without being gimmicky
4. Improve CTAs for clarity and encouragement
5. Ensure British English spelling/terminology
6. Maintain judgment-free, supportive language
