# Sprint 1 Plan

## Project and team

- **Project title:** Student Study Organizer
- **Group:** B
- **Team members:**
  - Shaikhah Nayef Alajmi
  - Deemah Meshal Althaher
  - Renad Adil Alotaibi
- **GitHub Project URL:** https://github.com/users/justshayo/projects/1
- **Sprint dates:** 15 November 2026 – 28 November 2026 (Two weeks)

## Connection to Assignment 1

We derived our 10-issue product backlog directly from `PROJECT_PROPOSAL.md` by breaking down our three core workflows (`W1: Plan study for upcoming deadlines`, `W2: Complete sessions and review progress`, and `W3: Publish a course deadline`), all eight functional requirements (`FR-01` through `FR-08`), all three non-functional requirements (`NFR-01` through `NFR-03`), and our high/medium project risks (Section 8).

Following the milestone roadmap in Section 8 of `PROJECT_PROPOSAL.md` (Milestone 2: *Requirements and models*), we structured the backlog into two layers:
1. **Requirements validation, data modeling, algorithm specification, and UI wireframing (Issues #1–#4):** Actionable specification tasks that mitigate our top risks (changing requirements, scheduling algorithm complexity, simulated data privacy, and interface accessibility) before coding starts.
2. **Incremental implementation and verification (Issues #5–#10):** End-to-end implementation of authentication (`NFR-02`), Workflow 1 (`FR-01`–`FR-04`, `FR-06`, `NFR-01`), Workflow 2 (`FR-05`, `FR-08`), Workflow 3 (`FR-07`), and usability testing (`NFR-03`).

## Sprint goal

Validate the initial requirements for all three workflows with students and an instructor, and produce reviewed specifications for the relational data model, the rule-based scheduling algorithm, and accessible UI wireframes so Workflow 1 implementation can begin cleanly in Sprint 2.

## Selected issues

| Issue | Assignment 1 source | Owner | Expected outcome |
|---|---|---|---|
| [#1](https://github.com/justshayo/Student-Study-Organizer/issues/1) | Section 2, Section 6 (FR-01–FR-08), Section 8 (Risk: Changing requirements) | Renad Adil Alotaibi | Validated requirements and workflow feedback from 3 students and 1 instructor documented in `docs/REQUIREMENTS_VALIDATION.md` |
| [#2](https://github.com/justshayo/Student-Study-Organizer/issues/2) | Section 4, W1–W3, FR-01, FR-02, FR-05, FR-07, Section 8 (Risk: Privacy) | Deemah Meshal Althaher | Relational database schema (ERD and table definitions) and simulated dataset specification documented in `docs/DATA_MODEL.md` |
| [#3](https://github.com/justshayo/Student-Study-Organizer/issues/3) | Workflow 1 (W1), FR-03, FR-06, NFR-01, Section 8 (Risk: Algorithm complexity) | Shaikhah Nayef Alajmi | Rule-based scheduling algorithm specification, overload warning conditions, and 4 worked test cases documented in `docs/SCHEDULING_SPEC.md` |
| [#4](https://github.com/justshayo/Student-Study-Organizer/issues/4) | Workflows W1–W3, FR-04, FR-08, NFR-03, Section 8 (Risk: Accessibility) | Renad Adil Alotaibi | Low-fidelity UI wireframes for all three workflows with semantic HTML and contrast guidelines documented in `docs/UI_WIREFRAMES.md` |

## Workflow rules

- **Maximum issues In Progress at one time:** 2
- **Review policy:** Work must be submitted via a branch and Pull Request and reviewed against its acceptance criteria by at least one other team member before moving from `Review` to `Done`.
- **Evidence policy:** Completed issues must link to concrete evidence in the repository (commits, Pull Requests, and the corresponding Markdown specification files in `docs/`).

## Contribution plan

| Team member | Role (from Assignment 1) | Will lead in Sprint 1 | Will review in Sprint 1 |
|---|---|---|---|
| Shaikhah Nayef Alajmi | Process and project coordinator | Issue [#3](https://github.com/justshayo/Student-Study-Organizer/issues/3) (Scheduling algorithm specification and test cases); repository and GitHub Project configuration | Issue [#1](https://github.com/justshayo/Student-Study-Organizer/issues/1) (Requirements validation) and Issue [#4](https://github.com/justshayo/Student-Study-Organizer/issues/4) (UI wireframes) |
| Deemah Meshal Althaher | Implementation and quality coordinator | Issue [#2](https://github.com/justshayo/Student-Study-Organizer/issues/2) (Database schema and simulated dataset specification) | Issue [#3](https://github.com/justshayo/Student-Study-Organizer/issues/3) (Scheduling algorithm specification and test cases) |
| Renad Adil Alotaibi | Requirements and design coordinator | Issue [#1](https://github.com/justshayo/Student-Study-Organizer/issues/1) (Requirements validation) and Issue [#4](https://github.com/justshayo/Student-Study-Organizer/issues/4) (Accessible UI wireframes for W1–W3) | Issue [#2](https://github.com/justshayo/Student-Study-Organizer/issues/2) (Database schema and simulated dataset specification) |

---