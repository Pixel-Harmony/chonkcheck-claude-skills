# ChonkCheck Claude Skills

Shared Claude Code skills for ChonkCheck product development. These skills provide consistent UX design and copywriting guidance across all ChonkCheck platforms (web, mobile).

## Installation

### Option 1: Claude Plugin Marketplace (Recommended)

Add the marketplace and install the plugin in your project:

```bash
# Add the marketplace
/plugin marketplace add Pixel-Harmony/chonkcheck-claude-skills

# Install the skills plugin
/plugin install chonkcheck-skills@chonkcheck-skills
```

Or configure in your project's `.claude/settings.json`:

```json
{
  "extraKnownMarketplaces": {
    "chonkcheck-skills": {
      "source": {
        "source": "github",
        "repo": "Pixel-Harmony/chonkcheck-claude-skills"
      }
    }
  },
  "enabledPlugins": {
    "chonkcheck-skills@chonkcheck-skills": true
  }
}
```

### Option 2: Clone Alongside Project

Clone this repository next to your project:

```bash
cd /path/to/your/workspace
git clone https://github.com/Pixel-Harmony/chonkcheck-claude-skills.git
```

Then reference the skills directory in your project's CLAUDE.md.

## Available Skills

### UX Design (`/chonkcheck-skills:ux-design`)

Expert UX design guidance for ChonkCheck features. Provides:
- Design system compliance (colors, typography, spacing)
- Accessibility guidelines (WCAG 2.1 AA)
- Mobile-first responsive patterns
- Component specifications and wireframes
- User flow documentation

**Usage**: `/chonkcheck-skills:ux-design` or describe what you want to design

### Copywriter (`/chonkcheck-skills:copywriter`)

Brand voice and UX copy refinement for ChonkCheck. Provides:
- Tone and voice guidelines
- Messaging framework
- Copy patterns for common UI elements
- Error message templates
- Microcopy best practices

**Usage**: `/chonkcheck-skills:copywriter` or ask to refine copy

## Directory Structure

```
chonkcheck-claude-skills/
├── .claude-plugin/
│   ├── plugin.json           # Plugin manifest
│   └── marketplace.json      # Marketplace configuration
├── skills/
│   ├── ux-design/
│   │   ├── SKILL.md          # Skill definition and instructions
│   │   ├── references/
│   │   │   ├── marketing-design-system.md
│   │   │   ├── web-app-design-system.md
│   │   │   └── accessibility-guidelines.md
│   │   └── examples/
│   │       ├── dashboard-design-example.md
│   │       └── onboarding-ux-design.md
│   └── copywriter/
│       ├── SKILL.md          # Skill definition and instructions
│       ├── references/
│       │   ├── brand-voice-guide.md
│       │   ├── messaging-framework.md
│       │   └── copy-patterns.md
│       └── examples/
│           ├── dashboard-copy-example.md
│           └── onboarding-copy-refinement.md
└── README.md
```

## Using with ChonkCheck Projects

After installation, skills are available in any ChonkCheck project:

1. **UX Design**: Ask to design a feature, page, or user flow
2. **Copywriter**: Ask to refine copy, write CTAs, or improve messaging

Skills are automatically invoked based on context, or manually via `/chonkcheck-skills:ux-design` and `/chonkcheck-skills:copywriter`.

## Maintenance

Update skills when:
- New design patterns emerge
- Brand voice evolves
- Accessibility requirements change
- New platforms are added (e.g., Android)

Keep reference files in sync with actual product implementations.

## License

Private repository - Pixel Harmony proprietary content.
