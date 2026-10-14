# SWE301 Assignment 1: Project Proposal and Initial Requirements

## 1. Team information

- **Project title:** Student Study Organizer
- **Group letter:** B
- **Team members:**
  - [Member A full name]
  - [Member B full name]
  - [Member C full name]
- **GitHub repository URL:** [TEAM: paste URL]
- **Summary:** Student Study Organizer is a small web application that turns a student's course deadlines and estimated effort into a weekly study plan, tracks completed study time, and lets instructors publish deadlines directly to their course.

## 2. Problem and users

> **[TEAM: replace the "current process" description below with what you actually observe. Interview or survey at least 3 students (and ideally one instructor), and write what they really said. Do not invent results.]**

University students typically receive deadlines from several places: syllabi, a learning platform, announcements, and class messages. They then record them in a notes app, a phone calendar, or a paper planner. Deciding *when* to study is done in their head. Common failure points are deadlines that are missed or entered late, several assignments and exams clustering in the same week without the student noticing until it is too late, and no record of how much time was actually spent, so students cannot see whether their plan is realistic.

The problem is experienced by students, especially those taking four or more courses, and indirectly by instructors, who see late or rushed submissions and have no easy way to make a deadline appear in each student's own planner. It matters because poor planning leads to last-minute cramming, stress, and lower-quality work.

The main actors are:

1. **Student** – enters courses and tasks, views the study plan, and logs study time.
2. **Instructor** – publishes assignment and exam deadlines to a course.

## 3. Existing solutions

| Existing process or solution | Useful features | Limitation for our users | Source |
|---|---|---|---|
| Current process (notes app, phone calendar, paper planner) | Free; familiar; flexible | Deadlines entered manually from multiple sources; no workload overview; no suggestion of when to study; no study-time history | [TEAM: cite your own interviews/survey, with dates] |
| MyStudyLife | Classes, homework, and exams in one calendar; reminders; revision tasks for exams; personal study statistics; free for students | Study and revision tasks are created manually by the student; focus is on personal tracking, with sharing aimed at timetables and parents rather than instructor-published deadlines (per its listings); we found no automatic workload warning (team should verify by testing the app) | https://mystudylife.com/schools/ ; https://chrome.google.com/webstore/detail/my-study-life/mnjdjjiobjicmlhnjlogfgbibihjhkeo/ ; https://apps.apple.com/us/app/-/id910639339 |
| Todoist | Fast task capture, due dates and recurring tasks, priorities, projects, productivity reports | General-purpose to-do tool with no concept of courses, exams, or estimated study effort; reporting is mostly personal Karma scores rather than study-time analysis | https://doist.com/blog/how-to-use-todoist-effectively ; https://geekflare.com/software/todoist-review/ |

**What we learned:** Task lists, due dates, reminders, and progress statistics are already well covered, so we should not try to rebuild a general planner. The gap we found is narrower: automatically converting deadlines plus estimated effort into a realistic day-by-day plan with an overload warning, and letting instructors push deadlines into student plans. We are not claiming that no solution exists; both tools above partly address the problem.

## 4. Proposed solution and justification

The system lets a student register courses, add tasks (assignments, exams, readings) with a due date, estimated effort in hours, and priority, and set a maximum number of study hours per day. It then generates suggested study sessions spread across the days before each deadline and shows them in a weekly view. The student marks sessions complete and logs actual time. If the plan is unrealistic (a day exceeds the limit or a task cannot fit before its deadline), the system warns the student. Instructors can publish a deadline to a course so that enrolled students receive it as a task automatically.

This improves the current process by removing manual re-entry of deadlines, making workload visible before it becomes a crisis, and providing a record of actual study time. Compared with MyStudyLife and Todoist, it focuses on automatic plan generation and instructor-published deadlines.

Three students can complete a small prototype because the scheduling uses a simple rule-based algorithm (spread remaining effort evenly across available days), not machine learning. The data model is small (users, courses, tasks, sessions). We plan to reuse a web framework (e.g. Flask or Django), SQLite, a built-in authentication library, Bootstrap for the interface, and optionally Chart.js for the progress chart. All data used will be simulated.

## 5. Scope and workflows

| In scope (semester prototype) | Out of scope (not attempted) |
|---|---|
| Student and instructor login | University single sign-on or learning-platform integration |
| Course and task management | Mobile app |
| Rule-based study plan generation | AI or machine-learning recommendations |
| Weekly plan view | Syncing with external calendars (Google, Outlook) |
| Logging study time and weekly summary | Push notifications, email reminders |
| Overload warnings | Group study features and chat |
| Instructor publishing deadlines to a course | Grading or grade tracking |
| Simulated demonstration data | Real student data |

