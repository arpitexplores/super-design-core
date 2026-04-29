# Super Design Core

Create implementable UI/UX direction, product flows, visual systems, and component guidance.

## Install

Copy this folder into your agent's skills directory, then restart or reload the agent.

```bash
cp -R super-design-core ~/.your-agent/skills/
```

Use it by name:

```text
Use $super-design-core to help with this request.
```

## Best For

- product UX planning
- information architecture
- visual systems
- React/UI implementation patterns
- rapid layout ideation

## Outputs

- flow and layout notes
- interaction guidance
- visual system tokens
- component priorities

## Modules

| Module | Purpose |
| --- | --- |
| `magic-ui-generator.md` | Rapid UI generation, layout exploration, and implementation-ready design prompts |
| `react-ui-patterns.md` | React and framework UI patterns, component structure, and implementation guidance |
| `ui-ux-designer.md` | UX strategy, flows, information architecture, and interaction design |
| `ui-ux-pro-max.md` | Visual systems, styles, palettes, typography, components, and design intelligence |

## Example Prompts

- `Use $super-design-core to design a dashboard for this product.`
- `Use $super-design-core to improve this onboarding flow.`
- `Use $super-design-core to create a visual system for a SaaS landing page.`

## Package Contents

- `SKILL.md` is the installable skill entry point.
- `references/modules/` contains detailed workflows loaded only when needed.
- `agents/` contains optional agent metadata where supported.
- `scripts/` and `assets/` are optional helpers when bundled.

## Compatibility

This skill is plain Markdown and is intended to be agent-agnostic. If a bundled helper mentions a specific tool path, translate that instruction to the equivalent path for your environment.

## Version

See `VERSION` and `CHANGELOG.md`.

## Licence

MIT. See the root repository `LICENSE`.
