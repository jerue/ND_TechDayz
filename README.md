# ServiceNow Workspace TechDayz Lab

## Service Operations Workspace: an agent-focused introduction

**Audience:** ServiceNow agents and platform-adjacent team members who are familiar with working records but are not expected to configure or develop a workspace.

**Core lab time:** 35 minutes

**Optional extension:** 5–8 minutes

**Session design:** 12 minutes of presentation + 35 minutes of lab + 8 minutes of debrief + 5 minutes of buffer.

## What you will learn

By the end of this lab, you should be able to:

1. Find relevant work in Service Operations Workspace (SOW).
2. Work an incident from intake through a documented next step without losing context.
3. Use the record’s related information to support a decision.
4. Explain when a focused workspace helps an agent and when Core UI may still be the better surface.
5. Recognize that one user may legitimately work in more than one workspace, depending on their role.

## Before you begin

This is an agent workflow lab. You are not expected to build or publish a workspace.

The facilitator should replace the values below before the event.

| Lab item | Fill in before the session |
| --- | --- |
| SOW landing page or navigation path | `https://northdakotasandbox.service-now.com/sow` |
| Lab incident | `<INC>` — recommended scenario: repeated VPN authentication prompts |
| Lab knowledge article | `<>` — recommended: VPN authentication troubleshooting checklist |
| Lab CI / service | `<LAB-CI-NAME>` / `<LAB-SERVICE-NAME>` |
| Lab assignment group | `<NDIT-End User Compute>` |`<NDIT-Network Services>` | `<NDIT-Lab Agent>` |

### Facilitator setup checklist

- Use a dedicated sandbox or sub-production instance with fictional records only. Do not ask attendees to exercise a live production incident.
- Confirm that the Service Operations Workspace for ITSM application is installed and that participants can launch it. The current application listing is `sn_sow_itsm_cont`; exact installation and compatibility requirements depend on your release and entitlements.
- Give each participant the normal ITSM access needed to read and update the seeded incident. A common SOW role is `sn_sow_user`, but it is not a replacement for your normal incident ACLs and role bundle—validate your local configuration first.
- Seed one incident with a caller, assignment group, affected CI/service, a related knowledge article, and enough activity history to make investigation realistic.
- Ensure that actions such as emails, notifications, integrations, or flows are disabled or redirected for the lab data if they could reach real people or systems.
- If Agent Assist, Recommended Actions, investigation tabs, or collaboration are not enabled in your sandbox, leave them out rather than improvising configuration during the event. The core lab still works.

### Recommended lab scenario

Use a small, intentionally safe record set.

| Record | Recommended value |
| --- | --- |
| Incident | `<LAB-INCIDENT-NUMBER>` — “Repeated VPN authentication prompts after password reset” |
| Caller | `Avery Chen` (fictional) |
| Assignment group | `<LAB-ASSIGNMENT-GROUP>` / Network Operations |
| Affected CI | `<LAB-CI-NAME>` / `VPN-GW-01` |
| Business service | `<LAB-SERVICE-NAME>` / Remote Access Service |
| Knowledge | `<LAB-KB-NUMBER>` — “Troubleshoot repeated VPN authentication prompts” |
| Starting state | New or Assigned; Priority 2; assigned to the lab group, not an individual |

## Lab conventions

- Labels, tabs, and actions vary by ServiceNow release and your instance configuration. Use the equivalent function if the wording differs.
- Do not change the CI, service, knowledge article, assignment group, or workspace configuration unless an exercise explicitly tells you to do so.
- Make all updates on the seeded lab incident only.
- If you do not see an optional capability, record that observation and continue. A missing panel is not a failure.

---

## Exercise 1 — Find and frame the work (5 minutes)

### Goal

Orient yourself in SOW and identify the work that needs attention.

1. Open `<YOUR-SOW-LANDING-PAGE>`.
2. Take 30 seconds to identify the navigation pane, landing page, work queues or lists, and any alerts or assigned-work indicators your experience exposes.
3. Navigate to the incident work list for "Assigned to Me". You will then be able to see an incident,  `<LAB-INCIDENT-NUMBER>`.
4. Filter or sort the list so the lab incident is easy to find. Do not save a personal list layout unless your facilitator asks you to.
5. Open the incident in a workspace tab.

