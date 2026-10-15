# ROB MEP Auto Hanger v0.3.7 field test

[Download the complete updated tool ZIP](releases/ROB-MEP-Auto-Hanger-v0.3.7-baseline.zip?raw=true)

[Public-tool comparison](releases/PUBLIC_TOOL_COMPARISON.md) | [Controlled next test](releases/NEXT_TEST.md)

This hotfix corrects the single-hanger diagnostic extractor contract: extract_segment returns (segment, issue), which is now unpacked before dictionary access. Invalid extraction exits before station picking or model transactions. Wrapper tests now execute the actual deployed extractor/profile reader rather than mocking the wrong return format.

The integrated one-duct clicked-station diagnostic still reports creation, every rod, measured and validated targets, sizing/clearance and origin offset, then always rolls back. Reference review remains explicit and execution-only. Normal placement and native/draft safeguards remain unchanged.

350 offline tests passed. Original archive and ZIP integrity verified. Actual Revit placement remains unverified; repeat the same single-hanger field test.

SHA256: `ae422c63f53aaa7921b8b6c0cd454e52bbbe158e60422dfe3638f84676e6426b`
