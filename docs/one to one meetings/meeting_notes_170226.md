# Meeting Notes – 17 February 2026

## Summary

Robin is currently working in Munich during the week and returning to Berlin at weekends. The session opened with a discussion about AI tooling limits before moving into a detailed review of David's Airflow work. David has built a solid local Airflow setup using the **Astro CLI** and **MinIO**, culminating in a working OpenWeather data pipeline. Feeling comfortable with Airflow, the conversation shifted to where to go next — the agreement was to deepen Python fundamentals, specifically around **Abstract Base Classes (ABCs)**, design patterns (the **Repository Pattern**), typed code, and profiling. A concrete homework task was agreed: implement an abstract `WeatherDataTransformer` class with concrete implementations in Pandas, Polars, and (optionally) NumPy. Decorators were also flagged as a topic David hasn't implemented himself yet. Next meeting scheduled for **Friday 20th February at 09:00 (David's time) / 08:00 (Robin's time)**.

---

## Key Points

### AI Tooling
- David has hit his **GitHub Copilot premium token limit** and is temporarily without it.
- Options discussed:
  - Upgrade to the next paid tier (expensive).
  - Use **multiple basic-tier tools** (e.g. Copilot + Cursor + Claude at ~€20 each) to spread usage — cheaper than one high tier.
  - Company licenses are another route — Robin's company has access to Cursor, Claude, and Copilot at basic tier.
- Limits are sometimes **temporary hourly blocks** rather than permanent caps.
- Consider using **lighter/cheaper models** (e.g. Sonnet instead of Opus) for simpler tasks to conserve credits.

### Airflow Deep Dive
- David used the **Astro CLI** (by Astronomer) to scaffold and run a local Airflow project — analogous to `uv` for project setup.
  - Standard folder structure: `dags/` for DAGs, `include/` for helper/business logic.
  - Runs everything in **Docker**.
- Key principle reinforced: **DAGs orchestrate; they don't do heavy lifting.** Business logic belongs in helper modules under `include/`.
- David built two pipelines: a stock market example (course) and an **OpenWeather pipeline** (his own), storing results as JSON files in **MinIO** (a local S3-compatible store).
- Compared to his workplace's Airflow setup:
  - Work uses a plain repository of DAGs, no tests, deployed to **S3 via TeamCity CI/CD**.
  - Airflow in AWS reads DAGs directly from the S3 bucket.
  - Work uses Airflow **Connections** (hooks) to manage credentials without hardcoding them.
- David's local setup is **more sophisticated than work's**.

### Direction Going Forward — Deeper Python
- The "breadth-first" phase is largely complete. Time to go **depth-first**.
- Topics agreed to focus on:
  1. **Abstract Base Classes (ABCs)** — defining interfaces and enforcing them via concrete implementations.
  2. **Repository Pattern** — implement it once to understand when it's useful.
  3. **Typing** — continue building stronger type annotations.
  4. **Advanced fixtures / pytest** — go deeper on test design.
  5. **Decorators** — David has *used* them (DAGs, pytest) but never *implemented* one himself.
  6. **Profiling** — measuring CPU time (easier) vs. memory (harder); tools like `cProfile` and others.

### ABCs — Design Discussion
- Plan: create an abstract `WeatherDataSource` (load/pre-process) and an abstract `WeatherDataTransformer` (e.g. `get_mean_daily_temperature`).
- Concrete implementations of the transformer:
  - **PandasWeatherDataTransformer** — uses a DataFrame.
  - **PolarsWeatherDataTransformer** — similar API, subtly different.
  - **NumpyWeatherDataTransformer** — array-based, requires manual iteration; most different from the others.
- The value: consumers interact with a **stable interface** without needing to know the underlying implementation. Easy to swap sources/backends.
- Pandas may have an edge for **easy plotting**; NumPy for **vectorised performance**; Polars for **speed at scale**.
- Profiling could be added to compare the implementations meaningfully.

### Decorators
- Classic use case: a **timing decorator** to measure how long a function takes.
- Can be implemented as a function decorator or a class decorator.
- Flagged as a good self-contained exercise to understand decorators before they come up naturally in larger code.

---

## Actions / Homework

- **Sort out Copilot access**
  - Decide whether to upgrade personal tier, use multiple basic-tier tools, or request company license.
  - Robin offered to help debug/unblock this if needed.

- **Read about Abstract Base Classes**
  - Start with the Python docs: `abc` module (`ABC`, `abstractmethod`).
  - Spend ~30 minutes to get a solid conceptual understanding before implementing.

- **Read about the Repository Pattern**
  - Keep it brief — 30 minutes max to understand the concept and when it's useful.

- **Implement `WeatherDataTransformer` ABC + concrete classes**
  - Define an abstract base class with at least one abstract method (e.g. `get_mean_daily_temperature`).
  - Implement at least two concrete versions:
    - `PandasWeatherDataTransformer`
    - `PolarsWeatherDataTransformer`
  - Optionally add a `NumpyWeatherDataTransformer` for contrast.
  - Use the existing OpenWeather pipeline data as input.

- **Implement a timing decorator**
  - Write a decorator from scratch that wraps a function and logs/prints its execution time.
  - Try both a function-based and a class-based version if time allows.

- **Next meeting: Friday 20 February at 09:00 David's time / 08:00 Robin's time**
