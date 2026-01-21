## Key points

- You’re in the first couple of days at the new job and most of your time has gone into **getting set up** (including a painful laptop/password/IT reset cycle that wiped settings and forced you to start again).
- The company’s stack (from what you’ve seen so far) includes **Atlassian tooling (Jira + Confluence)** and a large **AWS + Redshift** data warehouse.
- They use **Airflow** for orchestration (and there’s already mention internally of **Airflow 3** / migration considerations).
- Discussion on **Airflow vs Prefect**:
  - Prefect is perceived as “easier to run/test locally” and was built by folks with Airflow background.
  - Airflow remains widely used in industry, so learning it is still valuable for your role.
  - Having informed opinions on both tools is useful, but **timing matters** when raising suggestions early in a new job.
- You’ve been doing a **deep(ish) dive into Docker**, including Docker Compose as a way to host/run Airflow and potentially run end-to-end tests.
- There’s value in staying pragmatic: learn what the team uses, observe how they work, then decide where you can add improvement suggestions without overreaching early.

## Actions / takeaways

- **Finish onboarding hardening**
  - Stabilise your machine/setup so you’re not losing time to resets (capture any recurring issues + fixes in notes).
- **Map the team’s workflow**
  - Confirm how they use **Jira ↔ GitHub** (tickets, PRs, linking, branching, review expectations).
  - Identify where Airflow fits in their pipeline lifecycle (deployments, scheduling, monitoring, ownership).
- **Airflow learning with purpose**
  - Note down what you need to be effective quickly (how DAGs are structured, where logs live, how deployments happen).
  - Capture what you hear about **Airflow 3** and the reality of migrating (prereqs, effort, risk).
- **Keep Prefect as “informed context”, not a crusade**
  - Learn enough to compare trade-offs, then be deliberate about *when* (and *how*) you raise alternatives at work.
- **Docker workflow**
  - Keep iterating on your Docker/Docker Compose setup for Airflow so you can reproduce issues and learn faster.
  - Write down a repeatable “runbook” for: start Airflow locally → trigger a run → find logs → debug failures.
- **Create a question list for the team**
  - Bring a short set of high-signal questions (Airflow patterns, environments, observability, data movement, ownership).
- **Document as you go**
  - Continue capturing what you learn (quick notes now; refine later) so you’re building a personal reference you can reuse.