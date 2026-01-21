## Key Points from the Meeting

- David is in the final days at his current job:
  - Finishes **Thursday lunchtime**
  - Low workload → using the time for **“Python, Python, Python”**
- Coaching workflow expectations were reinforced:
  - Aim for **daily PR review cadence** (when possible)
  - Both sides should rely on **GitHub notifications**
  - If feedback is needed urgently: ping via Circle as well
- David has made strong progress since the coach’s earlier review:
  - Significant refactors after the weekend review
  - Actively using **Copilot code review** to iterate
- A “decisions document” was created:
  - Similar to an **ADR (Architectural Decision Record)**
  - Purpose: record options tried, final choice, and rationale
- Dependency Injection was a key design focus:
  - Creating `requests.Session` outside the client and injecting it
  - Motivation: **testability** (mocking), separation of concerns
  - Coach agreed this is a strong pattern here and aligned with clean/hex architecture ideas
- Config management improvements were implemented:
  - Added `.env` file for URL / API key / timeout
  - Confirmed secrets are in `.gitignore`
  - Coach recommended adding a **`.env.example`** tracked in Git for onboarding
- Positive productivity loop emerging:
  - Transcribe recordings → summarise with ChatGPT → create reference docs
  - Coach mentioned this is “low-hanging fruit” and could even become a small app later
- Pydantic Settings was introduced and adopted:
  - Value: early validation and **explicit errors on import**
  - Avoids cryptic runtime failures caused by bad environment variables
- Current blocker: Airflow DAG running in Docker
  - David created a DAG wrapper, attempted to run it in Docker, hit issues
  - Root cause appears to be **imports / packaging misunderstandings**
  - The `dags/` folder being **outside `src/`** is likely contributing to import pain
  - Coach reiterated: `src/` layout forces proper packaging and avoids these surprises
- Debugging Airflow errors:
  - David wasn’t sure where to find tracebacks/logs
  - Coach guided:
    - Look inside **Docker container logs**
    - Check Airflow UI logs (but logs can be hidden / permissioned)
    - A **403 “forbidden”** appeared when trying to view logs in the UI (can’t read logs)
  - Hypothesis raised: missing/incorrect worker setup or logging configuration
- Design guidance for structure going forward:
  - Move DAGs inside the package (under `src/`)
  - Consider separating:
    - **Airflow orchestration package** (DAGs)
    - **Weather domain package** (client/business logic)
  - Add a test that imports/calls the DAG module to confirm packaging/imports are correct
- Delivery process guidance:
  - Early stages can be exploratory and “messy” (less overhead)
  - Longer term, aim for **smaller, focused PRs**:
    - PR 1: unit-tested weather client logic
    - PR 2: DAG wrapper
    - PR 3: Docker Compose setup
- Follow-up issue workflow in GitHub was taught:
  - From a PR comment → “…” menu → **Reference in new issue**
  - Benefits:
    - Keeps PR scope tight
    - Captures improvement ideas with context
    - Potentially delegatable to AI for quick PR generation
- Additional progress:
  - David created a couple of issues already (e.g., retries w/ exponential backoff)
  - David wrote a blog using **MkDocs Material** and likes the workflow

## Actions to Take Away

### Fix the Current Blocker (Imports / Airflow in Docker)

- [ ] Move `dags/` **inside `src/`** (or into an `airflow_dags` package under `src/`)
- [ ] Split code into clear packages:
  - [ ] `weather_client` (domain logic)
  - [ ] `airflow_dags` (orchestration wrappers)
- [ ] Add/adjust tests to confirm import correctness:
  - [ ] Test that imports the DAG module successfully (package install validation)
- [ ] Re-run Docker Compose and confirm the DAG runs end-to-end

### Improve Logging / Debuggability

- [ ] Learn where Airflow logs appear in your setup:
  - [ ] Docker container logs (scheduler/webserver/worker)
  - [ ] Airflow UI logs (resolve the **403 forbidden** issue if persistent)
- [ ] Capture one failing run and record:
  - [ ] Which container shows the traceback
  - [ ] What the error actually is (import path vs runtime issue)

### Repo Hygiene and Onboarding

- [ ] Add `.env.example` to the repo so others can set required env vars safely
- [ ] Keep `.env` untracked (already done) and stay strict on secret handling

### Workflow and Delivery

- [ ] Aim for **daily PR feedback loop**:
  - [ ] Push progress frequently
  - [ ] Ping coach on Circle if you need a review and it hasn’t landed
- [ ] Start shifting toward **smaller PRs** once exploration settles:
  - [ ] Weather client PR
  - [ ] DAG PR
  - [ ] Docker PR

### GitHub Technique to Use Immediately

- [ ] Use “Reference in new issue” from PR comments whenever:
  - The feedback is useful but not needed now
  - You want to keep the current PR narrow
  - The task is small and potentially “AI-delegatable”

### Personal Learning Focus for the Next Day

- [ ] Refresh understanding of:
  - Python packages vs modules
  - Absolute vs relative imports
  - How `src/` layout affects import behavior
- [ ] Build just enough Docker understanding to debug confidently:
  - Containers involved
  - Where logs live
  - How Airflow executes work (scheduler vs workers)

---