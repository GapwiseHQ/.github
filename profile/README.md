<div align="center">

<img src="./assets/logo-mark.svg" width="116" alt="Gapwise" />

# Gapwise

### Free and open-source university timetable, campus navigation, and campus data infrastructure for students across Canada.

**Privacy-first timetable intelligence, campus maps, and day planning in one application for multiple universities.**

[![Open Gapwise](https://img.shields.io/badge/Open_Gapwise-gapwise.ca-4EA7FE?style=for-the-badge&labelColor=111820)](https://gapwise.ca)
[![Documentation](https://img.shields.io/badge/Docs-docs.gapwise.ca-4EA7FE?style=for-the-badge&labelColor=111820)](https://docs.gapwise.ca)
[![Status](https://img.shields.io/badge/Status-status.gapwise.ca-4EA7FE?style=for-the-badge&labelColor=111820)](https://status.gapwise.ca)

<br />

**[Gapwise](https://gapwise.ca)** · **[Android](https://github.com/GapwiseHQ/android)** · **[iOS](https://github.com/GapwiseHQ/ios)** · **[AI](https://ai.gapwise.ca)** · **[Data](https://data.gapwise.ca)** · **[Docs](https://docs.gapwise.ca)** · **[CLI](https://github.com/GapwiseHQ/cli)** · **[Status](https://status.gapwise.ca)**

<br />

**Local-first · deterministic where correctness matters · explicit about trust boundaries**

</div>

---

Gapwise turns a university timetable into a model of the day around it: **what is next, how much usable time exists between classes, where a student can realistically go, when they need to leave, and how certain the underlying campus information is.**

Gapwise supports **13 universities across 15 campus models** in Canada from one canonical web application:

| University | Edition | Scope | Timetable Source |
| --- | --- | --- | --- |
| **University of Toronto** | [gapwise.ca](https://gapwise.ca) | Mississauga, St. George, Scarborough | ACORN calendar export (`.ics`) |
| **Carleton University** | [carleton.gapwise.ca](https://carleton.gapwise.ca) | Ottawa campus | Carleton Central schedule text & `.ics` |
| **Toronto Metropolitan University** | [tmu.gapwise.ca](https://tmu.gapwise.ca) | Downtown Toronto campus | MyServiceHub (RAMSS) & Google Calendar |
| **Queen's University** | [queens.gapwise.ca](https://queens.gapwise.ca) | Kingston campus | SOLUS Student Center subscription & text |
| **Wilfrid Laurier University** | [laurier.gapwise.ca](https://laurier.gapwise.ca) | Waterloo campus | LORIS Detail Schedule & MyLS |
| **York University** | [york.gapwise.ca](https://york.gapwise.ca) | Keele campus | VSB / REM timetable & `.ics` |
| **McMaster University** | [mcmaster.gapwise.ca](https://mcmaster.gapwise.ca) | Hamilton campus | Mosaic Timetable & Outlook Calendar |
| **Western University** | [western.gapwise.ca](https://western.gapwise.ca) | London campus | Student Center schedule text & `.ics` |
| **University of Guelph** | [guelph.gapwise.ca](https://guelph.gapwise.ca) | Guelph campus | WebAdvisor schedule text & `.ics` |
| **University of Ottawa** | [uottawa.gapwise.ca](https://uottawa.gapwise.ca) | Downtown Ottawa campus | uoCampus schedule text & `.ics` |
| **Brock University** | [brock.gapwise.ca](https://brock.gapwise.ca) | St. Catharines campus | BrockDB / Student Portal text & `.ics` |
| **University of British Columbia** | [ubc.gapwise.ca](https://ubc.gapwise.ca) | Vancouver / Point Grey campus | Workday View My Courses table |
| **University of Waterloo** | [waterloo.gapwise.ca](https://waterloo.gapwise.ca) | Main campus | Quest Class Schedule list view |

Each university provides its own timetable adapter, campus data model, and branding configuration. The shared application, pedestrian routing, gap planner, and UI are not duplicated.

The web campus explorer includes source-backed building identities and footprints for all 13 supported universities. Pedestrian routing is available across all 15 campus models, with provenance and accessibility certainty preserved per campus.

Timetable files are parsed locally in the browser. Arithmetic, routing, travel time, gap budgets, destination feasibility, and leave-by calculations are deterministic rather than delegated to a language model.

## The ecosystem

| Repository | Owns | Surface |
| --- | --- | --- |
| **[`gapwise`](https://github.com/GapwiseHQ/gapwise)** | Core web/PWA, canonical timetable/gap/routing semantics, public API, OpenAPI, and SDK source | [gapwise.ca](https://gapwise.ca) · [api.gapwise.ca](https://api.gapwise.ca/v1) |
| **[`android`](https://github.com/GapwiseHQ/android)** | Native Kotlin + Jetpack Compose Android implementation and Android integration | Android |
| **[`ios`](https://github.com/GapwiseHQ/ios)** | Native Swift + SwiftUI iOS implementation and Apple-platform integration | iOS |
| **[`ai`](https://github.com/GapwiseHQ/ai)** | OAuth/MCP boundary for explicitly delegated student context and bounded AI actions | [ai.gapwise.ca](https://ai.gapwise.ca) |
| **[`data`](https://github.com/GapwiseHQ/data)** | Canonical public campus data, provenance, schemas, validation, and distribution | [data.gapwise.ca](https://data.gapwise.ca) |
| **[`cli`](https://github.com/GapwiseHQ/cli)** | Public campus discovery and queries, plus university scaffolding and validation | [CLI guide](https://docs.gapwise.ca/cli/) |
| **[`docs`](https://github.com/GapwiseHQ/docs)** | Public developer documentation for APIs, SDKs, data, security, native integration, and AI/MCP | [docs.gapwise.ca](https://docs.gapwise.ca) |
| **[`status`](https://github.com/GapwiseHQ/status)** | Independent service-health monitoring and incident communication | [status.gapwise.ca](https://status.gapwise.ca) |

Organization-wide contribution, security, support, and issue defaults live in **[`.github`](https://github.com/GapwiseHQ/.github)**.

### One source of truth per responsibility

```mermaid
flowchart LR
    U[Student] --> W[Web / PWA]
    U --> A1[Android]
    U --> I[iOS]
    U -. optional delegation .-> AI[AI / MCP]

    W --> C[Deterministic Gapwise core]
    A1 --> C
    I --> C
    AI --> C

    C --> D[Canonical multi-university campus data]
    AI --> D

    DOCS[Documentation] -. describes .-> C
    DOCS -. describes .-> D
    STATUS[Status] -. observes .-> W
    STATUS -. observes .-> AI
```

**`gapwise` owns deterministic student-day semantics and the single web application. `data` owns shared public campus facts. `cli` scaffolds integrations. `docs` documents released contracts. `status` observes public services. `android` and `ios` adapt canonical behavior to their platforms. `ai` consumes bounded context; it does not become a second timetable or routing engine.**

## Engineering principles

| | Principle | What it means |
| --- | --- | --- |
| **01** | **Privacy first** | Collect, transmit, and retain less student information. Keep trust boundaries narrow and explicit. |
| **02** | **Deterministic core** | Schedules, routes, durations, feasibility, and leave-by timing must be reproducible. |
| **03** | **Canonical facts** | Shared campus information has one owner, with provenance and visible uncertainty. |
| **04** | **Local where practical** | Keep useful functionality available without unnecessary network dependencies. |
| **05** | **Interfaces consume truth** | Web, Android, iOS, APIs, and AI should not silently recreate domain behavior. |
| **06** | **Scope stays honest** | All-campus timetable support does not imply all-campus map or routing coverage. |
| **07** | **Useful over complicated** | Architecture exists to improve a student's day, not to make the diagram larger. |

## Developer surfaces

- **API:** [`api.gapwise.ca/v1`](https://api.gapwise.ca/v1)
- **OpenAPI:** [`api.gapwise.ca/openapi.json`](https://api.gapwise.ca/openapi.json)
- **Documentation:** [`docs.gapwise.ca`](https://docs.gapwise.ca)
- **Campus data:** [`data.gapwise.ca`](https://data.gapwise.ca)
- **AI / MCP:** [`ai.gapwise.ca`](https://ai.gapwise.ca)
- **JavaScript / TypeScript SDK:** `@gapwise/sdk`
- **Python SDK:** `gapwise`
- **Security:** [`security@gapwise.ca`](mailto:security@gapwise.ca)
- **Support:** [`support@gapwise.ca`](mailto:support@gapwise.ca)

## Contributing

Choose the repository that owns the behavior you want to change. Shared contribution, security, support, and pull-request guidance lives in this organization's [`.github`](https://github.com/GapwiseHQ/.github) repository and is inherited by repositories that do not provide a more specific policy.

Campus facts and routing evidence belong in **[`data`](https://github.com/GapwiseHQ/data)**. Product behavior belongs in **[`gapwise`](https://github.com/GapwiseHQ/gapwise)**. Android-specific implementation belongs in **[`android`](https://github.com/GapwiseHQ/android)**. iOS-specific implementation belongs in **[`ios`](https://github.com/GapwiseHQ/ios)**. Public documentation belongs in **[`docs`](https://github.com/GapwiseHQ/docs)**. Keep changes focused and preserve the source-of-truth boundary.

---

<div align="center">

**Independent student software. Not affiliated with, endorsed by, or an official service of any supported university.**

<br />

**Built for the spaces between classes.**

</div>