| Workflow | Main actor and goal | Expected outcome |
|---|---|---|
| W1: Plan study for upcoming deadlines | A student adds courses and tasks with due dates and estimated hours and generates a study plan | A weekly plan of study sessions is saved and displayed, with warnings if it is unrealistic |
| W2: Complete sessions and review progress | A student marks sessions complete, logs actual time, and reviews a weekly summary | Completed sessions and hours are recorded and the planned vs actual summary is shown |
| W3: Publish a course deadline | An instructor publishes an assignment or exam deadline to a course | Enrolled students see the deadline as a task in their organizer |

## 6. Initial requirements

### Functional requirements

| ID | Functional requirement | Priority |
|---|---|---|
| FR-01 | The system shall allow an authenticated student to create, edit, and delete courses. | Must |
| FR-02 | The system shall allow an authenticated student to add a task with a course, title, due date, estimated effort in hours, and priority. | Must |
| FR-03 | The system shall generate study sessions for each task between the current date and its due date without exceeding the student's configured daily study-hour limit. | Must |
| FR-04 | The system shall display the student's study sessions and deadlines in a weekly view. | Must |
| FR-05 | The system shall allow a student to mark a study session as complete and record the actual time spent. | Must |
| FR-06 | The system shall warn the student when a task cannot be scheduled within the daily limit before its due date. | Should |
| FR-07 | The system shall allow an instructor to publish a deadline to a course so that it appears as a task for each enrolled student. | Must |
| FR-08 | The system shall display a weekly summary of planned hours versus completed hours for the student. | Should |

### Non-functional requirements

| ID | Category | Measurable requirement |
|---|---|---|
| NFR-01 | Performance | The system shall generate a study plan for up to 20 tasks within 3 seconds on the demonstration dataset. |
| NFR-02 | Security and privacy | The system shall store passwords only as salted hashes, and automated tests shall confirm that a student account receives an access-denied response for 100% of requests for another student's data. |
| NFR-03 | Usability | At least 4 of 5 first-time test users shall add a course and a task and generate a plan without assistance within 5 minutes. |

These are initial requirements and will be validated and expanded in the requirements milestone.

## 7. Development approach

We choose an **incremental, Agile-style hybrid**. The overall idea and three workflows are fixed early so we can plan against the semester deadline, but details such as how the plan should be displayed or how effort should be estimated are likely to change after students try early versions. Each increment delivers one workflow end to end: W1 first, then W2, then W3.

We will work in roughly two-week iterations. Each iteration begins with a short planning meeting where we choose requirements from a backlog kept as GitHub Issues, and ends with a demo to at least two outside students and a short retrospective. Because we reuse an existing framework and libraries, much of the work is integration and configuration, and we will test each increment before starting the next. The main risks (changing requirements, an overly complex scheduling rule, limited time) are handled by keeping the algorithm simple and dropping "Should" requirements (FR-06, FR-08) before any "Must" requirement if time runs short.

## 8. Team plan and risks

**Coordinator roles** (all members contribute to every part of the project):

| Role | Member |
|---|---|
| Process and project coordinator | [Member A] |
| Requirements and design coordinator | [Member B] |
| Implementation and quality coordinator | [Member C] |

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

**Sources**

1. MyStudyLife for Schools: https://mystudylife.com/schools/
2. MyStudyLife Chrome Web Store listing: https://chrome.google.com/webstore/detail/my-study-life/mnjdjjiobjicmlhnjlogfgbibihjhkeo/
3. MyStudyLife App Store listing: https://apps.apple.com/us/app/-/id910639339
4. Doist, "How to Use Todoist Effectively": https://doist.com/blog/how-to-use-todoist-effectively
5. Geekflare, Todoist review: https://geekflare.com/software/todoist-review/
6. [TEAM: add your own interview/survey notes and any other source]

**AI use**

- **Tool:** Claude (Anthropic).
- **How it was used:** To search for existing solutions and draft the first version of this proposal.
- **Verification and revision:** [TEAM: describe what you actually did, for example: "We opened each source, tried both apps ourselves, checked each limitation claim, replaced the current-process section with our survey results, and edited the requirements in a group meeting on DATE."]

**Contributions**

Each member contributed through separate commits and pull requests visible in the repository history. [TEAM: list who wrote or revised which section, matching the real commit history.]
