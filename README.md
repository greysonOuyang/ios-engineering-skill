# ios-engineering

A reusable AI skill for product planning and end-to-end delivery of an existing SwiftUI/iOS application.

It is designed for agent environments that load a `SKILL.md` plus supporting references, templates, and scripts. The skill focuses on practical iOS engineering work: planning, implementation, review, debugging, UI validation, test generation, app audits, and evidence-based verification.

## Capabilities

```text
/ios plan
/ios implement
/ios review
/ios debug
/ios ui
/ios test feature
/ios audit app
/ios verify
```

Detailed workflows live in `modes/`. Reusable knowledge lives in `references/`. Project-specific facts must remain in the repository's profile, requirements, domain rules, design system, and test instructions.

## Installation

Copy the complete repository contents into a skill directory supported by your agent environment, or place the `ios-engineering` folder contents into an existing global skills location. Keep the folder intact so relative links to modes, references, templates, and scripts continue to work.

## Repository structure

- `SKILL.md`: entry point and routing rules
- `modes/`: focused workflows such as plan, implement, review, debug, test, audit, and verify
- `references/`: reusable engineering guidance loaded on demand
- `templates/`: durable report and execution templates
- `scripts/`: helper tooling for repeatable analysis
- `agents/openai.yaml`: UI metadata for OpenAI-compatible skill surfaces

## Project profile

Start from `templates/project-profile.md` when a repository does not already expose:

- product and domain truth locations
- module ownership
- state and persistence owners
- design-system names and component paths
- schemes, targets, and validation commands
- project-specific runtime invariants

## Scope boundary

This skill handles native iOS/SwiftUI work. A technology-specific Web skill such as Tailwind/React UI refactoring should remain separate.

## License

MIT