### Checkpoint

Write down one piece of information that was available before you opened the record. Examples: priority, assignment group, SLA indicator, caller, service, or a queue count.

> Reflection: What did the workspace put in front of you that you would otherwise have had to find through navigation?

---

## Exercise 2 — Take ownership and document the next step (8 minutes)

### Goal

Work the incident safely while preserving an auditable record.

1. On the incident record, confirm the short description, caller, priority, assignment group, and current state.
2. Review the activity stream or record history before changing anything.
3. Assign the incident to yourself, or use the lab owner named by the facilitator.
4. Change the state to **In Progress** or your sandbox’s equivalent active state.
5. Add this work note, replacing the bracketed text:

   ```text
   Initial investigation started in SOW. Reviewed [CI/service] and [knowledge or related record]. Next step: [specific, safe next action].
   ```

6. Save or update the record.
7. Re-open the activity stream entry and verify that your change is visible.

### Checkpoint

Can a teammate who was not present understand what you checked and what happens next?

> Reflection: Which updates feel like agent work, and which fields still feel like pure record maintenance?

---

## Exercise 3 — Use context rather than opening a scavenger hunt (8 minutes)

### Goal

Use the incident’s related information to form a reasonable troubleshooting direction.

1. Locate the affected CI or business service on the incident.
2. Open the record’s related-information view, contextual side panel, or equivalent tab.
3. Find `<LAB-CI-NAME>` and `<LAB-SERVICE-NAME>`. Do not edit either record.
4. Open `<LAB-KB-NUMBER>` through the record, Agent Assist, a related list, or search—use the route exposed in your workspace.
5. Identify one troubleshooting step from the article that applies to this incident.
6. Add a second work note:

   ```text
   Context review: [KB number/title] recommends [one applicable step]. Related service/CI reviewed: [name].
   ```

7. Save the incident.

### Checkpoint

Record the path you used:

```text
Incident → ____________________ → ____________________ → KB / CI / service
```

> Reflection: Did the record page help you gather context in one flow, or did it push you back into separate navigation? Be specific.

### Optional: Agent Assist (2 minutes, only if enabled)

Open the Agent Assist panel. ServiceNow documents it as a way to find similar Universal Requests, knowledge articles, catalog items, and pinned articles.

- Find one potentially relevant suggestion.
- Do not apply or publish generated/recommended content automatically.
- Add a work note only if the suggestion is actually useful and you have verified it.

---

## Exercise 4 — Collaborate without losing the record (6 minutes)

### Goal

Practice a safe handoff or escalation in the same work context.

Choose one path that your sandbox supports:

### Path A — Work-note handoff (works in every lab)

1. Add a work note that names the next team or role that would own the next technical decision.
2. Include the evidence that person needs: the CI/service, the relevant knowledge step, and the observed symptom.
3. Save the record.

### Path B — Assign or create follow-on work (only if seeded and safe)

1. Use the incident’s available action to assign to the lab escalation group or create a **lab-only** follow-on task.
2. Link the follow-on work to the incident.
3. Verify that the original incident still tells the full story.

### Path C — Collaboration integration (only if explicitly enabled)

Use a sandbox collaboration action to add a lab-only discussion or shared context. Do not create a real Teams channel, conference call, notification, or external message.

### Checkpoint

Before you move on, answer this: If the incident opened in a second workspace tab, would its status and context still be trustworthy? Why?

---

## Exercise 5 — See the multi-workspace reality (4 minutes)

### Goal

Understand that workspaces are role-specific experiences, not separate identities.

1. Open the application launcher or your organization’s workspace switcher.
2. Identify another workspace that your current roles allow you to use. This could be CSM Configurable Workspace, CMDB Workspace, HR Agent Workspace, Security Operations Workspace, SPM, or another locally relevant experience.
3. Do not request new access or attempt to work records outside the lab scope.
4. If you do not have a second workspace, use the facilitator’s demonstration or screenshot instead.
5. Record the answer:

   ```text
   My current role could legitimately use ____________________ in addition to SOW because ____________________.
   ```

