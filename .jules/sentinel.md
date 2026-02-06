## 2025-05-20 - Mixed DOM/String Rendering
**Vulnerability:** Found `innerHTML` usage with template literals attempting to overwrite safer `document.createElement` logic. The string logic also contained a `ReferenceError` (`blocksHtml`), causing a runtime crash.
**Learning:** The code appeared to be mid-refactor, containing both the "old" unsafe way and the "new" safe way, but the "old" way was winning (and failing).
**Prevention:** Always delete dead code immediately after refactoring. Use linting rules to detect unused variables. Verify refactors by running the code.
