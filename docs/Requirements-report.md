---
title: "AI-Based Question Paper Generator (AIQPG) — Requirements Report"
---

# AI-BASED QUESTION PAPER GENERATOR (AIQPG)
## Software Requirements / Requirements Report

**Document ID:** AIQPG-RR-v1.0
**Project Type:** SDLC / Software Engineering Academic Project
**Document Version:** 1.0
**Prepared as part of academic coursework (Software Engineering / SDLC)**

---

## 1. Introduction

### 1.1 Project Title
AI-Based Question Paper Generator (AIQPG)

### 1.2 Purpose
The AI-Based Question Paper Generator is a web-based application designed to give faculty and academic administrators a structured, auditable, and time-efficient way to assemble examination question papers from a maintained question bank, using AI/NLP techniques for question generation, intelligent selection, difficulty balancing, and duplicate avoidance. The portal supports question-bank management, parameterized paper configuration, AI-assisted authoring, manual review and regeneration, paper history/versioning, and export to distribution-ready formats — while keeping human faculty as the final authority over every published paper.

### 1.3 Problem Statement
Most departments still rely on ad-hoc methods — faculty typing papers individually in Word, emailing drafts for review, or reusing old papers with minor edits — to produce examination question papers. This creates the following problems:

- Lack of a centralized, searchable repository for exam questions across subjects and topics.
- Time-consuming manual selection of questions that meet marks, duration, and difficulty targets.
- Inconsistent difficulty distribution and topic coverage across sections.
- Accidental repetition of questions used in recent papers, weakening exam integrity.
- No structured tagging of questions by topic, difficulty, or cognitive level (e.g., Bloom's Taxonomy).
- Difficulty tracking which paper version was finalized, by whom, and when.
- Weak confidentiality controls around draft papers before the exam date.
- Difficulty scaling the process as the number of subjects, sections, and question banks grows.
- No easy way to regenerate or swap a single flawed question without redoing the whole paper.
- Limited visibility for coordinators/administrators into paper status before distribution.

Therefore, a centralized AI-Based Question Paper Generator is proposed to reduce faculty workload, improve consistency and topic/difficulty balance, safeguard exam confidentiality, and provide an auditable history of every generated paper.

### 1.4 Proposed Solution
The proposed system uses AI/NLP techniques to automatically generate and/or intelligently select questions from a maintained question bank, based on user-defined parameters such as subject, total marks, duration, number of sections, topic coverage, and difficulty distribution. Faculty can review, edit, replace, or regenerate individual questions before finalizing a paper, and export the finished paper to PDF/Word. AI-generated or AI-selected content is always advisory; final approval and accountability remain with the faculty member.

### 1.5 Intended Audience
This document is intended for the course instructor/evaluator, the project development team, and any future contributors extending the system.

---

## 2. Objectives

- Provide faculty with a simple, secure platform to build and manage a question bank.
- Tag every question by subject, topic, difficulty level, and cognitive (Bloom's) level.
- Allow faculty to configure paper parameters (marks, duration, sections, difficulty mix, topic coverage).
- Use AI to generate new questions and/or intelligently select existing ones matching those parameters.
- Detect and prevent duplicate questions within a paper and across recently generated papers.
- Allow manual review, editing, replacement, and regeneration of individual questions before finalizing.
- Assign each generated paper a unique paper reference ID and maintain version history.
- Route papers through an optional coordinator review/approval step before finalization.
- Export finalized papers to PDF/Word in a clean, exam-ready layout.
- Maintain a tamper-evident audit trail and history log of all generated and finalized papers.
- Provide dashboards for faculty, coordinators, and administrators to track question-bank health and paper status.
- Enforce role-based access and confidentiality so draft/finalized papers are visible only to authorized users.
- Notify faculty and coordinators of key events (paper ready for review, insufficient questions, approval needed).
- Improve consistency, fairness, and exam-integrity posture across the department.

---

## 3. Scope of the System

### 3.1 Faculty Scope
- Register/authenticate using institutional credentials.
- Login/logout and manage profile.
- Add, edit, delete, and tag questions in the question bank (subject, topic, difficulty, Bloom's level).
- Configure paper generation parameters (subject, marks, duration, sections, difficulty mix, topic coverage).
- Trigger AI-based question generation and/or intelligent selection.
- Review, edit, replace, or regenerate individual questions before finalizing.
- Submit a completed paper for coordinator review (optional workflow) or finalize directly.
- Export finalized papers to PDF/Word.
- View history of previously generated papers for their subjects.
- Receive notifications on generation completion, insufficient question-bank coverage, and approval status.

### 3.2 Department Coordinator Scope
- View, search, and filter papers submitted for review.
- Review a generated paper for topic coverage, difficulty balance, and formatting.
- Approve a paper for finalization or return it to faculty with review comments.
- Monitor paper status across subjects and faculty within the department.
- Escalate overdue/unreviewed papers as the exam date approaches.
- Generate department-level coverage and usage reports.

### 3.3 Administrator Scope
- Manage users (faculty, coordinators) and their department/subject assignments.
- Manage subjects, topic taxonomies, difficulty matrices, and Bloom's-level definitions.
- Configure system settings, AI-provider settings, and notification templates.
- Monitor system activity and audit logs.
- Generate institution-wide question-bank health and paper-generation reports.

### 3.4 Student (Indirect Stakeholder)
- Does not interact with the system directly, but is affected by the quality, fairness, and consistency of generated papers.

---

## 4. Stakeholders

| Stakeholder | Role |
|---|---|
| Faculty / Teachers | Build the question bank, configure and generate papers, review and finalize output |
| Department Coordinator | Reviews and approves generated papers before distribution |
| System Administrator | Manages the overall system, users, and configuration |
| Academic Office / Management | Monitors question-bank health, paper turnaround, and compliance with exam policy |
| Student (indirect) | Affected by paper quality, fairness, and difficulty balance |

---

## 5. User Roles

| Role | Description |
|---|---|
| Faculty / Teacher | Can manage the question bank for their subjects, configure and generate papers, and finalize output within their scope. |
| Department Coordinator | Can review, comment on, and approve/reject papers submitted by faculty before finalization. |
| Administrator | Has system-level configuration and management privileges across subjects, users, and settings. |

---

## 6. Functional Requirements

| ID | Requirement |
|---|---|
| FR-01 | **User Registration & Login:** The system shall allow authorized users to register/authenticate and log in/out securely (institutional account or local credentials). |
| FR-02 | **Role-Based Access Control:** The system shall enforce distinct permissions for Faculty, Department Coordinator, and Administrator. |
| FR-03 | **Question Bank Management:** Faculty/admin shall add, edit, delete, and categorize questions by subject, topic, difficulty level, and Bloom's Taxonomy level. |
| FR-04 | **Bulk Question Import:** The system shall allow faculty to import questions in bulk (e.g., CSV/Excel) into the question bank. |
| FR-05 | **Paper Parameter Configuration:** Faculty shall specify subject, total marks, exam duration, number of sections, section-wise marks split, difficulty distribution, and topic coverage for a paper. |
| FR-06 | **AI-Assisted Question Generation:** The system shall use an AI/NLP model to generate new questions and/or intelligently select existing questions from the bank matching the specified parameters. |
| FR-07 | **Intra-Paper Duplicate Prevention:** The system shall ensure no duplicate or near-duplicate questions appear within a single generated paper. |
| FR-08 | **Cross-Paper Repetition Avoidance:** The system shall avoid reusing questions from a configurable number of recent papers for the same subject, where feasible. |
| FR-09 | **Paper ID Generation:** The system shall automatically generate a unique paper reference identifier, e.g. `AIQPG-2026-CS301-014`. |
| FR-10 | **Manual Review & Editing:** Faculty shall manually review, edit, replace, or regenerate individual questions before finalizing a paper. |
| FR-11 | **Difficulty & Bloom's Balancing:** The system shall verify that the selected/generated question set meets the configured difficulty and cognitive-level distribution, flagging any shortfall. |
| FR-12 | **Insufficient Bank Alerts:** The system shall notify the user when the question bank cannot satisfy the requested parameters (e.g., not enough "Hard" questions for a topic). |
| FR-13 | **Coordinator Review Workflow:** Faculty shall optionally submit a paper for coordinator review; coordinators shall approve, reject, or return it with comments. |
| FR-14 | **Paper Status Management:** The system shall maintain statuses such as Draft, Generated, Under Review, Returned, Approved, Finalized, and Archived. |
| FR-15 | **Paper History & Versioning:** The system shall maintain a version history of edits made to a paper prior to finalization, and a searchable log of all finalized papers. |
| FR-16 | **Export:** The system shall export a finalized paper to PDF and/or Word format in a clean, print-ready layout, including institution header, marks, and instructions. |
| FR-17 | **Search and Filtering:** Faculty, coordinators, and administrators shall search/filter the question bank and paper history by subject, topic, difficulty, Bloom's level, status, and date range. |
| FR-18 | **Dashboard:** The system shall provide role-specific dashboards (faculty, coordinator, administrator) showing question-bank coverage, pending reviews, and recent papers. |
| FR-19 | **Reports:** The system shall generate reports on question-bank coverage, topic/difficulty distribution, and paper-generation activity by subject, department, and date range. |
| FR-20 | **Audit Trail:** The system shall maintain a tamper-evident audit log of question-bank changes, paper generation events, edits, approvals, and exports. |
| FR-21 | **Notifications:** The system shall notify relevant users on paper generation completion, insufficient bank coverage, review submission, approval, and rejection. |

---

## 7. AI-Based Functional Requirements

| ID | Requirement |
|---|---|
| AI-FR-01 | **Question Generation:** The system may generate new candidate questions from the syllabus/topic description using an AI/NLP model, tagged with a suggested difficulty and Bloom's level. |
| AI-FR-02 | **Intelligent Question Selection:** The system may rank and select existing question-bank entries that best satisfy the requested marks, topic coverage, and difficulty mix. |
| AI-FR-03 | **Difficulty & Bloom's-Level Prediction:** The system may analyze a question's text and suggest its difficulty level and Bloom's Taxonomy classification; faculty may accept or override the suggestion. |
| AI-FR-04 | **Duplicate / Near-Duplicate Detection:** The system may compare candidate questions against the question bank and recent papers using semantic similarity to flag likely duplicates or close paraphrases. |
| AI-FR-05 | **Coverage Gap Analysis:** The system may analyze the current paper draft against the configured topic-coverage targets and flag under-represented topics before finalization. |
| AI-FR-06 | **Regeneration Suggestions:** When a question is rejected or flagged, the system may propose one or more AI-generated or bank-sourced replacements matching the same topic and difficulty slot. |

---

## 8. Non-Functional Requirements

| ID | Requirement |
|---|---|
| NFR-01 | **Performance:** A complete question paper (typical size) should be generated within approximately 30 seconds under normal load. |
| NFR-02 | **Security:** Use secure authentication, password hashing, role-based authorization, encryption of the question bank and generated papers at rest and in transit, and input validation. |
| NFR-03 | **Confidentiality:** Draft and finalized papers, and the underlying question bank, shall be visible only to authorized roles associated with that subject; papers shall be inaccessible before the configured release/exam date. |
| NFR-04 | **Usability:** Provide a simple interface usable by faculty with no programming background, with a clear paper-configuration flow, status indicators, and a responsive design for desktop and tablet. |
| NFR-05 | **Reliability:** The AI component shall generate contextually relevant, syllabus-appropriate questions with a low error rate, and the system shall not lose in-progress question-bank or paper data during normal operation. |
| NFR-06 | **Availability:** The system should be accessible whenever faculty need to generate papers, with minimal scheduled downtime, particularly ahead of examination periods. |
| NFR-07 | **Scalability:** The architecture shall support a growing number of subjects, departments, users, and question-bank entries without major redesign. |
| NFR-08 | **Maintainability:** Use a modular architecture so new subjects, difficulty rules, cognitive-level taxonomies, and AI providers can be added with minimal changes. |
| NFR-09 | **Compatibility:** Support modern browsers such as Chrome, Edge, and Firefox. |
| NFR-10 | **Auditability:** All access to and modification of the question bank and generated papers shall be logged in a tamper-evident audit trail. |
| NFR-11 | **Backup and Recovery:** The question bank, paper history, and configuration data should be backed up periodically so information can be recovered after a system failure. |
| NFR-12 | **Academic Integrity Alignment:** Duplicate-avoidance and confidentiality controls should be configurable to align with the institution's examination-integrity policy. |

---

## 9. External Interface Requirements

### 9.1 User Interface
- **Faculty:** login, dashboard, question-bank management, paper configuration wizard, AI generation review, export.
- **Department Coordinator:** dashboard, review queue, approval/return workflow, department reports.
- **Administrator:** user, subject, and taxonomy management, dashboard, institution-wide reports.

### 9.2 Software Interfaces
- MongoDB / relational database for structured question-bank and paper data.
- Institutional SSO / identity provider for authentication (optional).
- Third-party AI/LLM API for question generation, difficulty prediction, and similarity detection.
- Document-generation service for PDF/Word export.
- Notification service (email, and optionally in-app).

### 9.3 Hardware Interfaces
- Desktop computers
- Laptops
- Tablets

---

## 10. Proposed Technology Stack

| Layer | Technology |
|---|---|
| Frontend | React.js |
| Styling | CSS / Tailwind CSS |
| Backend | Node.js |
| Backend Framework | Express.js |
| Database | MongoDB |
| Database Management | MongoDB Compass |
| Authentication | JWT (+ optional SSO/OAuth2) |
| Password Security | bcrypt |
| AI / NLP | Third-party LLM API (e.g., OpenAI API / Hugging Face models) |
| Document Export | PDF/Word generation library (e.g., pdf-lib, docx) |
| Charts | Recharts |
| API Testing | Postman |
| Version Control | Git + GitHub |
| Development Environment | VS Code |

---

## 11. System Architecture

```
AI-BASED QUESTION PAPER GENERATOR
     FACULTY / COORDINATOR / ADMIN
                 |
          React Frontend
                 |
             REST API
                 |
        Node.js + Express
                 |
   +-------------+--------------+
   |             |              |
MongoDB     Document Export   AI / LLM
Database    Service (PDF/Word) Service
   |                             |
   |                    Generation / Selection /
   |                    Difficulty Prediction /
   |                    Duplicate Detection
   |
Question Bank + Paper History + Audit Log
```

---

## 12. Question Paper Generation Lifecycle

```
Faculty configures paper parameters
             |
   Parameters validated against
        question-bank coverage
             |
        Sufficient?
        /        \
      No          Yes
      |            |
  Notify faculty   AI generates / selects questions
  (insufficient    |
   bank coverage)  Duplicate & coverage checks
                    |
             Draft paper produced
                    |
        Faculty reviews / edits / regenerates
                    |
              Review required?
              /            \
            No              Yes
            |                |
       Finalize        Coordinator review
            |           /            \
            |      Approved        Returned
            |          |               |
            |      Finalize      Back to faculty
            |          |
            +----------+
                    |
            Export to PDF/Word
                    |
        Archived in paper history
```

---

## 13. Business Rules

- A user must be authenticated before accessing the question bank or generating a paper.
- Every generated paper must have a unique paper reference ID.
- Every question in the bank must belong to a valid subject and topic.
- Only faculty assigned to a subject can add, edit, or use questions from that subject's bank.
- A paper cannot be finalized while a duplicate question is present within it.
- Papers submitted for coordinator review cannot be finalized until approved.
- Only an authorized coordinator or the originating faculty member can finalize a paper.
- Finalized papers shall not be silently altered; any post-finalization change requires a new version and an audit entry.
- AI-generated questions and AI-suggested difficulty/Bloom's levels are recommendations; faculty retain final authority.
- Draft and finalized papers are hidden from users not assigned to that subject or role.
- Users cannot access information or functionality outside their assigned role.

---

## 14. Assumptions

- Faculty have access to the institution's network or a secure remote connection.
- A structured question bank (manually entered or AI-assisted) is available or will be built incrementally.
- The system depends on a third-party AI/LLM API, requiring internet connectivity.
- Users have basic computer literacy; no specialized training is provided.
- The accuracy and relevance of AI-generated questions depend on the quality of the underlying model and question-bank data.
- Coordinators and administrators are registered in the system in advance where the review workflow is enabled.

---

## 15. Constraints

- Network/internet connectivity is required to access the portal and reach the AI/LLM API.
- AI output quality depends on the volume and quality of historical question-bank data.
- The initial version supports a limited set of subjects/departments and primarily text-based question types (MCQ, short answer, long answer).
- Development timeline and team size may limit the scope achievable within the semester.
- The initial project may be a prototype rather than a production institution-wide deployment.

---

## 16. Feasibility Analysis

### 16.1 Technical Feasibility
The system can be developed using widely available technologies such as React.js, Node.js, Express.js, and MongoDB, together with a third-party AI/LLM API and standard authentication/encryption libraries. Therefore, the project is technically feasible.

### 16.2 Economic Feasibility
The prototype can rely on open-source technologies and free/developer-tier AI API access, keeping development cost low.

### 16.3 Operational Feasibility
The system simplifies question-bank maintenance and paper assembly for faculty while giving coordinators a lightweight review step. Therefore, it is operationally feasible.

### 16.4 Schedule Feasibility
The project can be developed in phases: requirement analysis, system design, database design, frontend development, backend development, AI-integration, testing, and deployment.

---

## 17. Security Requirements

- Secure authentication (JWT-based, with optional SSO).
- Password hashing for local accounts.
- Role-based access control enforced on every API endpoint.
- Encryption of the question bank and generated papers at rest and in transit.
- Time-gated access to finalized papers until the configured release/exam date.
- Input validation and file-type/size validation for bulk question imports.
- Protection against unauthorized API access.
- Tamper-evident audit logging of all question-bank and paper-related actions.
- Proper session/token management and timely session expiry.

---

## 18. Testing Requirements

**Unit Testing** — Individual functions and modules (e.g., difficulty balancing, paper-ID generation, duplicate detection) shall be tested independently.

**Integration Testing** — Interactions between frontend/backend, backend/database, and the external AI/LLM API shall be tested.

**System Testing** — The complete paper-generation lifecycle shall be tested from parameter configuration through export.

**Security Testing** — Unauthorized access, role permissions, and pre-release confidentiality of papers shall be tested.

**Usability Testing** — The system shall be evaluated for ease of question-bank management and paper configuration.

**User Acceptance Testing** — Representative faculty and coordinators shall evaluate whether the system meets requirements.

---

## 19. Requirement Prioritization (MoSCoW)

- **Must Have:** FR-01, FR-02, FR-03, FR-05, FR-06, FR-07, FR-09, FR-10, FR-16, FR-21
- **Should Have:** FR-04, FR-08, FR-11, FR-12, FR-17, FR-19
- **Could Have:** FR-13, FR-14, FR-15, FR-18, FR-20
- **Won't Have (this version):** Automated grading, handwriting recognition, multi-institution deployment

---

## 20. Success Criteria

- Users can register/authenticate and log in successfully.
- Faculty can build and maintain a tagged question bank.
- Faculty can configure and generate a paper meeting marks, duration, and difficulty targets.
- Every generated paper receives a unique reference ID.
- No duplicate questions appear within a finalized paper.
- Faculty can review, edit, replace, and regenerate individual questions before finalizing.
- Coordinators can review and approve/return papers where the workflow is enabled.
- Finalized papers can be exported to PDF/Word in a clean, exam-ready format.
- Role-based access and pre-release confidentiality work correctly.
- Reports and dashboards give faculty/coordinators/administrators visibility into bank coverage and paper status.
- AI modules provide useful recommendations without preventing normal paper generation when unavailable.

---

## 21. Future Enhancements

- Support for question types beyond text (diagrams, code snippets, image-based questions).
- AI-based plagiarism/similarity checking against external question sources.
- Automatic answer-key and rubric generation alongside the question paper.
- Multi-institution / multi-tenant deployment.
- Mobile application for on-the-go paper review and approval.
- Analytics on question performance (post-exam difficulty calibration) to improve future AI predictions.
- Direct LMS integration for syllabus ingestion and paper distribution.
- Configurable approval workflows with multiple review stages.

---

## 22. Glossary

| Term | Meaning |
|---|---|
| Question Bank | A repository of stored questions categorized by subject, topic, and difficulty. |
| NLP | Natural Language Processing — AI techniques used to understand and generate human language. |
| Bloom's Taxonomy | A classification of learning objectives used to assess the difficulty/cognitive level of questions. |
| MoSCoW | A prioritization technique: Must have, Should have, Could have, Won't have. |
| Paper Reference ID | A unique identifier automatically assigned to every generated question paper. |

---

## 23. References

- IEEE Std 830-1998 — IEEE Recommended Practice for Software Requirements Specifications.
- Sommerville, I., *Software Engineering*, 10th Edition, Pearson.
- Third-party AI/NLP tools, APIs, or datasets referenced by the team (e.g., OpenAI API, Hugging Face models).

---

## 24. Conclusion

The AI-Based Question Paper Generator provides a centralized solution for building, maintaining, and drawing on a tagged question bank to assemble examination papers that meet marks, duration, topic-coverage, and difficulty targets. The system connects faculty and department coordinators through a structured, auditable paper-generation lifecycle — from configuration and AI-assisted authoring, through manual review and optional coordinator approval, to export and archival. It improves consistency and exam integrity through duplicate detection, difficulty/Bloom's-level balancing, versioning, and audit logging, while dashboards and reports give faculty and administrators visibility into question-bank health and paper-generation activity. AI-assisted question generation, selection, and difficulty prediction can further reduce faculty workload while keeping final decisions under human (faculty) supervision. The proposed system is technically, economically, and operationally feasible, and can serve as a foundation for a scalable, institution-wide exam-preparation support platform.
