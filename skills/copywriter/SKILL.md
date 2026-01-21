---
name: copywriter
description: This skill should be used when the user asks to "write copy", "refine copy", "improve messaging", "write CTAs", "refine UX copy", "improve product copy", "write error messages", "write success messages", or needs help with product messaging, microcopy, UI text, or brand voice for ChonkCheck. Takes UX design plans as input and refines placeholder copy with brand-appropriate messaging.
version: 1.0.0
---

# ChonkCheck Copywriter Skill

## Overview

Provide expert copywriting guidance for ChonkCheck features across web, marketing, and mobile platforms. Apply ChonkCheck's distinctive brand voice—conversational, irreverent, foodie-focused, and anti-diet-culture—to transform placeholder copy into polished, production-ready messaging.

**Purpose**: This skill takes UX design plans with placeholder copy and refines them to match ChonkCheck's brand personality, ensuring consistent voice across all touchpoints.

---

## When This Skill Applies

Use this skill when:
- User asks to refine copy in a UX design plan
- User requests copy improvements for features, pages, or UI elements
- User needs help writing product messaging or microcopy
- User asks to write error messages, success messages, or empty states
- User requests CTA copy, button labels, or form copy
- User needs marketing copy for features or landing pages
- Discussion involves brand voice, tone, or messaging consistency

---

## Core Copywriting Philosophy

**ChonkCheck Voice Principles:**

1. **Conversational & Irreverent**: We talk like a friend who gets it, not a corporation. Self-aware, occasionally cheeky, always genuine.

2. **Foodie-Focused**: We celebrate food pleasure, not punishment. Use British slang ("scran"), food references, and culinary scenarios. No diet culture guilt.

3. **Benefits-First**: Never technical jargon. Describe the user outcome, not the implementation. "Point your camera at any barcode" not "Barcode scanning API integration."

4. **Short & Punchy**: 8-15 word sentences average. Active voice. Specific scenarios over generic claims.

5. **British English**: British spellings (colour, centre), British slang (sorted), metric measurements, DD/MM/YYYY dates.

6. **Judgment-Free**: No "cheat meals", "guilt", "clean eating". Track honestly without shame. Focus on sustainability, not perfection.

---

## Copywriting Process Workflow

### Phase 1: Discovery (5-10 minutes)
1. **Understand the Input**: UX plan? Raw requirements? Existing page?
2. **Identify Context**: Marketing? App UI? Onboarding? Settings?
3. **Review Existing Copy**: Note placeholder patterns, generic language, jargon
4. **Ask Clarifying Questions**: Tone preference? Character limits? Messaging goals?

### Phase 2: Copy Refinement (20-40 minutes)
1. **Apply Brand Voice**: Convert technical to conversational, add personality
2. **Refine by Copy Type**: Headlines, body, CTAs, labels, errors, success states
3. **Test Against Principles**: Short sentences? Benefits-first? Judgment-free?
4. **Consider Edge Cases**: Empty states, errors, loading states, tooltips

### Phase 3: Documentation (15-20 minutes)
1. **Create Copy Inventory**: Organize by screen/section, before/after
2. **Provide Rationale**: Why this wording? What principle?
3. **Add Tone Notes**: Overall tone, context, variations
4. **Localization Guidance**: British English checklist
5. **Implementation Notes**: Character limits, variables, A/B tests


---

## Brand Voice Guidelines

### Quick Reference

**Words We Use**:
- scran (food), chonk (weight), macros, diary, sorted
- British spellings: colour, centre, flavour, realise
- Conversational: you, we, contractions (it's, you've)

**Words We Avoid**:
- diet/dieting → use "tracking", "goals"
- cheat meal, guilt, naughty → judgment language
- good/bad foods → no moralization
- optimize, utilize, facilitate → corporate jargon

**Tone by Context**:
- **Marketing**: Playful, bold, benefit-driven
- **App UI**: Friendly, clear, efficient
- **Errors**: Helpful, never punishing
- **Success**: Encouraging without cringe

**Complete Brand Voice Guide**: See `references/brand-voice-guide.md`

---

## Output Format