### Checkpoint

What remains the same when you move among workspaces? Think in terms of data, access controls, ownership, and audit history.

---

## Exercise 6 — Compare intentionally, do not declare a winner by default (4 minutes)

### Goal

Choose the best work surface for the task rather than treating a workspace as a mandatory replacement.

1. If your facilitator has supplied a safe Core UI link, open the same lab incident in Core UI. Otherwise, use the record’s available classic/open-in-platform option or observe the facilitator’s comparison.
2. Compare the two experiences using the table below.

| Question | SOW observation | Core UI observation |
| --- | --- | --- |
| How did I find the record? |  |  |
| What context was immediately visible? |  |  |
| What did I need to navigate elsewhere to find? |  |  |
| Which view better supported this exact task? |  |  |

3. Choose one task category that belongs primarily in SOW and one that may still belong in Core UI.

### Checkpoint

Finish this sentence:

> A workspace is the better default for ____________________, while Core UI is still useful for ____________________.

---

## Optional extension — Observe the configuration boundary (5–8 minutes)

This extension is for observation, not editing.

### Recommended control

Do **not** give every attendee broad `admin` access merely for this exercise. The core lab does not require it. If you want to show the configuration layer, use a dedicated sandbox, an isolated lab copy, a temporary least-privilege account where feasible, or a facilitator-led screen share.

### Goal

See that a workspace is configured intentionally, while keeping the team’s focus on agent outcomes.

1. Open the SOW administration or UI Builder experience that the facilitator has prepared.
2. Open an existing **lab-only** record page or landing page in read-only/observe mode.
3. Identify three concepts without changing anything:
   - A page or route.
   - A component or panel.
   - An audience, role, or variant that controls who sees an experience.
4. Close the builder without saving, publishing, or changing variants.

### Reflection

What agent problem would justify a configuration change? “It looks different” is not enough; identify a Find, Understand, or Act problem.

---

## Debrief prompts (8 minutes)

Use these questions as a group.

1. Where did SOW reduce navigation or context switching in this scenario?
2. What information was missing, noisy, or too far from the decision point?
3. Which capability was configuration-dependent in your sandbox?
4. What work should remain in Core UI for now, and why?
5. If an agent has access to multiple workspaces, what should guide the default landing experience?
6. What is one small experience improvement that would make the lab workflow more reliable?

## Completion criteria

You are done when you have:

- Updated the seeded incident with an ownership change and two useful work notes.
- Used a related CI, service, knowledge article, or equivalent context to support the next step.
- Identified a second workspace or explained why you do not need one for your role.
- Made one evidence-based observation about when SOW helps and when Core UI still fits.

## Facilitator reset

After the session:

1. Restore the seeded incident to its starting state, assignment, and work notes, or clone a new record set for the next cohort.
2. Remove temporary access and any time-bound elevation.
3. Verify that no test notifications, collaboration artifacts, external messages, or follow-on tasks escaped the sandbox.
4. Collect participant observations under the three categories: **Find**, **Understand**, and **Act**.

## Source and facilitator references

- [Service Operations Workspace for ITSM — ServiceNow Docs](https://www.servicenow.com/docs/r/it-service-management/service-operations-workspace/sow-landing-page.html)
- [Use Agent Assist in Service Operations Workspace — ServiceNow Docs](https://www.servicenow.com/docs/r/it-service-management/service-operations-workspace/agent-assist-ur-sow.html)
- [Redirect UI16 module links to Service Operations Workspace — ServiceNow Docs](https://www.servicenow.com/docs/r/it-service-management/service-operations-workspace/redirect-ui16-module-links-sow.html)
- [Forms in the classic environment — ServiceNow Docs](https://www.servicenow.com/docs/r/platform-user-interface/c_UsingForms.html)
- [List of workspaces — ServiceNow Docs](https://www.servicenow.com/docs/r/platform-user-interface/list-of-workspaces.html)
- [Employee Slate — ServiceNow Docs](https://www.servicenow.com/docs/r/employee-service-management/employee-experience-foundation/employee-slate-landing-page.html)
