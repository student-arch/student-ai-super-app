# Roadmap — Phased Delivery Plan

Version: 0.9.1-approved | Date: 2026-09-21 | Status: Vision v0.9.0 applies, all aligned

## Phase 0 — Supabase Setup plus DPDP Readiness (prerequisite) — APPROVED
- Provision development, staging, production projects.
- Configure Auth methods: Google sign-in plus email only (password, email OTP, reset). No phone OTP.
- Configure storage buckets per SUPABASE-PLAN.md Section 4, access principles per Section 5.
- Enable backups for production. Apply starter locks: 100 MB per student, 5 notes, 3 tests, 5 summaries per day. See FOUNDER-STARTUP-GAPS.md Section 10.
- Pilot scope: 1 college, 1 branch, 1 semester (Pilot-College-TBD until named). Goal 100 waitlist.
- DPDP build-now checklist per COMPLIANCE-DPDP.md Section 11: purposes recorded, processor contracts reviewed, access owners named with ID masking, breach playbook with without-delay user notice and 72-hour Board path, retention categories, age gate with parental consent, access export plus 90-day grievance plus nominee, transfer map, SDF watch. Build now for duties scheduled 13 May 2027.

## Phase 1 — MVP (Learn, Practice, Remember, Attend) — APPROVED
Objective: usable daily study loop.

Includes:
- Dashboard and profile plus approved additions: auth recovery and verification, CGPA tracker, assignments tracker.
- PYQ library, materials, notes generation plus approved additions: annotation, OCR import, syllabus checklist, lecture-link notes.
- AI doubt assistance, test and mock system subset (single-definition rule).
- Flashcards with spaced repetition.
- Weekly timetable, date exceptions, attendance with targets, self-marked only.
- Student contributor plus internal reviewer flows for content approval. No college staff accounts.

Exit criteria:
- Onboarding to dashboard works, including reset and logout-all.
- PYQ search, view, annotate, bookmark works.
- PDF upload to summary works. Syllabus checklist percent-complete works.
- Timed MCQ test with history works.
- Spaced repetition rescheduling works.
- Holiday and cancelled classes do not lower attendance.
- Contributor submit to reviewer approve works.
- Privacy request creates trackable grievance with 90-day response cap. Access export includes sharing list.

## Phase 2 — Progress and Opportunities
Objective: connect study to outcomes.

Includes (from vision list, pending detailed PRD):
- Calendar sync, offline management.
- Career roadmap subset, events and opportunities discovery.
- Search and analytics subset, notifications subset.
- P1 proposals remain unapproved: resume builder, coding tracker, gamification XP, multi-language, focus tools, mentorship, fees tracking.

## Phase 3 — Community and Portfolio
Objective: collaboration and career launch.

Includes:
- Team-up, team management, communities with moderation (moderation approved as prerequisite spec, UI in Phase 3).
- Project workspace, showcase, portfolio entries.
- Placement prep, mock interviews, resume builder (still proposal, not approved).
- GK feed, wellness reminders, full analytics.

## Explicitly Deferred
- Diet planner remains excluded per vision Section 11. Wellness reminders stay in scope for Phase 3.
- SMS notifications deferred. Phone OTP excluded per v0.4.0 auth decision.
- Long-answer auto-evaluation deferred to manual review in Phase 1.

## Dependency Notes — UPDATED student-only
- Community launch requires moderation spec already approved in v0.2.0. Moderation by internal ops, no college staff.
- Content library uses student contributors plus internal reviewers. No college staff accounts.
- Attendance: self-marked only. No faculty verification.