Every complete copy refinement delivers:

### 1. Executive Summary
- Source document (UX plan, requirements, etc.)
- Scope of refinement (3-step onboarding, dashboard, feature page)
- Overall tone (welcoming, functional, playful, etc.)
- Key changes made (top 3-5 refinements)

### 2. Copy Refinement by Section
For each screen/section:
- **Before**: Original placeholder copy
- **After**: Refined copy matching brand voice
- **Rationale**: Why changed? What principle applied?
- **Alternative Options**: If multiple approaches viable

### 3. Complete Copy Inventory
- All final copy organized by screen/section
- Grouped by type (headlines, buttons, labels, messages)
- Ready for direct implementation

### 4. Tone Notes
- Overall tone for each major section
- Context for developer/copywriter handoff
- Voice level (% conversational vs. functional)
- Variations for different user states

### 5. Localization Guidance
- British English spelling checklist
- Cultural references to maintain/adapt
- Region-specific considerations (date format, currency, measurements)

### 6. Implementation Notes
- Character limits (if relevant)
- Dynamic content (user names, dates, variables)
- A/B testing opportunities
- Edge cases to consider (empty states, long text, etc.)
- Accessibility considerations (aria-labels, screen readers)

---

## Where to Save Deliverables

**CRITICAL**: Copy refinement documents are project deliverables, NOT skill examples.

