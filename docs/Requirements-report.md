# Requirements Report

**Project Title:** AI-Based Question Paper Generator
**Course:** Software Engineering
**Document Version:** 1.0
**Date:** September 09, 2026

**Team Members:**
| Name | Roll No. | Role |
|---|---|---|
| _Aryan Jha_ | _202401100100064_ | Requirements Report |
| _Akshat Sharma_ | _202401100100029_ | SRS Document |
| _Ashrit Shukla_ | _202401100100069_ | UML Use Case Diagram |
| _Atharva Singh_ | _202401100100072_ | Development / Implementation |

---

## 1. Introduction

### 1.1 Purpose
This document presents the requirements analysis for the **AI-Based Question Paper Generator**, a system designed to automate the creation of examination question papers using artificial intelligence. It identifies the problem being solved, the scope of the proposed system, the stakeholders involved, and the functional and non-functional requirements that the system must satisfy. This report serves as the foundation for the subsequent Software Requirements Specification (SRS) document and the UML Use Case Diagram.

### 1.2 Problem Statement
Manually preparing question papers is a time-consuming and repetitive task for faculty. It requires selecting questions of appropriate difficulty, ensuring adequate topic coverage, avoiding repetition from previous papers, and formatting the paper correctly — all while maintaining confidentiality and academic standards. This process is prone to human error, inconsistent difficulty distribution, and inefficient use of faculty time.

### 1.3 Proposed Solution
The proposed system uses AI/NLP techniques to automatically generate question papers based on a given syllabus, subject, topic distribution, difficulty level, and marks allocation. Faculty can specify parameters such as total marks, number of sections, and difficulty mix, and the system will generate a well-structured, non-repetitive question paper that can be reviewed, edited, and exported.

### 1.4 Intended Audience
This document is intended for the course instructor/evaluator, the project development team, and any future contributors to the project.

---

## 2. Project Scope

### 2.1 In Scope
- Management of a question bank (add, edit, delete, tag questions by topic and difficulty).
- AI-based generation of questions and/or intelligent selection from the question bank based on user-defined parameters.
- Configuration of paper parameters: subject, total marks, duration, number of sections, difficulty distribution, and topic coverage.
- Detection and avoidance of duplicate/repeated questions within a paper and across recent papers.
- Manual review, editing, and regeneration of individual questions before finalizing a paper.
- Export of the generated question paper into a downloadable format (PDF/Word).
- Basic user authentication for faculty/admin access.

### 2.2 Out of Scope
- Automatic grading or evaluation of student answer scripts.
- Handwriting recognition or scanning of physical documents.
- Plagiarism detection outside the system's own question bank.
- Support for subjective/practical/viva-based assessments requiring human judgment.
- Multi-institution deployment in the initial version (single-institution use only).

### 2.3 Assumptions and Constraints
- A structured question bank (manually entered or AI-generated) is available or will be built incrementally.
- The system may depend on a third-party AI/LLM API, requiring internet connectivity.
- Initial version supports a limited set of subjects/departments, primarily text-based question types (MCQ, short answer, long answer).
- Users are assumed to have basic computer literacy; no specialized training is provided.
- The accuracy and relevance of AI-generated questions depend on the quality of the underlying model/dataset.

---

## 3. Stakeholders and User Roles

| Role | Description |
|---|---|
| **Admin** | Manages user accounts, subjects, and overall system configuration. |
| **Teacher / Faculty** | Creates and manages the question bank, configures paper parameters, generates and finalizes question papers. |
| **Department Coordinator** *(optional)* | Reviews and approves generated papers before distribution. |
| **Student** *(indirect stakeholder)* | Does not interact with the system directly but is affected by the quality of generated papers. |

---

## 4. Functional Requirements

| ID | Requirement | Priority |
|---|---|---|
| FR1 | The system shall allow authorized users to log in and log out securely. | Must |
| FR2 | The system shall allow the admin/faculty to add, edit, delete, and categorize questions in a question bank by subject, topic, and difficulty level. | Must |
| FR3 | The system shall allow faculty to specify paper generation parameters: subject, total marks, exam duration, number of sections, and difficulty distribution (e.g., easy/medium/hard ratio). | Must |
| FR4 | The system shall use an AI/NLP model to generate new questions and/or intelligently select existing questions matching the specified parameters. | Must |
| FR5 | The system shall ensure that no duplicate questions appear within a single generated paper. | Must |
| FR6 | The system shall avoid repeating questions used in a configurable number of previous papers for the same subject, where feasible. | Should |
| FR7 | The system shall allow faculty to manually review, edit, replace, or regenerate individual questions in a generated paper before finalizing it. | Must |
| FR8 | The system shall allow the finalized question paper to be exported/downloaded in PDF and/or Word format. | Must |
| FR9 | The system shall tag each question with a difficulty level and/or Bloom's Taxonomy level for balanced paper generation. | Should |
| FR10 | The system shall maintain a history/log of previously generated papers for reference and audit purposes. | Could |
| FR11 | The system shall notify the user of errors (e.g., insufficient questions in the bank to meet specified parameters). | Must |

---

## 5. Non-Functional Requirements

| ID | Category | Requirement |
|---|---|---|
| NFR1 | Performance | The system shall generate a complete question paper within an acceptable time (e.g., under 30 seconds for a standard paper). |
| NFR2 | Usability | The interface shall be simple and usable by faculty with no technical/programming background. |
| NFR3 | Security | Question bank data and generated papers shall be protected from unauthorized access to preserve exam confidentiality. |
| NFR4 | Reliability | The AI component shall generate contextually relevant and syllabus-appropriate questions with a low error rate. |
| NFR5 | Scalability | The system architecture shall support the addition of new subjects, departments, and larger question banks without major redesign. |
| NFR6 | Maintainability | The codebase shall be modular to allow easy updates to the AI model or question bank structure. |
| NFR7 | Availability | The system shall be accessible whenever faculty need to generate papers, with minimal downtime. |

---

## 6. Requirement Prioritization (MoSCoW)

- **Must Have:** FR1, FR2, FR3, FR4, FR5, FR7, FR8, FR11
- **Should Have:** FR6, FR9
- **Could Have:** FR10
- **Won't Have (this version):** Automated grading, handwriting recognition, multi-institution support

---

## 7. Constraints and Dependencies

- Dependency on an external AI/LLM API or a locally trained NLP model for question generation.
- Dependent on availability of a reasonably populated question bank for meaningful output.
- Development timeline and team size may limit the scope achievable within the semester.

---

## 8. Glossary

| Term | Meaning |
|---|---|
| **Question Bank** | A repository of stored questions categorized by subject, topic, and difficulty. |
| **NLP** | Natural Language Processing — AI techniques used to understand and generate human language. |
| **Bloom's Taxonomy** | A classification of learning objectives used to assess difficulty/cognitive level of questions. |
| **MoSCoW** | A prioritization technique: Must have, Should have, Could have, Won't have. |

---

## 9. References

1. IEEE Std 830-1998 — IEEE Recommended Practice for Software Requirements Specifications.
2. Sommerville, I., *Software Engineering*, 10th Edition, Pearson.
3. _[Add any specific AI/NLP tools, APIs, or datasets referenced by your team, e.g., OpenAI API, Hugging Face models, etc.]_

---

*This Requirements Report will serve as the basis for the Software Requirements Specification (SRS) Document and the UML Use Case Diagram.*
