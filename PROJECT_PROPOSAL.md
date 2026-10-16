# SWE301 Assignment 1: Project Proposal and Initial Requirements

## 1. Team information

- **Project title:** Student Study Organizer
- **Group letter:** [TEAM: fill in]
- **Team members:**
  - Shaikhah Nayef Alajmi
  - Deemah Meshal Althaher
  - Renad Adil Alotaibi
- **GitHub repository URL:** https://github.com/justshayo/Student-Study-Organizer
- **Summary:** Student Study Organizer is a small web application that turns a student's course deadlines and estimated effort into a weekly study plan, tracks completed study time, and lets instructors publish deadlines directly to their course.

## 2. Problem and users

## 3. Existing solutions

## 4. Proposed solution and justification

## 5. Scope and workflows

## 6. Initial requirements

### Functional requirements

### Non-functional requirements

## 7. Development approach

We choose an **incremental, Agile-style hybrid**. The overall idea and three workflows are fixed early so we can plan against the semester deadline, but details such as how the plan should be displayed or how effort should be estimated are likely to change after students try early versions. Each increment delivers one workflow end to end: W1 first, then W2, then W3.

We will work in roughly two-week iterations. Each iteration begins with a short planning meeting where we choose requirements from a backlog kept as GitHub Issues, and ends with a demo to at least two outside students and a short retrospective. Because we reuse an existing framework and libraries, much of the work is integration and configuration, and we will test each increment before starting the next. The main risks (changing requirements, an overly complex scheduling rule, limited time) are handled by keeping the algorithm simple and dropping "Should" requirements (FR-06, FR-08) before any "Must" requirement if time runs short.

## 8. Team plan and risks

**Coordinator roles** (all members contribute to every part of the project):

| Role | Member |
|---|---|
| Process and project coordinator | Shaikhah Nayef Alajmi |
| Requirements and design coordinator | Deemah Meshal Althaher |
| Implementation and quality coordinator | Renad Adil Alotaibi |

| Milestone | Main planned output | Coordinator |
|---|---|---|
| 1. Proposal | This document and repository set up | Process and project |
| 2. Requirements and models | Validated requirements, use cases, data model | Requirements and design |
| 3. Design and initial prototype | Architecture, UI sketches, W1 working | Implementation and quality |
| 4. Final prototype, testing, and presentation | W1–W3 working, test report, demo | Process and project |

| Risk | Impact | Planned response |
|---|---|---|
| Requirements change after development starts | High | Review the three workflows with students and one instructor before implementation, and after each increment |
| Scheduling algorithm is too complex or produces unrealistic plans | High | Start with a simple even-spread rule; test with sample cases; refine only if time allows |
| Privacy of student data | Medium | Use only simulated data; hash passwords; document in the README that no real data is stored |
| Interface not accessible to all users | Medium | Use semantic HTML and sufficient colour contrast; check with a browser accessibility checker |
| Uneven contribution or merge conflicts | Medium | Each member uses their own branch and pull requests reviewed by a teammate |

## 9. Sources, AI use, and contributions

### Sources

Each source was opened and read by a team member on [DATE].

1. MyStudyLife, "MyStudyLife for Schools": https://mystudylife.com/schools/
2. MyStudyLife, Chrome Web Store listing: https://chrome.google.com/webstore/detail/my-study-life/mnjdjjiobjicmlhnjlogfgbibihjhkeo/
3. MyStudyLife, App Store listing: https://apps.apple.com/us/app/-/id910639339
4. Doist, "How to Use Todoist Effectively": https://doist.com/blog/how-to-use-todoist-effectively
5. Geekflare, "Todoist Review": https://geekflare.com/software/todoist-review/
6. Our own survey of fellow students about how they currently plan their studying (Section 2 and the "current process" row in Section 3). The notes are kept in the repository: [filename or link].

No external code, images, datasets, or templates were used in this proposal. Flask or Django, SQLite, Bootstrap, and Chart.js are only proposed for later milestones.

### AI use

The instructor permits generative AI. We used **Claude (Anthropic)** in the following ways:

- To search for existing study-planner solutions and suggest MyStudyLife and Todoist as comparison points.
- To produce a first draft of this proposal, including the wording of the requirements, workflows, risks, and development approach.

We chose the project topic (Student Study Organizer) ourselves. We verified and revised the AI output as follows:

- We opened each source listed above and checked that the feature descriptions and limitations in Section 3 match what those pages and apps actually show.
- We tried MyStudyLife and Todoist ourselves to confirm the limitations we describe.
- We replaced the AI's generic description of the current process with the results of our own survey of students.
- We read the whole draft together on [DATE], and changed or removed anything we could not explain or that did not fit our project.
- Every team member can explain every section of this proposal.

### Contributions

All contributions are recorded in the repository's commit history (https://github.com/justshayo/Student-Study-Organizer/commits/main) and pull requests (https://github.com/justshayo/Student-Study-Organizer/pulls).

| Member | Main sections written or revised | Reviewed |
|---|---|---|
| Shaikhah Nayef Alajmi | README, Sections 1, 7, 8, 9 | Section [__] by [member] |
| Deemah Meshal Althaher | Sections 2, 5, 6 (functional requirements) | Section [__] by [member] |
| Renad Adil Alotaibi | Sections 3, 4, 6 (non-functional requirements) | Section [__] by [member] |