### Deliverable Location
- **Save to**: `docs/` directory in the repo root
- **File naming**: `[feature]-copy-refinement.md` (e.g., `onboarding-copy-refinement.md`)
- **DO NOT save to**: `.claude/skills/copywriter/examples/` (that's for skill reference examples only)

### Example Paths
✅ **Correct**: `/home/scott/code/pixelharmony/chonkcheck/docs/onboarding-copy-refinement.md`
❌ **Wrong**: `/home/scott/code/pixelharmony/chonkcheck/.claude/skills/copywriter/examples/onboarding-copy-refinement.md`

### Skill Directory Contents
The `.claude/skills/copywriter/` directory contains:
- `SKILL.md` - This skill definition
- `references/` - Brand voice guide, copy patterns, messaging framework (permanent reference materials)
- `examples/` - Example copy refinements showing the format/approach (reference only, not real deliverables)

**Rule**: If it's a real copy refinement for the project, it goes in `docs/`. If it's a reference example for the skill, it goes in `examples/`.

---

## Copy Patterns Reference

### Common UI Elements

**Buttons**:
- Primary CTAs: Verb-first, specific ("Start Tracking", "Save Recipe")
- Secondary: Non-committal ("Skip for Now", "Cancel")
- Destructive: Clear consequence ("Delete Food")

**Error Messages**:
- Pattern: [What went wrong] [How to fix it]
- Friendly opener ("Oops!", "Hmm")
- Example: "Oops! That number doesn't look right. Try a value between 1 and 300?"

**Success Messages**:
- Pattern: [What happened] [Positive reinforcement]
- Example: "Recipe saved! Nice work"

**Empty States**:
- Pattern: [What's missing] [Encouraging next step]
- Example: "No recipes yet. Create your first one!"

**Complete Copy Patterns**: See `references/copy-patterns.md`

---

## Messaging Framework

### Value Proposition Formula
**[User pain point] → [Our solution] → [Emotional benefit]**

Example:
- Pain: "endless menus, confusing databases"
- Solution: "ChonkCheck keeps it simple"
- Benefit: "get back to the good stuff"

### Feature Messaging Structure
```
Headline: Short, punchy, conversational (5-8 words)
Body: Specific scenario, relatable language (2-3 sentences)
CTA: Action-oriented, clear next step
```

**Example**:
```
Headline: Cook Twice? Log Once.

Body: That lasagne you make every Sunday? Save it as a recipe and add
      the whole thing with one tap. We'll work out the macros per
      portion—you just focus on getting the seasoning right.

CTA: Create Your First Recipe
```

**Complete Messaging Framework**: See `references/messaging-framework.md`

---

## Examples

### Real-World Example
**File**: `examples/onboarding-copy-refinement.md`

Based on actual onboarding UX design plan (`docs/onboarding-ux-design.md`). Shows complete refinement of 3-step onboarding flow with before/after, rationale, and implementation notes.

**Key Refinements**:
- "Welcome to ChonkCheck!" → "Welcome! Let's get you sorted."
- "Let's personalize your tracking experience" → "Quick setup. Promise."
- "Used in BMR calculation formula" → "We use this for calorie calculations"
- Removed all acronyms (TDEE, BMR), added personality, applied British English

---

### Template Example
**File**: `examples/dashboard-copy-example.md`

Fictional dashboard refinement showing format and approach. Demonstrates tone notes, localization guidance, A/B testing opportunities, and alternative options.

---

## Quality Standards

A complete copy refinement should:

- ✅ **Match ChonkCheck brand voice consistently** (conversational, foodie-focused, judgment-free)
- ✅ **Use British English throughout** (colour, centre, kg, £, DD/MM/YYYY)
- ✅ **Lead with benefits, not features** (user outcome, not technical implementation)
- ✅ **Use specific scenarios over generic claims** ("That lasagne you make every Sunday?" not "Recipe management system")
- ✅ **Avoid judgment language about food/diet** (no "cheat meals", "guilt", "clean eating")
- ✅ **Be conversational, never corporate** (contractions, direct address, no jargon)
- ✅ **Provide clear rationale for changes** (explain why each refinement was made)
- ✅ **Include tone notes for each section** (context for handoff)
- ✅ **Consider all edge cases** (empty, error, loading, success states)
- ✅ **Be implementable** (realistic character counts, clear instructions)

---

## Key Design Tokens (for Context)

### Brand Colors
- **Primary/Vivid**: `#22c55e` (green - success, positive actions)
- **Coral**: `#ff6347` (vibrant accent)
- **Amber**: `#f59e0b` (warm accent)
- **Teal**: `#14b8a6` (accent)
- **Purple**: `#a855f7` (accent)
- **Danger**: `#ef4444` (errors, destructive actions)

### Typography
- **Font**: Inter (web/mobile), default system fonts (marketing)
- **Scale**: text-xs (12px), text-sm (14px), text-base (16px), text-lg (18px), text-xl (20px)

### Responsive Breakpoints
- **Mobile**: 375px+ (mobile-first)
- **Tablet**: 768px+
- **Desktop**: 1024px+

---

## Additional Resources

### Reference Files
- `references/brand-voice-guide.md` - Brand personality, tone by context, words to use/avoid
- `references/copy-patterns.md` - UI patterns (buttons, forms, errors, success, empty states)
- `references/messaging-framework.md` - Value proposition, feature messaging formulas

### Marketing Copy Examples (Codebase)
- `apps/marketing/src/components/Hero.tsx` - Hero headlines and subheadlines
- `apps/marketing/src/components/Features.tsx` - Feature benefit copy
- `apps/marketing/src/components/ComingSoon.tsx` - Future features messaging
- `apps/marketing/src/components/CTA.tsx` - Call-to-action patterns

### UX Plans (Codebase)
- `docs/onboarding-ux-design.md` - Onboarding flow with placeholder copy (source for real example)

### Project Context
- `CLAUDE.md` - Project guidelines, brand voice summary, design language

---

## Success Criteria

Your copy refinement is successful when:

1. **User can visualize the scenario** - "That lasagne you make every Sunday?" = instant connection
2. **Tone matches context** - Playful for marketing, functional for app UI, helpful for errors
3. **British English throughout** - No American spellings or terminology
4. **No jargon or acronyms** - Technical terms replaced with user-friendly language
5. **Judgment-free language** - No diet culture terms or moralizing about food
6. **Clear next steps** - Every CTA, error, and empty state guides user forward
7. **Consistent voice** - All copy sounds like it came from the same friendly, foodie-focused brand
8. **Implementable** - Developers/designers can use the copy inventory directly
9. **Rationale provided** - Changes are explained, not arbitrary
10. **Edge cases covered** - Empty states, errors, loading states all have personality

---

## Notes for Developers & Copywriters

### For Developers
- **Character limits**: Provided in implementation notes when relevant
- **Dynamic content**: Variables marked clearly (e.g., [X] cal/day, [User name])
- **Responsive**: Mobile-first copy, same across breakpoints unless noted
- **Accessibility**: aria-labels and alt text specified where needed

### For Copywriters
- **Copy inventory**: Ready to implement directly
- **Tone notes**: Context for each section's voice level
- **Alternative options**: Multiple variations provided when viable
- **Localization**: British English checklist included
- **A/B testing**: Opportunities identified for optimization

### For UX Designers
- **Integration**: This skill complements the UX design skill
- **Workflow**: UX designer creates plan with placeholders → Copywriter skill refines copy
- **Handoff**: Copy inventory maps directly to UX wireframes
- **Iteration**: Refinements include rationale for design decisions

---

## Relationship to UX Design Skill

**Complementary Workflow**:
```
UX Design Skill (Phase 1-3)
    ↓
Creates wireframes + placeholder copy
    ↓
Copywriter Skill (This Skill)
    ↓
Refines copy to match brand voice
    ↓
Complete UX + Copy Specification
    ↓
Ready for Implementation
```

**Division of Labor**:
- **UX Skill**: Information architecture, wireframes, component specs, user flows, placeholder copy
- **Copywriter Skill**: Brand voice application, messaging strategy, copy refinement, tone guidance

**When to Use Both**:
1. User asks for complete feature design → Use UX skill first
2. UX plan complete with placeholders → Use Copywriter skill to refine
3. User asks for both design + copy → Use UX skill, then Copywriter skill
4. User only needs copy (no design) → Use Copywriter skill directly

---

## Maintenance

This skill should be updated when:
- Brand voice evolves significantly
- New copy patterns emerge in the product
- User research reveals better language
- New platforms launch (e.g., mobile apps)
- Marketing campaigns establish new messaging

**Review cadence**: Quarterly, or before major product launches

**Update checklist**:
- [ ] Brand voice guide reflects current personality
- [ ] Copy patterns include new UI elements
- [ ] Messaging framework aligns with product positioning
- [ ] Examples remain relevant and accurate
- [ ] Reference files link to current codebase locations

---

## Quick Start Guide

### Quick Start

1. **Read this SKILL.md** - Understand when and how to use the skill
2. **Review brand-voice-guide.md** - Internalize ChonkCheck personality
3. **Scan copy-patterns.md** - Familiarize with common UI patterns
4. **See examples/** - Understand expected output format

---

## Common Pitfalls to Avoid

1. **Too corporate**: "Personalize your tracking experience" → "Let's get you sorted"
2. **Too generic**: "Recipe management system" → "That lasagne you make every Sunday?"
3. **Too clever**: "The whey to success" → Use clear copy
4. **American English**: "Customize your colors" → "Customise your colours"
5. **Judgment language**: "Log your cheat meals" → "Log your meals"
6. **Passive voice**: "Your recipe has been saved" → "Recipe saved! Nice work"
7. **Vague errors**: "Invalid input" → "Oops! That number doesn't look right..."
8. **Over-the-top**: "AMAZING JOB!!!" → "Nice work"

---

## Tips for Excellence

1. **Read it aloud** - If it doesn't sound conversational, revise
2. **Visualize the scenario** - Can you picture it? Good. Can't? Revise.
3. **Cut ruthlessly** - Shorter is almost always better
4. **Test the "why"** - Why this word? Why this structure? Answer or reconsider.
5. **Match user's state** - Frustrated? Excited? Curious? Adjust tone accordingly.
6. **Reference real examples** - Look at Hero.tsx, Features.tsx for inspiration
7. **Use the checklist** - Quality checks catch issues before delivery
8. **Provide alternatives** - When in doubt, offer 2-3 options
9. **Explain your thinking** - Rationale helps developers understand intent
10. **Celebrate small details** - Great microcopy makes a huge difference

---

## Version History

- **v1.0.0** (2026-01-14) - Initial skill creation
- **v1.1.0** (2026-01-20) - Condensed reference files and examples for reduced context usage
