# Redesign & Migration
Change visual language without destroying product behavior, IA, or maintainability.
Audit → identify intent → extract target language → map tokens → map components → define migration boundaries → migrate screen-by-screen → render/compare → validate.
Preserve working behavior unless scope changes it. Do not rewrite unrelated areas. Prefer normalization/variants over page patches. Identify old-system vs target-reference conflicts before implementation. Avoid big-bang migration when staged replacement reduces regression.
