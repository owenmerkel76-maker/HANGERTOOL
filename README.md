# ROB MEP Auto Hanger v0.3.7 field test

[Download the complete updated tool ZIP](releases/ROB-MEP-Auto-Hanger-v0.3.7-baseline.zip?raw=true)

[Read the public-tool comparison](releases/PUBLIC_TOOL_COMPARISON.md) | [Follow the controlled next test](releases/NEXT_TEST.md)

The latest update follows a source comparison with Murray-Tools, the public Hanger Layout add-in and Autodesk SDK 2025 samples. Hosted creation and rod-detachment patterns match; retained-placement failures occur in expanded validation. GraphicsStyle definitions are now filtered. Optional unchecked, run-only review can classify ambiguous unreadable drawing/coordination references; known physical geometry, MEP and approved targets are ineligible.

Use the integrated Single hanger test with exactly one duct and a clicked station. It reports creation, requested/actual origin, every rod's raw and validated targets, sizing and clearance. It always rolls back; zero retained is expected even on PASS. Normal placement remains available after a reviewed test.

347 offline tests passed. Original archive provenance and complete ZIP integrity were verified. Public implementations were source-reviewed, not executed in the user's model. Actual Revit field behavior remains unverified.

SHA256: `789148a65b317a7625fe420a7a93d81733950c2e322b4eea5eeb7ac10c67551f`
