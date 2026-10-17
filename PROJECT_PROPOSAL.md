# SWE301 Assignment 1: Project Proposal and Initial Requirements

## 1. Team information

- **Project title:** Student Study Organizer
- **Group letter:** B
- **Team members:**
  - Shaikhah Nayef Alajmi
  - Deemah Meshal Althaher
  - Renad Adil Alotaibi
- **GitHub repository URL:** https://github.com/justshayo/Student-Study-Organizer
- **Summary:** Student Study Organizer is a small web application that turns a student's course deadlines and estimated effort into a weekly study plan, tracks completed study time, and lets instructors publish deadlines directly to their course.

## 2. Problem and users

## 3. Existing solutions

We compared our current way of planning study with two existing applications, MyStudyLife and Todoist, to identify their useful features and their limitations for university students.

| Existing process or solution | Useful features | Limitation for our users | Source |
|---|---|---|---|
| Current process (notes app, phone calendar, paper planner) | Free, familiar, and flexible | Deadlines are entered manually from several sources; there is no overview of workload and no suggestion of when to study; study time is not recorded | [] |
| MyStudyLife | Organizes classes, homework, and exams in one place; provides reminders, revision tasks, and personal study statistics | Study and revision tasks must be created manually. Our initial comparison did not show automatic workload warnings or instructor-published deadlines [TEAM: after testing, state what you actually found.] | https://mystudylife.com/schools/ ; https://chrome.google.com/webstore/detail/my-study-life/mnjdjjiobjicmlhnjlogfgbibihjhkeo/ ; https://apps.apple.com/us/app/-/id910639339 |
| Todoist | Supports quick task creation, due dates, recurring tasks, priorities, projects, and productivity reports | It is a general-purpose task manager with no focus on courses, exams, or estimated study effort. Its reports show general productivity rather than planned versus actual study time. [TEAM: after testing, state whether it generates a study plan automatically.] | https://doist.com/blog/how-to-use-todoist-effectively ; https://geekflare.com/software/todoist-review/ |

**Testing plan:** We will test both applications with sample academic tasks. In MyStudyLife we will examine classes, deadlines, reminders, and revision tasks. In Todoist we will examine task creation, due dates, priorities, recurring tasks, and reports. In both we will check whether study sessions are scheduled automatically from estimated effort and whether the system warns students about an unrealistic workload. [TEAM: once the testing is done, replace this paragraph with "We tested..." and a short summary of the results.]

**What we learned:** Both applications offer useful task management and planning features, so we should not rebuild a general planner. The gap we identified is narrower: automatically converting deadlines and estimated effort into a realistic daily study plan, warning students about workload problems, and letting instructors publish deadlines directly into student plans. We are not claiming that no solution exists, and we will confirm these findings through testing.

## 4. Proposed solution and justification

The Student Study Organizer is a web application that helps university students manage their academic tasks and organize their study time. Students register courses and add assignments, exams, and readings with a due date, estimated effort in hours, and priority. They also set a maximum number of study hours per day.

The system generates suggested study sessions by spreading the remaining effort across the available days before each deadline, and shows them in a weekly view. Students mark sessions as complete and record the actual time spent. If the plan is unrealistic because a day exceeds the study-hour limit or a task cannot fit before its deadline, the system warns the student. It also shows a weekly summary of planned versus completed hours. Instructors can publish assignment and exam deadlines to a course so that enrolled students receive them automatically as tasks.

**How it improves the current process:** it reduces manual deadline entry, makes upcoming workload visible before it becomes a problem, and records actual study time.

**How it addresses limitations found in existing solutions:** compared with MyStudyLife and Todoist, our project focuses on automatic study-plan generation, workload warnings, and deadlines published by instructors.

**Why three students can complete a prototype:**

- The scheduling uses a simple rule-based algorithm (spread the remaining hours evenly across available days), not machine learning.
- The data model is small: users, courses, tasks, and study sessions.
- The prototype is limited to three workflows: plan study, complete sessions and review progress, and publish a course deadline.
- All data is simulated, so no real student information is needed.

**Components we may reuse:** a web framework (Flask or Django), SQLite for storage, the framework's built-in authentication, Bootstrap for the interface, and optionally Chart.js for the weekly progress chart.

## 5. Scope and workflows

## 6. Initial requirements

### Functional requirements

