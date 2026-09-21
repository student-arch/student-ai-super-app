# PRD — MVP Scope

Version: 0.16.0-approved | Date: 2026-09-21 | Status: Seed-once shared library, full-auto, no reviewer logins

This PRD defines a buildable MVP subset of `student-ai-super-app-complete-feature-list.md` v0.9.0. It does not modify that file. P0 enhancements from FEATURE-GAPS.md v0.9.1 are now included below as approved scope for new docs.

## 1. Problem Statement
Students juggle PYQs, notes, tests, revision, timetable, and attendance across disconnected tools. The full 14-module vision is too large for an initial release.

## 2. MVP Goals
- Google plus email login only with college, branch, year, semester, subjects.
- Find and study PYQs and materials by subject, semester, university.
- Generate notes and clear doubts with AI assistance.
- Practice with timed tests and review incorrect answers.
- Retain with flashcards and spaced repetition.
- Track weekly timetable, one-day exceptions, and attendance vs target.

## 3. In Scope (Phase 1)

### 3.1 Dashboard and Student Profile
- Registration, login, logout. Approved auth: Google login and email login only — Google sign-in, email and password, email OTP, password reset via email, logout all devices, college ID verification status. No phone OTP.
- Profile: college name and ID, department and branch, year and semester, subjects, skills and interests, goals.
- Dashboard widgets: daily progress, upcoming classes, pending tasks, recent activity, recommendations, achievements.
- Approved additions:
  - Academic record: semester marks entry, SGPA and CGPA calculation, goal tracking.
  - Assignments tracker: list with due date, subject link, status (pending, submitted, overdue), reminder linkage.
- Profile edit with DPDP rights: access export showing what data is processed and shared, grievance request with published 90-day response cap, nominee recording, consent withdrawal. Age gate with verifiable parental consent for under-18 before collection. See COMPLIANCE-DPDP.md Sections 8 and 9.

Acceptance: new student can complete onboarding via Google or email and see personalized dashboard with subjects and upcoming classes. Password reset and logout-all work. Marks entry calculates CGPA. Assignment due dates trigger reminders. Privacy contact request creates a trackable grievance. Export includes sharing list.

### 3.2 Question Paper Library (subset)
- PYQs by subject, semester, university, branch, year, topic and chapter.
- Search, filter, bookmark, recently viewed, saved organization.
- PDF viewer with approved annotation: highlight, note, bookmark anchors. Download (subject to rights).
- Student uploads publish via automated checks only. No reviewer queue. See Section 5.
- Seed-once shared library by ops outside the app (no admin login): PYQs, standard materials, notes, test banks, formula packs seeded once per pilot scope, refreshed per semester and on report thresholds. Students read-only plus report-wrong-content.

Acceptance: student can filter by subject plus semester, open viewer, annotate, bookmark, and find it under Saved.

### 3.3 Study Materials (subset)
- Library by subject, topic, chapter, syllabus.
- PDF viewer, personal PDF upload, summarization, key points, definitions, formulas, important questions extraction.
- Approved additions: photo-to-text import via OCR, syllabus unit-wise completion checklist linked to materials.
- Bookmarking and annotation (highlight, note).
- Formula rendering: LaTeX-style entry with live preview, crisp display in viewer, text fallback for accessibility, error preview for bad syntax. Applies to materials, notes, tests, flashcards, doubt answers.

Out of MVP: offline access management UI is deferred to Phase 2. See ROADMAP.

Acceptance: uploaded PDF produces summary plus key points and can be bookmarked. Syllabus checklist shows percent-complete per subject. Formulas render crisply with readable fallback when syntax is invalid.

### 3.4 Notes Generation (subset)
- AI notes by topic and chapter, from uploaded PDFs. Single definition point for AI notes (see clarification in FEATURE-GAPS.md).
- Short revision notes and detailed notes, exam-oriented notes.
- Approved addition: lecture-link notes from video link with source attribution, plus photo-import notes.
- Organize by subject and chapter, edit, save, export, search.

