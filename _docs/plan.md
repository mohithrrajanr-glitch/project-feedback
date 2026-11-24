# Weekly Project Feedback & Retrospective Tool — MVP Plan

## 1. Product vision

Build a multi-tenant, AI-assisted SaaS application for Agile software development teams to collect weekly feedback, understand team sentiment, conduct effective retrospectives, and track agreed improvements through completion. The product supports continuous improvement, not individual employee performance evaluation.

## 2. Confirmed scope decisions

All 27 decisions from the brainstorming session are captured below. Recommendations not explicitly selected are identified separately in Section 7.

| # | Decision | Selected option | Scope |
|---|---|---|---|
| 1 | Primary objective | B + C + D | Team retrospectives, employee feedback (sentiment, workload, collaboration and satisfaction), and action tracking. |
| 2 | Target audience | A | Agile software development teams for the MVP. |
| 3 | Feedback collection | D | Hybrid: structured ratings, open-ended feedback, and AI follow-up. |
| 4 | Feedback identity | D | Participants choose anonymous or identified submissions. |
| 5 | Retrospective workflow | C | Asynchronous collection, AI-generated insights, and live team discussion. |
| 6 | AI responsibilities | E | Summarization, analysis, trend detection, recommendations, and facilitation. |
| 7 | Questionnaires | D | Standard recurring questions, project-specific customization, and adaptive AI follow-ups. |
| 8 | Action tracking | A (MVP) | Description, owner, due date, and status; basic built-in tracking only. |
| 9 | Project hierarchy | B | Multiple projects, each with its own team, feedback, retrospectives, and actions. |
| 10 | User roles | B | Admin, Facilitator, and Team Member. |
| 11 | Scheduling | C | Automatic weekly cycles plus manual launch and rescheduling, with configurable submission deadlines. |
| 12 | Live retrospective | A + C | Report-driven facilitator-led discussion with AI assistance and recorded decisions; no interactive collaborative board required. |
| 13 | Reporting | D | Weekly reports, historical trends, action analytics, and project-level dashboards. |
| 14 | Notifications | B | Email and in-app notifications for invitations, feedback deadlines, and published reports. |
| 15 | Report publication | C | Preliminary AI report for facilitator review; final report after live discussion. |
| 16 | Submission interface | C | Structured questionnaire followed by optional AI chat. |
| 17 | Historical AI context | C | Rolling 4–8 weeks of project history. |
| 18 | Anonymous feedback protection | D | No stored association between anonymous feedback content and its author; aggregate reporting with minimum participation thresholds. |
| 19 | Authentication | B | Passwordless email magic links and invitation-based project membership. |
| 20 | Deployment | B | Multi-tenant SaaS with strict organizational data isolation. |
| 21 | Organization onboarding | B | Self-service registration, organization creation, and team invitations; no billing in MVP. |
| 22 | Data retention | C | Organization-admin-configurable retention periods and automatic deletion of expired data. |
| 23 | Application interface | B | Responsive web application for desktop, tablet, and mobile browsers. |
| 24 | Live AI interaction | A | Text-based assistant available to the facilitator during the retrospective. |
| 25 | AI context sources | A + B | Internal project feedback, retrospective history and actions, plus manually entered sprint goals and updates. |
| 26 | Insight validation | C | Manual facilitator review plus supporting anonymized evidence and aggregate metrics. |
| 27 | Success measures | D | Engagement, effectiveness, and efficiency metrics. |

## 3. Core MVP workflow

1. **Onboard:** An organization admin registers, creates an organization and projects, assigns roles, and invites users.
2. **Configure:** A facilitator configures the weekly schedule, submission deadlines, standard and project-specific questions, and optionally supplies sprint goals or project updates.
3. **Launch:** The system starts the weekly cycle automatically or the facilitator starts it manually. Participants receive email and in-app invitations.
4. **Collect:** Members complete structured ratings and open-ended questions, optionally use AI follow-up chat, and choose anonymous or identified submission. Deadline notifications support participation.
5. **Analyze:** The AI consolidates eligible feedback, identifies themes, analyzes aggregate sentiment, detects recurring issues using rolling history, and suggests discussion topics and actions.
6. **Review:** The facilitator reviews the preliminary report, checks permitted supporting evidence and aggregate metrics, and edits inaccurate or potentially identifying content.
7. **Discuss:** The facilitator leads a live retrospective using the report and text-based AI assistant. Team decisions and proposed actions are recorded.
8. **Publish:** The facilitator publishes the final report after discussion. Team members receive notifications.
9. **Act:** Agreed actions are assigned owners and due dates, and their statuses are tracked.
10. **Improve:** Project dashboards surface historical trends and action analytics, informing subsequent weekly retrospectives.

## 4. Functional modules

### Organization, project, and access management
- Self-service organization registration and setup.
- Multiple projects per organization, with independent memberships, feedback, retrospective history, and actions.
- Passwordless email authentication and invitations.
- Role-based access control and tenant isolation.

### Roles
| Role | Primary responsibilities |
|---|---|
| Admin | Manage organization, projects, users, permissions, and retention settings. |
| Facilitator | Configure and launch retrospectives; supply context; review reports; guide discussion; record decisions and actions; publish reports. |
| Team Member | Submit feedback, optionally chat with AI, participate in discussions, view permitted reports, and manage assigned actions. |

