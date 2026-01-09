## Key Points from the Meeting

- Good progress has been made:
  - First PR was merged successfully
  - Second PR reviewed with useful back-and-forth
  - Early PR-based communication is already improving
- The **PR → review → iterate loop** is starting to become a habit:
  - This repetition is intentional and will feel natural over time
  - Efficient communication is a core skill being developed early
- Airflow is now running locally via **Docker Compose**:
  - Simple “hello world” DAG is running successfully
  - Logs confirm expected execution
- Testing approach discussion:
  - Airflow DAGs are **hard to test directly**
  - Strong agreement that:
    - Do **not** test Airflow plumbing itself
    - Focus on **unit testing Python logic**
    - Keep DAGs as thin wrappers around testable Python functions
- End-to-end tests with Docker Compose are possible, but:
  - Should be used sparingly
  - Unit tests should cover the majority of logic
- Comparison with Prefect:
  - Prefect allows easier local execution and testing
  - Airflow has more friction, which is useful to experience deliberately
- Architectural principle reinforced:
  - Business logic lives in plain Python
  - DAGs orchestrate, not compute
- Testing & debugging workflow in VS Code:
  - `uv run pytest` works well for running all tests
  - VS Code’s **Python Testing UI** (pytest integration) is powerful:
    - Configure tests once
    - Run all tests or individual tests from the UI
    - Debug tests using breakpoints
    - Inspect variables and objects interactively
- Debugging insight:
  - Debugging tests is a major productivity multiplier
  - Helps quickly diagnose issues like:
    - Incorrect DAG folder paths
    - Unexpected object structures
- Tooling setup is paying off:
  - Proper package structure avoids path-related test issues
  - Many common pain points were avoided due to earlier setup
- Project direction discussion:
  - Desire for a **non-toy, realistic dataset**
  - Preference for data that updates regularly (e.g. daily)
  - Strong interest in:
    - Weather / meteorology data
    - Energy market data
- Suggested project direction:
  - Daily weather data ingestion (e.g. OpenWeather API)
  - Optional correlation with energy prices
  - ETL-focused pipeline with increasing complexity
- Visualisation ideas:
  - Streamlit as a fast prototyping tool
  - Possible evolution:
    - Streamlit prototype
    - FastAPI backend
    - Optional full frontend later
- Alternative side-project idea:
  - “Stadium of Light – Wall of Fame” brick registry
  - Crowdsourced + AI-assisted transcription
  - Strong community and portfolio value
  - Interesting but **secondary priority** for now
- Strategic focus:
  - Primary goal is to **hit the ground running on 19th January**
  - Prioritise skills and patterns that map directly to the new role
- Personal reflection:
  - Perfectionism identified as a blocker
  - Key takeaway: **ship early, iterate often**
  - Progress beats perfection

## Actions to Take Away

### Immediate / Short-Term Actions

- [ ] Continue using **early PRs** as the primary communication channel
- [ ] Keep DAGs minimal and push logic into testable Python functions
- [ ] Use VS Code’s pytest integration regularly:
  - Run tests from the UI
  - Debug tests with breakpoints
- [ ] Create a new GitHub issue:
  - *Extract daily data from OpenWeather API*
- [ ] Implement:
  - Python extraction logic
  - Simple Airflow DAG wrapper
  - Unit tests for the extraction logic
- [ ] Store extracted data locally (CSV is sufficient for now)

### Near-Term (Next Sessions)

- [ ] Create a second issue:
  - *Design medallion-style data layout (bronze/silver)*
- [ ] Explore how this could later map to:
  - Iceberg
  - Cloud storage (e.g. S3)
- [ ] Keep everything local initially to reduce complexity
- [ ] Identify:
  - Areas of confidence for the new role
  - Gaps or uncertainties to focus coaching sessions on

### Ongoing Habits to Reinforce

- [ ] Ship “good enough” code early
- [ ] Avoid over-polishing initial implementations
- [ ] Use PRs + reviews to refine ideas incrementally
- [ ] Treat orchestration as the *last* layer, not the first
- [ ] Prioritise learning that directly supports starting strong on the 19th