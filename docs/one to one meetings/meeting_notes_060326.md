## Key Points from the Meeting

- You explored **Pulumi** and successfully created an AWS resource (an S3 bucket) in your account.
  - The main insight: Pulumi allows **infrastructure to be written in a real programming language (Python)** rather than a DSL like Terraform.
  - This opens the door to using **software engineering concepts** (e.g., abstract base classes, reusable interfaces) in infrastructure code.
  - Example idea discussed: creating an abstract `Bucket` interface and implementing provider-specific buckets (AWS, GCP, etc.).

- You experimented with **Prefect**:
  - Followed the tutorial and got a simple workflow running.
  - At a high level you understand how flows and tasks work.
  - The remaining step is **spending time understanding the details and internal mechanics**.

- Prefect was discussed as an orchestration option with strong **observability and flexibility**.
  - Flows can be composed with subflows.
  - Removing decorators essentially leaves plain Python functions.
  - Prefect can run locally or with a **local server for observability**, or in the cloud.

- A long-term idea discussed:
  - Deploying your **own Prefect environment in AWS using Pulumi**.
  - This would create an **end-to-end production-style pipeline environment**.

- You are exploring **new data sources** to make your project more realistic.
  - Found UK energy generation mix data (renewables breakdown).
  - Considering correlating it with **weather data**.

- A practical problem emerged:
  - The **OpenWeather API does not provide the hourly granularity you want** without a paid plan.
  - You discovered **Open-Meteo**, which provides **free hourly historical data**.

- This triggered a design consideration:
  - Switching APIs would require rewriting parts of the pipeline.
  - You started exploring the **Repository Pattern** to abstract data sources.
  - Idea:
    - Define a common parent interface for weather data sources.
    - Implement concrete classes for each provider (OpenWeather, Open-Meteo, etc.).
    - Keep the rest of the pipeline unchanged when switching sources.

- You discussed how most APIs share common structure:
  - URL
  - parameters
  - headers
  - authentication
  - response parsing
  - These shared concepts could live in a **base class**.

- The broader theme of the conversation:
  - Move from experimentation to **building a clean, well-structured repository**.
  - Focus on maintainability, testing, and code quality rather than just adding features.

---

## Actions to Take Away

### Infrastructure Exploration

- [ ] Continue experimenting with **Pulumi**.
- [ ] Try defining reusable infrastructure patterns (e.g., bucket abstractions).
- [ ] Consider how infrastructure definitions could become **reusable Python modules**.

---

### Prefect Understanding

- [ ] Spend time understanding Prefect more deeply:
  - flows
  - tasks
  - subflows
  - decorators
  - local server / observability
- [ ] Run Prefect locally with a **local Prefect server** to explore monitoring and orchestration behaviour.

---

### Data Pipeline Design

- [ ] Investigate **Open-Meteo API** as a weather data source.
- [ ] Evaluate how its response structure differs from OpenWeather.

- [ ] Implement a **Repository Pattern** for weather data sources:
  - Create a base interface describing common behaviour.
  - Implement provider-specific repositories (OpenWeather, Open-Meteo).

- [ ] Identify the **common API components**:
  - base URL
  - parameters
  - headers
  - authentication
  - response parsing

---

### Project Direction

- [ ] Combine **weather data with UK energy generation data**.
- [ ] Explore correlations (e.g., temperature vs renewable generation mix).

- [ ] Continue moving toward a **clean production-style repository** with:
  - clear architecture
  - testing
  - code quality checks
  - reusable components

---

### Long-Term Direction

- [ ] Consider building a **full end-to-end pipeline**:
  - data ingestion
  - orchestration with Prefect
  - infrastructure managed with Pulumi
  - observability via Prefect UI
- [ ] Aim for a project that demonstrates **production-grade data engineering practices**.

---