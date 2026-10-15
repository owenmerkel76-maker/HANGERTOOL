# Office review — simplified Auto Hanger menus

Install the complete extension from the existing GitHub download and reload
pyRevit (restart Revit if helpers remain cached). Use a detached Revit 2025 model.
This update simplifies menus; it does not establish successful IFC attachment.

## Everyday workflow

1. Select fabrication duct and open **Auto Hanger**. Choose the structural
   model(s) in the short model list.
2. In **Connection targets**, check the intended **Beams / joists** and optional
   **Roof / deck fallback** groups. Expand a group to review individual types,
   or use **Select in Model** for specific members. **Connect rods to** clearly
   shows steel-first, steel-only or deck-only behavior. Choose **Continue to hangers**.
3. In **Hangers and placement**, check the suggested hanger for each selected
   duct service, spacing cap and maximum rod length. Only relevant duct shapes
   appear. Keep **Preview only** checked and choose **Preview layout**.
4. Review the proposal. To place, reopen the tool, confirm targets and hanger
   choices, clear **Preview only**, then choose **Place hangers**. Leaving
   **Allow measured, unattached hangers** enabled permits marked drafts only
   when every rod has a measured approved target and passes enabled checks.

Project structure approvals are remembered when confirmed; hanger-service
settings and Preview retain their existing per-launch defaults. Advanced options
are optional, not required steps. The spacing schedule remains preliminary and
must match the approved project support/hardware schedule.

## What is tucked away

- **Advanced structure options**: custom/unclassified IFC types, per-type role
  overrides, direct-pick role and the initial rod limit. Saved nonstandard type
  roles remain visible even when advanced controls are closed. The main settings
  rod limit is the final confirmed value.
- **Advanced layout options**: optional large-duct trapeze threshold, end/turn
  offset, size-based schedule details, fitting fallback and clearance switches.
  Enabling the trapeze override reveals the per-service trapeze choices.
- **Office support / diagnostics**: temporary single-hanger test and deliberate
  per-run review of ambiguous drawing references. Leave these off for normal use.

## Office pilot feedback

Try one small area first. Record whether a first-time user understands the
steel/deck selection, finds the correct hanger, distinguishes Preview from Place,
and can identify retained drafts. Note the time between each screen, model size,
and number of selected links. A less crowded menu does not prove faster IFC
geometry discovery; opening times still require measurement in Revit.

If placement is blocked, retain the output and review the cause with the tool
owner. Do not disable clearance or classify uncertain physical objects as
references simply to get a hanger placed. The previous one-hanger result proved
creation and correct duct hosting at its chosen station, but both rods missed the
one selected steel member by 2.630 feet in plan. Menu changes do not solve a
missing target above a rod.

## Optional support procedure — one hanger, always rolled back

Use this test to identify the failing stage before testing another full area.
It is part of the existing Auto Hanger button. It does not retain a hanger.

1. Replace the extension with this ZIP and reload pyRevit (restart Revit if
   helper modules remain cached). Work in a detached Revit 2025 test model.
2. Preselect **exactly one straight fabrication duct** below the native deck
   used in the last result. Open Auto Hanger.
3. Approve the intended readable steel and native roof/deck fallback. Use
   **Steel first, then selected deck**, matching the last roof-hit case.
   Leave unclassified target types unchecked.
4. Keep the correct hanger button for that duct's fabrication service. Enable
   **Single hanger test — choose one duct and click a station**. Run it.
   This mode overrides Preview for a temporary rolled-back test and keeps
   clash validation enabled. No spacing or duplicate optimizer runs.
5. If an unreadable-reference list appears, check ONLY background or duplicate
   drawing/coordination references you actually recognize. Checkboxes start
   empty. Physical/uncertain objects stay unchecked. Cancel excludes none.
   The classification is for this run only; it is not saved to other projects.
6. Click the desired station along the selected duct. The point is projected
   onto the duct axis and clamped inside its connector regions.
7. Send the **SINGLE HANGER TEST** output, including the stage table, both rod
   sections, any reference-scope notes and requested/actual origin coordinates.

Interpret the result:

- **PASS**: API creation, host, both/all rod targets, lengths, enabled clearance
  and tested along-duct origin passed. Every test hanger was removed.
- **STATION REVIEW**: geometry/clearance passed but the origin offset needs
  content/connector inspection. No automatic distance reversal was applied.
- **BLOCKED**: the stage table identifies creation, geometry or clearance
  failure, with every readable rod reported. Every test hanger was removed.
- **Zero retained is expected in this test mode**, including on PASS. This is
  not the normal layout's “no hangers kept” failure message.

After reviewing a PASS, disable Single hanger test and try one small normal
layout. For manual structural attachment, enable Keep UNATTACHED. Enable
Review unreadable drawing / coordination references again when needed; scopes
are not persisted. Confirm all retained rods, fitting/branch/end coverage and
actual physical clearances in Revit. A diagnostic PASS is not native anchorage
or full-layout certification.