Detailed permission matrix remains to be defined.

### Feedback and scheduling
- Configurable weekly automatic schedule, manual launch and rescheduling.
- Configurable submission deadlines.
- Standard recurring rating questions for longitudinal comparison.
- Open-ended feedback and customizable project questions.
- Optional adaptive AI follow-up conversation.
- Participant choice of anonymous or identified feedback.
- Email and in-app invitations and deadline notifications.

### AI and retrospective facilitation
- Summarize feedback and group common themes.
- Analyze team-level sentiment, blockers, and recurring issues.
- Recommend improvements, discussion questions, and action items.
- Use rolling 4–8 weeks of eligible project history, prior actions, and manually supplied context.
- Provide a text-based facilitator assistant during the live discussion.
- Generate preliminary reports with permitted supporting evidence.
- Require facilitator review before publication; team retains decision-making authority.
- Avoid individual employee scoring and unsupported conclusions.

### Reports and dashboards
- Preliminary facilitator-only AI report and final published report.
- Weekly themes, feedback summaries, concerns, decisions, and actions.
- Week-over-week aggregate sentiment and recurring issues.
- Action completion rates, overdue actions, and resolution trends.
- Project-level historical dashboard.
- Published-report notifications.

### Action management
- Action description, owner, due date, and status.
- Track actions within the application.
- Automated action-specific reminders and external task synchronization are deferred (feedback deadline notifications remain in scope).

## 5. Privacy and security requirements

- Strict tenant isolation across database queries, reports, AI context, and user access.
- Anonymous feedback must not retain a link to the submitting user's identity, including in logs, analytics, AI transcripts, and metadata that could create such a link.
- Anonymous content is presented through aggregated themes subject to minimum participation thresholds.
- Evidence shown to facilitators must not undermine anonymous reporting; raw identifiable quotations or individual-level drill-downs must not be exposed for anonymous submissions.
- Identified feedback access must follow an explicit permission policy.
- Organization-configurable data retention and automatic deletion, including relevant derived data according to the eventual policy.
- No individual employee scoring or ranking.
- Human review of AI insights before publication.

The exact anonymity threshold and technical implementation have not been decided. Anonymity cannot be guaranteed by hiding names alone; small teams, content details, timestamps, and submission tracking require careful design.

## 6. MVP success metrics

| Dimension | Metrics |
|---|---|
| Engagement | Weekly feedback participation rate; retrospective completion rate. |
| Effectiveness | Action completion rate; changes in recurring issue frequency. |
| Efficiency | Time spent preparing retrospectives; retrospective meeting duration; time saved relative to baseline. |

Measure at team/project level. Baselines, calculation definitions, and numerical targets remain open.

## 7. Out of scope / deferred and recommendations

### Deferred from MVP
- Jira, GitHub, Azure DevOps, and other external project/task integrations.
- Slack and Microsoft Teams notification integrations.
- Automated action follow-ups and action-specific reminders.
- Real-time collaborative retrospective boards, grouping, and voting.
- Voice AI, meeting recording, and automated meeting facilitation.
- Native mobile apps and installable PWA capabilities.
- SSO and password-based authentication.
- Billing, subscriptions, and payment processing.
- Multiple independent teams per project, custom roles, and observer role.
- Automated secondary AI verification pipeline.

### Recommendations and implementation considerations (not separately confirmed)
- Default to anonymous feedback while preserving explicit participant choice.
- Require human approval for creating AI-suggested actions.
- Design the data model to permit future organization/project/team expansion.
- Use simple dashboard visualizations.
- Define safe aggregation thresholds before exposing reports; do not use raw participation timestamps to identify anonymous respondents.

## 8. Open decisions before implementation

- Exact standard questionnaire, rating scale, required vs optional questions, and AI follow-up limits.
- Anonymous submission mechanism, duplicate prevention, participation tracking, reporting threshold, and handling of small teams.
- Detailed role/permission matrix and visibility of identified feedback and reports.
- Retrospective lifecycle states, late submissions, cancellation, reopening, and report revision rules.
- Action status values, edit permissions, and carryover behavior.
- Default schedule, timezone handling, and notification timing.
- Retention defaults, allowed ranges, deletion of derived reports and backups, and audit policy.
- Exact rolling history window within the selected 4–8 week range.
- AI provider/model, data handling, prompt design, guardrails, evidence grounding, evaluation, and cost limits.
- Technology stack, database design, APIs, infrastructure, security testing, deployment, and observability.
- Metric definitions, baselines, and MVP acceptance criteria.

## 9. Next planning steps

The brainstorming session ended with Question 28, asking which deliverable to define next. No option was selected before this plan was saved.

Recommended sequence:
1. Product Requirements Document (PRD): formalize requirements and acceptance criteria.
2. User journeys: define end-to-end workflows for each role and key edge cases.
3. System architecture: technology stack, database, APIs, AI architecture, and infrastructure.
4. Development roadmap: epics, user stories, milestones, and implementation priorities.

---
This document consolidates the confirmed product scope from the 27-question brainstorming session. It is a planning baseline, not a finalized technical specification. Additional implementation details and recommendations are explicitly marked as such.