### Non-functional requirements

| ID | Category | Measurable requirement |
|---|---|---|
| NFR-01 | Performance | The system shall generate a study plan for up to 20 tasks within 3 seconds on the demonstration dataset. |
| NFR-02 | Security and privacy | The system shall store passwords only as salted hashes, and automated tests shall confirm that a student account receives an access-denied response for 100% of requests for another student's data. |
| NFR-03 | Usability | At least 4 of 5 first-time test users shall add a course and a task and generate a study plan without assistance within 5 minutes. |

These are initial requirements and will be validated and expanded in the requirements milestone.

## 7. Development approach

We choose an **incremental, Agile-style hybrid**. The overall idea and three workflows are fixed early so we can plan against the semester deadline, but details such as how the plan should be displayed or how effort should be estimated are likely to change after students try early versions. Each increment delivers one workflow end to end: W1 first, then W2, then W3.

We will work in roughly two-week iterations. Each iteration begins with a short planning meeting where we choose requirements from a backlog kept as GitHub Issues, and ends with a demo to at least two outside students and a short retrospective. Because we reuse an existing framework and libraries, much of the work is integration and configuration, and we will test each increment before starting the next. The main risks (changing requirements, an overly complex scheduling rule, limited time) are handled by keeping the algorithm simple and dropping "Should" requirements (FR-06, FR-08) before any "Must" requirement if time runs short.

## 8. Team plan and risks

**Coordinator roles** (all members contribute to every part of the project):

| Role | Member |
|---|---|
| Process and project coordinator | Shaikhah Nayef Alajmi |
| Requirements and design coordinator | Renad Adil Alotaibi |
| Implementation and quality coordinator | Deemah Meshal Althaher |

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

Each source was opened and read by a team member on 16 October 2026.

1. MyStudyLife, "MyStudyLife for Schools": https://mystudylife.com/schools/
2. MyStudyLife, Chrome Web Store listing: https://chrome.google.com/webstore/detail/my-study-life/mnjdjjiobjicmlhnjlogfgbibihjhkeo/
3. MyStudyLife, App Store listing: https://apps.apple.com/us/app/-/id910639339
4. Doist, "How to Use Todoist Effectively": https://doist.com/blog/how-to-use-todoist-effectively
5. Geekflare, "Todoist Review": https://geekflare.com/software/todoist-review/
6. Our own online interviews with fellow students about how they currently plan their studying (Section 2 and the current-process row in Section 3). The anonymised notes are in `survey_notes.md`.

No external code, images, datasets, or templates were used in this proposal. Flask or Django, SQLite, Bootstrap, and Chart.js are only proposed for later milestones.

### AI use

The instructor permits generative AI. We used **Claude (Anthropic)** in the following ways:

- To search for existing study-planner solutions and suggest MyStudyLife and Todoist as comparison points.
- To produce a first draft of this proposal, including the wording of the requirements, workflows, risks, and development approach.

We chose the project topic (Student Study Organizer) ourselves. We verified and revised the AI output as follows:

- We opened each source listed above and checked that the feature descriptions and limitations in Section 3 match what those pages and apps actually show.
- We tried MyStudyLife and Todoist ourselves to confirm the limitations we describe.
- We replaced the AI's generic description of the current process with the results of our own online interviews with students.
- We read the whole draft together on 17 October 2026, and changed or removed anything we could not explain or that did not fit our project.
- Every team member can explain every section of this proposal.

### Contributions

All contributions are recorded in the repository's commit history (https://github.com/justshayo/Student-Study-Organizer/commits/main) and pull requests (https://github.com/justshayo/Student-Study-Organizer/pulls).

| Member | Main sections written or revised | Reviewed by |
|---|---|---|
| Shaikhah Nayef Alajmi | README, Sections 1, 7, 8, 9 | Shaikhah Nayef Alajmi (self-review) |
| Renad Adil Alotaibi | Sections 2, 5, 6 (functional requirements) | Shaikhah Nayef Alajmi |
| Deemah Meshal Althaher | Sections 3, 4, 6 (non-functional requirements) | Shaikhah Nayef Alajmi |

> **Note on contributions:** Shaikhah Nayef Alajmi reviewed all sections and is responsible for maintaining the repository. **Renad and Deemah wrote their sections outside GitHub and Shaikhah committed them to the repository.**
