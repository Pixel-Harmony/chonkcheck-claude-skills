# ChonkCheck Accessibility Checklist

WCAG 2.1 Level AA compliance requirements for all features.

---

## Touch Targets

| Requirement | Standard |
|-------------|----------|
| Minimum size | 44x44px |
| Spacing between targets | 8px minimum |
| Icon buttons | Use padding to increase tap area: `className="p-3 -m-3"` |

---

## Color Contrast

| Requirement | Ratio |
|-------------|-------|
| Normal text (< 18pt) | 4.5:1 minimum |
| Large text (>= 18pt or 14pt bold) | 3.0:1 minimum |
| UI components | 3.0:1 against adjacent colors |
| Focus indicators | 3.0:1 against background |

**Safe combinations:**
- `text-gray-900` on white (16.1:1)
- `text-white` on vivid-500 (3.4:1)
- `text-white` on coral-500 (4.2:1)
- `text-gray-600` on white (4.6:1)

**Avoid:** `text-gray-400` on white (2.9:1 - insufficient)

---

## Keyboard Navigation

| Requirement | Implementation |
|-------------|----------------|
| All interactive elements | Must be keyboard accessible |
| Tab order | Logical (top to bottom, left to right) |
| Focus indicators | `focus:ring-2 focus:ring-primary-500 focus:ring-offset-2` |
| Escape key | Closes modals/dropdowns |
| Enter/Space | Activates buttons/links |

---

## Screen Reader Support

### Semantic HTML
Use correct elements: `<button>` for actions, `<a>` for navigation, `<nav>`, `<main>`, `<section>`, proper heading hierarchy (`h1`-`h6`), `<label>` for inputs.

### ARIA Patterns

| Element | Required ARIA |
|---------|---------------|
| Icon-only button | `aria-label="Delete entry"` |
| Loading state | `aria-live="polite" aria-busy="true"` |
| Modal | `role="dialog" aria-labelledby="title-id" aria-modal="true"` |
| Error message | `role="alert" aria-live="assertive"` |
| Success message | `role="status" aria-live="polite"` |
| Invalid input | `aria-invalid="true" aria-describedby="error-id"` |

---

## Forms

| Requirement | Implementation |
|-------------|----------------|
| Labels | Visible, associated with `htmlFor`/`id` |
| Required fields | Mark with `*` or "(required)" |
| Error messages | Below field, `aria-describedby` linked |
| Field groups | Use `<fieldset>` + `<legend>` |

---

## Motion

**Respect `prefers-reduced-motion`:**
```tsx
// Tailwind approach
className="animate-bounce motion-reduce:animate-none"
```

- No flashing content > 3Hz
- Provide static alternatives to animations

---

## Mobile-Specific

| Requirement | Notes |
|-------------|-------|
| No hover-only interactions | Critical functionality must work on tap |
| Orientation | Support portrait and landscape |
| Zoom | Allow up to 200% without breaking layout |
| Safe areas | Use `env(safe-area-inset-bottom)` for notched devices |

---

## Pre-Ship Checklist

- [ ] Keyboard navigation works (Tab, Enter, Escape, arrows)
- [ ] Screen reader announces content correctly
- [ ] Color contrast meets ratios (4.5:1 text, 3:1 UI)
- [ ] Touch targets are 44x44px minimum
- [ ] Motion respects prefers-reduced-motion
- [ ] Forms have visible labels and clear errors
- [ ] Focus indicators visible with 3:1 contrast
- [ ] Zoom to 200% doesn't break layout
- [ ] Semantic HTML structure correct
- [ ] ARIA labels on icon buttons and dynamic content

---

## Testing Tools

- **Contrast**: WebAIM Contrast Checker, Chrome DevTools
- **Screen readers**: VoiceOver (Mac/iOS), TalkBack (Android), NVDA (Windows)
- **Automation**: axe DevTools extension, Lighthouse
- **Manual**: Keyboard-only navigation, zoom to 200%