Acceptance: topic notes can be saved, edited, searched, and exported.

### 3.5 Test and Mock Exam (subset)
- AI test generation by subject, topic, chapter, syllabus, PYQ-based, PDF-to-questions. Single definition point for AI test generation.
- MCQ, True/False, short answer. Long answer deferred to manual review in MVP.
- Difficulty selection, custom test, timed mode, exam simulation.
- Auto-evaluation for MCQ and True/False, explanations, incorrect-answer review, history, retake, performance analysis.

Acceptance: timed MCQ test auto-scores, shows explanations, stores history. Student can report a wrong question or explanation for reviewer triage.

### 3.6 AI Study Assistant (subset)
- Doubt clearing, topic and chapter explanation, step-by-step, simplified explanations, examples, follow-ups.
- Weak-topic identification, revision recommendations, progress analysis.

Acceptance: follow-up questions retain context within a study session.

### 3.7 Revision Without Flashcards — REMOVED v0.15.0
- Flashcards system removed to control AI and storage cost, per approved removal.
- Revision via saved notes, incorrect-answer review, test retakes, syllabus checklist. No decks, no scheduling, no due notifications.

### 3.8 Timetable and Attendance
- Weekly setup, day-wise and period-wise views, subject and classroom details, semester timetable, editing.
- Date-specific exceptions: subject change, period change, extra class, cancelled class, rescheduled class, classroom change, holiday, restore regular.
- Attendance: Present, Absent, Unmarked per period; subject-wise and overall percentage; history; target setting; low-attendance alerts; recovery estimate; auto-recalculation; dashboard.
- Rule preserved: cancelled classes and holidays do not count as absences. Date-specific changes affect only selected date unless regular timetable is explicitly updated.

Acceptance: marking holiday does not lower percentage; setting 75% target highlights subjects below target with recovery count.

## 4. Out of Scope for MVP
- Career roadmap full system, events discovery, opportunities board, team-up and community, project workspace, GK daily feed, fitness tracking, global analytics suite.
- These remain in vision list and are phased in ROADMAP.md.

## 5. User Roles (MVP) — APPROVED full-auto student-only
- Student: only app login. All MVP features. No college staff login. No reviewer or admin logins.
- Uploads: student uploads go live via automated checks only — file type and size, duplicate detection, text-extraction sanity, spam and abuse filters. No human approve queue.
- Seed-once ops seeding happens outside the app with no login: ops loads PYQs, materials, notes, test banks, formula packs once per scope, refreshes per semester and on report thresholds. Students read-only.
- Reports: report-wrong-question and report-content trigger auto-hide plus auto-takedown rules with audit log. No human triage queue in MVP.
- DPDP legal contacts (grievance response and breach reporting owners) remain named humans as required by law. They are not app moderation roles and have no content-approval queue. See COMPLIANCE-DPDP.md.

## 6. Non-Goals for This Document
- No UI design, no API contracts, no database implementation. See ARCHITECTURE-PLAN.md and DATA-MODEL-SPEC.md for plans.

## 7. Open Questions Resolved in v0.2.0, v0.4.0, v0.8.0, v0.9.1
- Who approves uploads? Internal reviewer, not college staff. Approved v0.8.0.
- Attendance: self-marked only, plus rule that date-specific changes never mutate weekly template. Faculty verification excluded. Approved v0.8.0.
- AI single-definition rule approved.
- Auth locked in v0.4.0: Google login and email login only. Phone OTP excluded.
- Language locked in v0.9.1: English only for MVP. Regional languages deferred to Phase 2 proposal, see ROADMAP.md.

## 8. Open Questions Still Requiring User Decision
1. AI daily limits for free users? Starter applied: 5 notes, 3 tests, 5 summaries per day. Paid tier open.
2. Offline requirement for MVP?
