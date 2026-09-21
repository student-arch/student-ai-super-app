# Architecture Plan (No Implementation)

Version: 0.9.1-approved | Date: 2026-09-21 | Status: English-only MVP, vision v0.9.0 applies

Backend choice: Supabase. Details in SUPABASE-PLAN.md. This file keeps module boundaries and cross-cutting rules.

## 1. Module Boundaries

| Module | Owns | Depends On |
|--------|------|------------|
| Identity and Profile | Google login, email login (password, email OTP), password reset, sessions, logout-all, college and branch, year and semester, subjects, goals, verification status. No phone auth | None |
| Academic Progress (approved) | Marks and CGPA, assignments, syllabus checklist | Identity |
| Content Library | PYQs, materials, PDF metadata, bookmarks, uploads, annotations, approval status | Identity |
| Notes and AI Study | Notes, summaries, doubt sessions, explanations, OCR imports, lecture-link notes | Content Library, Identity |
| Assessment | Tests, questions, attempts, scores, explanations | Notes and AI Study, Content Library |
| Revision | Decks, cards, review schedule, statistics | Notes and AI Study |
| Timetable | Weekly template, date exceptions, holidays | Identity |
| Attendance | Records per period, targets, recovery estimates | Timetable |
| Engagement (Phase 2+) | Career, events, teams, community, projects, GK, wellness, notifications, search, analytics | Identity plus Phase 1 modules |

Rule: Assessment never writes timetable data. Attendance never writes test data. AI outputs are stored as assistive artifacts linked to source materials. Date-specific exceptions never mutate weekly template.

## 2. User Roles — APPROVED student-only 2026-09-21

- Student: only app user. Uses all released features.
- Contributor (student): student submits PYQs and materials.
- Reviewer (internal ops, not college staff): internal team or trusted students approve or reject with reason.
- Administrator (internal ops only): manages users, reports, safety prep for Phase 3. No college staff login anywhere.

No permissions are implemented in this doc. This is a specification.

## 3. Integrations — APPROVED: Supabase plus external services
- Backend platform: Supabase for Auth, managed database, file storage, scheduled jobs, server orchestration, realtime concepts. See SUPABASE-PLAN.md Sections 2 to 7.
- Calendar export for timetable and deadlines via server orchestration.
- Notification channels: push, email via server orchestration. SMS deferred.
- AI service provider called server-side only, behind per-student daily usage counters.

## 4. Non-Functional Requirements

- DPDP build-now: app as Data Fiduciary with lawful ground per purpose, processor contracts, accuracy for decisions, safeguards per Rules rule 6, breach notice without delay plus 72-hour Board update path, retention erasure at purpose end, under-18 age gate with verifiable parental consent, access plus 90-day grievance plus nominee, transfer map, SDF watch. Full guide in COMPLIANCE-DPDP.md. Build now for 13 May 2027 duties.
- Privacy: purpose limitation for college ID with masking, data export and account deletion flows, AI training opt-out to be decided.
- Reliability: timetable exception rule must hold — date-specific changes affect only that date.
- Availability: dashboard loads with cached timetable even if content library is slow.
- Accessibility: keyboard navigation, readable contrast, scalable text. Language: English only for MVP. Regional languages, text-to-speech, font scaling deferred to Phase 2 proposal.
- Scalability: PYQ search by college, university, regulation version, subject, year.
- Auditability: attendance recalculation traceable to class changes.

## 5. Explicit Non-Goals
- No API contracts in this version.
- No schema implementation. See DATA-MODEL-SPEC.md and SUPABASE-PLAN.md for specs without code.
