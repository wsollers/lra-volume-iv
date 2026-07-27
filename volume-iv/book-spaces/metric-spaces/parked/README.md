# Parked Metric-Space Material

This directory holds metric-space notes and proof stubs that are not part of
the active Volume IV build yet.

Workflow for promoting material out of this directory:

1. Prove the formal statement in Lean.
2. Build the corresponding TeX statement in the active notes.
3. Prove it by hand in the proof files.
4. Add `\LeanFormalizes` metadata only for formalizations that are actually
   part of the worked Lean progression.

Figures may remain in `../figures` even when their related text is parked.
