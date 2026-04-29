---
name: super-design-core
description: "Core UI/UX and product design: IA, flows, visual systems, UI patterns, and generators. Use for end-to-end design work."
---

# Super Design Core

## Overview
Create end-to-end UI/UX direction, visual systems, and implementable UI guidance.


## User Intent Examples
- "Need help with UI Generation for my product/site."
- "Create a plan for UI Patterns (React & Frameworks)."
- "Audit or improve UX Design."

## Capabilities
- Product UX, IA, and flows
- Visual systems and component guidance
- Framework-specific UI patterns
- Rapid UI generation and layout ideation

## Routing Map (Modules)
- **UI Generation** -> `references/modules/magic-ui-generator.md`
- **UI Patterns (React & Frameworks)** -> `references/modules/react-ui-patterns.md`
- **UX Design** -> `references/modules/ui-ux-designer.md`
- **UI/UX Systems** -> `references/modules/design-systems.md`

## Default Flow
1. Confirm product context, audience, and platform.
2. If a full UX plan is requested, start with UI/UX Designer.
3. If implementation patterns are requested, jump to React UI Patterns.
4. If a fast layout/generator is requested, jump to Magic UI Generator.

## Minimal Intake Questions
Ask only what is missing:
- Product type and platform (web, mobile, desktop)
- Target users and key flow
- Brand or existing design language

## Output Format
- Layout and flow notes
- Interaction guidance
- Visual system tokens
- Component priorities

## Bundled References
- `references/modules/`
- `scripts/`
- `assets/`

## Compatibility Notes
- If any module references slash commands or tool-specific paths, translate them into plain-language steps.
- Keep outputs platform-agnostic unless the user specifies a specific tool, stack, or agent.

## Guardrails
- Match brand or existing design language.
- Avoid generic UI.
- Keep output implementable.
