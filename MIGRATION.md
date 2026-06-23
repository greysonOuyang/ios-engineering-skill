# Migration from Previous Skills

This skill consolidates the reusable native-iOS responsibilities of the previous skills without copying project-specific names or forcing the user to select between overlapping skills.

| Previous skill/source | New location |
|---|---|
| `product-architecture-planner` | `modes/plan.md`, `references/product-architecture.md` |
| `ux-product-review` | `modes/plan.md`, `references/requirement-and-ux.md` |
| `requirement-design-verification` | `modes/plan.md`, `modes/verify.md`, `references/interaction-and-state-design.md`, plan/verification templates |
| `product-design-executor` | root execution/output policy, `modes/plan.md`, `templates/execution-prompt.md` |
| `ui-visual-review` | `modes/ui.md`, `references/visual-quality-review.md`, `templates/ui-review-report.md` |
| UI replication methodology | `references/ui-replication.md`, `modes/ui.md`, project profile overlay |
| `ios-generate-feature-tests` | `modes/test.md`, `references/testing.md`, XCTest templates |
| `ios-full-app-test-audit` | `modes/audit.md`, `references/full-app-audit.md`, audit template |
| bug pattern / fallback / data consistency rules | existing generic references loaded by implement/review/debug/test/verify |

## Deliberately not merged

`tailwindcss-ui-refactor` remains independent because it owns a React/Tailwind view-layer workflow, not native iOS/SwiftUI engineering.

## Retired invocation names

Replace old skill calls with:

```text
product architecture / UX / requirement design → /ios plan
feature implementation                     → /ios implement
engineering review                          → /ios review
runtime bug investigation                   → /ios debug
UI replication or visual review             → /ios ui
focused XCTest coverage                     → /ios test feature
whole-app QA                                → /ios audit app
final acceptance                            → /ios verify
```

## Project-specific content removed from the generic skill

The merged skill does not contain:

- app or module names
- fixed module order
- real schemes or test targets
- project token/component names
- medication or other product-domain models
- project-specific build commands

Store those in a project profile based on `templates/project-profile.md`.
