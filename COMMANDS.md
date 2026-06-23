# Command Reference

## `/ios plan <requirement>`

Use before implementation when product direction, module placement, UX, interaction, UI structure, data linkage, or acceptance criteria are not yet frozen.

Optional hints:

```text
--focus=architecture
--focus=ux
--focus=data-loop
--output=compact-spec
--output=execution-prompt
--output=full-spec
```

Default: one recommended solution, not an option tree.

## `/ios implement <task>`

Use for production changes under a defined scope.

```text
/ios implement ISS-123
/ios implement --focus=data "Add edit support without changing creation behavior"
```

Focus hints narrow attention but never waive affected-surface checks.

## `/ios review <scope>`

Use after implementation or for a targeted code audit.

```text
/ios review current branch
/ios review --focus=full
/ios review --focus=data
/ios review --focus=ui
/ios review --focus=test
/ios review --fix current branch
```

Without `--fix`, report findings only. With `--fix`, scan the relevant scope first, then repair deterministic in-scope findings and revalidate.

## `/ios debug <failure>`

Use when the behavior is wrong but the cause is unknown.

```text
/ios debug "After editing a recurring plan, today's timeline is empty"
```

Debug mode must explain the violated invariant, root cause, and why existing tests did not catch it.

## `/ios ui <submode> <surface>`

```text
/ios ui replicate <design or screenshot>
/ios ui review <implemented screen>
/ios ui fix <visual or interaction defect>
```

Rendered evidence is required for claims about alignment, wrapping, clipping, density, or visual fidelity.

## `/ios test feature <feature>`

Use for focused XCTest coverage.

```text
/ios test feature FeatureEditor
/ios test feature --focus=interaction CheckoutForm
```

Unit or owner-level tests are preferred. UI tests are added only when actual hit-testing, navigation containers, gestures, or rendered enabled state must be proven.

## `/ios audit app`

Use for staged whole-app QA, release validation, or cross-module acceptance.

```text
/ios audit app
/ios audit app --scope=release-candidate
```

Build a module inventory from the repository; never assume a fixed app structure.

## `/ios verify <requirement>`

Use for final acceptance.

The verdict must be exactly one of:

- `通过`
- `有条件通过`
- `不通过`

Every passed criterion needs evidence.
