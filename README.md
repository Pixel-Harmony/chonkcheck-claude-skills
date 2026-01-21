# ChonkCheck Claude Skills

Shared Claude Code skills for ChonkCheck product development. These skills provide consistent UX design and copywriting guidance across all ChonkCheck platforms (web, mobile).

## Skills

### UX Design (`ux-design/`)

Expert UX design guidance for ChonkCheck features. Provides:
- Design system compliance (colors, typography, spacing)
- Accessibility guidelines (WCAG 2.1 AA)
- Mobile-first responsive patterns
- Component specifications and wireframes
- User flow documentation

**Usage**: `/ux-design` or describe what you want to design

### Copywriter (`copywriter/`)

Brand voice and UX copy refinement for ChonkCheck. Provides:
- Tone and voice guidelines
- Messaging framework
- Copy patterns for common UI elements
- Error message templates
- Microcopy best practices

**Usage**: `/copywriter` or ask to refine copy

## Setup

To use these skills in a Claude Code project, clone this repository and reference it in your project's CLAUDE.md:

```bash
# Clone alongside your project
cd /path/to/your/workspace
git clone https://github.com/Pixel-Harmony/chonkcheck-claude-skills.git
```

Then in your project's CLAUDE.md, add instructions to reference the skills:

```markdown
## Shared Skills

ChonkCheck shared skills are located in the adjacent `chonkcheck-claude-skills` repository.
When invoking `/ux-design` or `/copywriter`, reference the skill files from that repository.
```

## Directory Structure

```
chonkcheck-claude-skills/
├── ux-design/
│   ├── SKILL.md              # Skill definition and instructions
│   ├── references/
│   │   ├── marketing-design-system.md
│   │   ├── web-app-design-system.md
│   │   └── accessibility-guidelines.md
│   └── examples/
│       ├── dashboard-design-example.md
│       └── onboarding-ux-design.md
├── copywriter/
│   ├── SKILL.md              # Skill definition and instructions
│   ├── references/
│   │   ├── brand-voice-guide.md
│   │   ├── messaging-framework.md
│   │   └── copy-patterns.md
│   └── examples/
│       ├── dashboard-copy-example.md
│       └── onboarding-copy-refinement.md
└── README.md
```

## Maintenance

Update skills when:
- New design patterns emerge
- Brand voice evolves
- Accessibility requirements change
- New platforms are added (e.g., Android)

Keep reference files in sync with actual product implementations.

## License

Private repository - Pixel Harmony proprietary content.
