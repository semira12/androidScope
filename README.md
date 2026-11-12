# androidScope
Android security analysis platform for mapping attack surfaces, tracing runtime behavior, and visualizing potential attack paths.

## Individual Contribution — Semira Nesru (CTC ID: CTC-6043-26)

**Role:** Attack Path & Correlation Engine Developer

### Key Contributions & Implementation Highlights
* **Correlation Engine (`correlation/engine.py`):** Developed the core engine module that correlates static data-flow findings (`static-result.json`) with dynamic runtime instrumentation events (`runtime-events.json`) via method and class signature matching.
* **Schema-Compliant Output Generation:** Implemented producers for `attack-paths.json`, `vulnerability-results.json`, and `evidence.json`, categorizing findings into confirmed (`CORRELATED`) versus unconfirmed (`STATIC_ONLY`) states.
* **Application ID Validation & Mismatch Notes:** Added top-level `application_id` safety checks between static analyses and runtime logs to prevent data contamination, populating human-readable mismatch details into the `"notes"` field of the output schema.
* **Refactored Lookback & Rerun Support:** Removed legacy component lookback heuristics to eliminate false rejections and ensured the engine supports clean, on-demand re-execution when new runtime events are posted via the backend (`/api/analysis/{id}/runtime-events`).

### Presentation & Demo Video
* **Video Link:** https://youtu.be/pnKsJDmntTo
