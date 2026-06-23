---
name: ios-engineering
description: End-to-end product planning, SwiftUI/iOS implementation, engineering review, root-cause debugging, UI replication and visual review, XCTest generation, whole-app audit, and evidence-based acceptance. Use for iOS product requirements, UI/UX changes, feature implementation, bug investigation, code review, testing, release validation, or final verification.
---

# iOS Engineering

## Purpose

Use this single skill for the complete lifecycle of an existing iOS product:

```text
product decision
→ design freeze
→ implementation
→ review
→ debugging
→ UI validation
→ feature testing
→ whole-app audit
→ final acceptance
```

The skill is generic. Product facts, domain rules, real module names, build schemes, test targets, design tokens, and component names must come from the active repository.

## Invocation

Preferred commands:

```text
/ios plan <requirement>
/ios implement <requirement or task>
/ios review <scope>
/ios debug <observed failure>
/ios ui <replicate | review | fix> <screen or design>
/ios test feature <feature>
/ios audit app
/ios verify <requirement or change>
```

Natural-language equivalents are valid. If the user explicitly names a mode, use it.

## Mode routing

Select one primary mode:

- `plan`: decide product structure, requirement scope, UX, interaction, UI structure, data loop, execution grouping, and acceptance criteria.
- `implement`: change production behavior under a frozen requirement.
- `review`: inspect completed or partial work for defects and omissions.
- `debug`: trace an observed failure to its root cause and add regression protection.
- `ui`: replicate, review, or repair rendered iOS UI.
- `test`: add focused XCTest coverage for one feature or contract.
- `audit`: run staged whole-app QA and cross-flow regression.
- `verify`: decide whether a requirement is actually complete.

Do not activate several full workflows at once. A primary mode may load references from other modes when the task crosses boundaries.

## Required project discovery

Before applying generic rules, search for project-specific sources in this order:

1. `.agent/project-profile.md`
2. `docs/project/ios-engineering-profile.md`
3. `docs/ENGINEERING-SKILL-PROFILE.md`
4. current issue, PRD, requirement, or design artifact
5. product and domain rules
6. architecture and data-flow documentation
7. design-system and component documentation for UI work
8. testing profile, schemes, targets, and validation commands

Project facts override examples in this skill. Project rules cannot weaken data integrity, deterministic testing, safety, accessibility, or evidence requirements.

## Universal operating rules

1. Understand the real user goal before accepting the requested control or surface as the solution.
2. Inspect the existing product and implementation before proposing a new module, data owner, or component.
3. Prefer `reuse → extend → refactor → rebuild`, in that order.
4. Default to one recommended solution. Offer alternatives only for a material trade-off or unresolved product conflict.
5. Separate durable product facts from implementation notes and one-time audit evidence.
6. Identify the authoritative state owner and complete read/write path before modifying stateful behavior.
7. Preserve explicit non-goals and already-correct behavior.
8. Fix the earliest wrong assumption or transition, not only the visible symptom.
9. Validate with the repository's real build, test, runtime, and visual entry points.
10. Report confirmed facts, inferred risks, unknowns, evidence, and remaining blockers separately.

## Hard rules

- Do not invent product behavior, module names, token names, test schemes, or target names.
- Do not create a parallel source of truth to make a feature appear to work.
- Do not hide missing business data with silent fallback.
- Do not rewrite historical facts from current mutable configuration.
- Do not classify a smell as a confirmed bug without a reachable failure path.
- Do not weaken assertions, validation, or business rules to make tests pass.
- Do not use arbitrary sleeps as synchronization or proof of correctness.
- Do not alter product semantics merely to match a static screenshot.
- Do not start fixing a review surface before the relevant scope has been scanned and findings grouped.
- Do not require user confirmation for deterministic, in-scope fixes when the user already requested implementation or repair.
- Do not auto-resolve a genuine product/design conflict; record the conflict and recommended decision.
- Do not declare completion from compilation, checked boxes, comments, or mock-only tests.
- Do not turn every observation into current-scope work; classify current, deferred, historical, and global-system issues.

## Reference loading

Load only what the task needs:

- Product architecture, requirement, UX, information architecture, or execution prompt:
  - `modes/plan.md`
  - `references/product-architecture.md`
  - `references/requirement-and-ux.md`
  - `references/interaction-and-state-design.md`
- Any production change:
  - `modes/implement.md`
  - `references/core-engineering-rules.md`
- Write, delete, persistence, history, notification, cache, widget, watch, or cross-page synchronization:
  - `references/data-consistency.md`
  - `references/fallback-and-error-handling.md`
- Code review or unexplained behavior:
  - `references/bug-patterns.md`
- SwiftUI, navigation, sheet, safe area, keyboard, accessibility, or layout:
  - `references/swiftui-and-ios-ui.md`
- Design reproduction or rendered visual review:
  - `references/ui-replication.md`
  - `references/visual-quality-review.md`
- Feature tests:
  - `modes/test.md`
  - `references/testing.md`
- Whole-app QA:
  - `modes/audit.md`
  - `references/full-app-audit.md`
- Acceptance or completion claims:
  - `modes/verify.md`
  - `references/evidence-and-reporting.md`
- Localization or copy-sensitive work:
  - `references/localization.md`

## Output policy

Default to concise, executable output. Expand only when the user asks for a full specification or audit report.

Every formal output must make these visible:

- scope examined
- product or engineering decision
- confirmed findings or completed changes
- preserved behavior and explicit non-goals
- evidence
- unresolved risks, decisions, or unverified conditions
- next required action, if any

Use the matching file under `templates/` when a durable report or execution prompt is needed.
