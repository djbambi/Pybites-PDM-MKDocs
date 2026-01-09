## Key Points from the Meeting

- The session is part of the PyBites PDM coaching programme, with a focus on **practical coding over passive learning**.
- Meetings will typically be **2 × 30 minutes per week**, with additional **asynchronous code review (2–3 hours/week)**.
- The primary workflow revolves around **GitHub as the single source of truth**:
  - Issues for tasks
  - A Kanban-style project board (Scrumban)
  - Early and frequent pull requests
- There is a clear separation between:
  - **PDM programme repository** (progress tracking, wins, admin)
  - **Personal code repository** (public-facing, portfolio-quality code)
- The first technical goal is to set up a **clean, production-grade Python repository**:
  - `src/` layout to enforce proper imports
  - `pyproject.toml`
  - `uv` for dependency and Python version management
  - `ruff` for linting and formatting
- Emphasis on **creating pull requests very early**, even with minimal code:
  - Use PRs to ask questions
  - Use draft PRs to signal work-in-progress
- Code-related questions should be asked **inside pull requests**, not chat tools:
  - Inline comments provide full context
  - Reduces cognitive load and back-and-forth explanations
- Self-review is encouraged:
  - First review your own PR
  - Optionally use AI (e.g. Copilot) before requesting human review
- VS Code is the primary IDE:
  - Heavy use of Command Palette (`Cmd + Shift + P`)
  - GitHub Pull Requests extension recommended
- `uv` is recommended over Poetry or Conda for most Python projects:
  - Fast, Rust-based
  - Strong VS Code ecosystem support
  - Conda/Pixi only needed for GPU-heavy or multi-language workflows
- The overall philosophy:
  - Make everything **explicit**
  - Minimise what your brain has to remember
  - Use tooling to externalise state and intent

## Actions to Take Away

### Immediate Actions (Today / Tomorrow)

- [ ] Create a **new personal GitHub repository** for the project (e.g. `airflow-spark-data-pipeline`)
- [ ] Add an **MIT license** to the repository
- [ ] Invite the coach as a collaborator
- [ ] Create an initial GitHub issue:
  - Title: *Set up Python repository structure*
  - Tasks:
    - Add `pyproject.toml`
    - Use `uv` for package management
    - Configure `ruff` for linting and formatting
    - Implement `src/` layout
- [ ] Create a **branch directly from the issue**
- [ ] Add a minimal `pyproject.toml` file
- [ ] Commit and push the change
- [ ] Open a **draft pull request**
- [ ] Assign yourself and the coach as reviewer
- [ ] Perform a **self-review** in the PR, even if the change is minimal

### Short-Term (Before Next Session)

- [ ] Get comfortable with:
  - Creating issues
  - Creating branches from issues
  - Draft vs non-draft PRs
- [ ] Use PR comments to ask at least one **contextual code question**
- [ ] Bookmark:
  - Your repo
  - The PDM GitHub project board
- [ ] Add non-code tasks (videos, code clinics) directly to the project board

### Ongoing Habits to Build

- [ ] Create PRs early and often
- [ ] Ask all code questions inside PRs
- [ ] Keep PR descriptions and comments explicit for future-you
- [ ] Treat GitHub as your **external brain**
- [ ] Focus time on coding; consume videos/podcasts only during low-energy periods

---

Source: Meeting transcription  [oai_citation:0‡meeting_one_transcription_06012026.md](sediment://file_000000001cf071f4aa901f032bc10c8c)