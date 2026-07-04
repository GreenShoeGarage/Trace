# FI060 Trace

**Version:** 3.2.3  
**Type:** Self-contained HTML/CSS/JavaScript web app  
**Storage model:** Local-first, browser-based autosave

FI060 Trace is a local-first investigation board for collecting claims, evidence, observations, links, quotes, uncertainties, actions, and decisions around a central question. It is intended for engineering troubleshooting, facilities investigations, policy reviews, site visits, field reports, root-cause reviews, and other situations where the work is less about managing a project and more about understanding what is true.

Trace helps answer four practical questions:

1. What do we think is true?
2. What evidence supports or contradicts it?
3. What remains uncertain?
4. What should we do next?

The app is not a cloud service, project manager, legal discovery system, or ticketing tool. It is a structured field notebook for reasoning from evidence.

---

## Contents

- [Quick Start](#quick-start)
- [Core Concepts](#core-concepts)
- [Main Views](#main-views)
- [Typical Workflow](#typical-workflow)
- [Autosave and Local Storage](#autosave-and-local-storage)
- [Import and Export](#import-and-export)
- [Fast Capture](#fast-capture)
- [Templates](#templates)
- [Map View](#map-view)
- [Review View](#review-view)
- [Reports](#reports)
- [Keyboard Shortcuts](#keyboard-shortcuts)
- [Data Model](#data-model)
- [Recommended Use Practices](#recommended-use-practices)
- [Troubleshooting](#troubleshooting)
- [Deployment](#deployment)
- [Version History](#version-history)

---

## Quick Start

1. Open `trace.html` in a modern web browser.
2. Click **Load Sample** to explore the sample investigation, or click **New Investigation** to start a blank board.
3. Enter the investigation title, guiding question, context, summary finding, and status in the right inspector panel.
4. Add claims, evidence, uncertainties, actions, and decisions from the board or the inspector.
5. Use **Trace View** and **Map** to evaluate relationships between claims and evidence.
6. Use **Review** to check board health, contradictions, and closeout readiness.
7. Use **Report** to generate a field report, executive brief, decision memo, troubleshooting report, or evidence appendix.
8. Use **Export JSON** regularly if you want a portable backup outside browser storage.

No installation, build process, server, account, or database is required.

---

## Core Concepts

### Investigation

An investigation is the top-level container. It has a title, guiding question, context, status, summary finding, final decision, tags, report notes, and collections of claims, evidence, uncertainties, actions, decisions, and snapshots.

Example guiding question:

> Why does AHU-2 report high motor temperature after 2 PM?

### Claim

A claim is a statement that might be true. Claims can be supported, contradicted, tested, accepted, or rejected.

Useful claim examples:

- Belt tension is too high.
- Motor temperature sensor is drifting.
- Filter restriction is increasing fan load.
- Afternoon occupancy load explains the alarm.

Claim fields include:

- Title
- Statement
- Status
- Confidence
- Classification: Known, Unknown, Assumed, Disputed, or Decided
- Owner
- Date observed
- Prove test
- Disprove test
- Test plan
- Test result
- Notes
- Tags

### Evidence

Evidence is an observation, measurement, note, quote, link, test result, or file reference that supports, contradicts, or provides neutral context for a claim.

Evidence fields include:

- Title
- Type
- Direction: Supports, Contradicts, or Neutral
- Related claim
- Source
- Source reliability
- Evidence strength
- Date observed
- File/reference field
- Quote or excerpt
- Notes
- Tags

### Uncertainty

An uncertainty is an open question that needs resolution before the board can be relied on.

Uncertainty fields include:

- Question
- Why it matters
- Priority
- Related claim
- Method to resolve
- Owner
- Due date
- Status

### Action

An action is a next step. Trace includes actions, but it is intentionally not a full task-management system.

Action fields include:

- Title
- Owner
- Priority
- Due date
- Related item
- Status
- Notes

### Decision

A decision records a conclusion or choice based on claims and evidence.

Decision fields include:

- Decision statement
- Rationale
- Date decided
- Decided by
- Related claims
- Notes

---

## Main Views

### Board

The Board is the primary capture and organization view. It displays claims, evidence, uncertainties, actions, and decisions as cards.

Use this view when you are building or editing the investigation.

### Trace View

Trace View is a claim-centered reasoning view. It shows, for each claim:

- Confidence score
- Supporting evidence
- Contradicting evidence
- Neutral context
- Open questions
- Related actions
- Decision trail
- Status recommendations

Use this view when you want to understand the strength of each claim.

### Map

The Map is a visual relationship view. It places claims in the center, evidence on the left, and questions, actions, and decisions to the right.

Map features include:

- Zoom in and out
- Fit to view
- Full-screen mode
- Drag-to-pan
- Node click inspection
- Relationship labels
- Claim focus
- Claim ordering
- Map modes
- Node-type toggles

Use this view when you need to see clusters, gaps, evidence islands, contradictions, and decision paths.

### Evidence Ledger

The Evidence Ledger is a structured table of all evidence items.

Use this view when reviewing sources, reliability, dates, and evidence linkage.

### Dashboard

The Dashboard summarizes the investigation using charts and metrics.

It includes:

- Claim count
- Evidence count
- Open uncertainties
- Average confidence score
- Claim status distribution
- Evidence direction distribution
- Confidence distribution
- Source reliability distribution
- Evidence strength distribution
- Known/Unknown/Assumed classification distribution
- Open actions by owner
- Evidence age

Use this view to quickly understand investigation health and where attention is needed.

### Review

Review combines the previous health, contradiction, and closeout checks into one view with tabs:

- **Health** checks for missing links, weak records, orphaned items, and incomplete fields.
- **Contradictions** focuses on claims with opposing evidence.
- **Closeout** checks whether the investigation is ready to close and export as a final package.

Use this view before making a recommendation or publishing a report.

### Snapshots

Snapshots capture the investigation state at a point in time. Use them to preserve milestones and compare changes.

Snapshot comparison can show:

- New evidence
- Added claims
- Changed counts
- Updated closeout state

### Report

The Report Builder generates readable output from the investigation.

Report modes include:

- Technical Field Report
- Executive Brief
- Decision Memo
- Troubleshooting Report
- Evidence Appendix

Report styles include:

- Color Field Report
- Executive Brief
- Plain

You can select which report sections to include.

---

## Typical Workflow

### 1. Start with a question

Create a new investigation and write a guiding question.

A good guiding question is specific enough to focus the evidence.

Example:

> Why does AHU-2 report high motor temperature after 2 PM?

### 2. Add claims

Claims are possible explanations, findings, or interpretations.

Good claims are testable and specific.

Instead of:

> Something is wrong with the HVAC system.

Use:

> Filter restriction is increasing fan load.

### 3. Add evidence

For each evidence item, identify whether it supports, contradicts, or provides neutral context for a claim.

Evidence should include a source, reliability, strength, and date observed when possible.

### 4. Record uncertainty

If a claim depends on missing information, add an uncertainty.

Example:

> Was belt tension measured after replacement?

### 5. Add actions

Actions should resolve uncertainty or collect discriminating evidence.

Example:

> Compare BAS temperature sensor to calibrated handheld reading.

### 6. Review contradictions

Use Trace View, Map, and Review to find claims with conflicting evidence.

Do not ignore contradiction. A high-quality contradiction is often more useful than several weak supporting notes.

### 7. Make decisions

Add decisions when you are ready to document a conclusion, recommendation, or next step.

### 8. Export a report

Use the Report Builder to generate an executive brief, technical report, decision memo, troubleshooting report, or appendix.

---

## Autosave and Local Storage

Trace automatically saves to the browser using `localStorage`.

The active storage key for this version is:

```text
fi060-trace-v3
```

Trace also attempts to migrate earlier local storage records from previous Trace and Evidence Board versions.

Important notes:

- Data is stored locally in the browser where the app is used.
- Data is not sent to a server by the app.
- Clearing browser storage can delete saved investigations.
- Different browsers or devices do not share data automatically.
- Use **Export JSON** for portable backups.

---

## Import and Export

### Export JSON

Use **Export JSON** to save a complete backup of the app state.

The JSON export includes:

- Investigations
- Claims
- Evidence
- Uncertainties
- Actions
- Decisions
- Snapshots
- Theme
- Report settings
- Map settings
- Display preferences

Use JSON export for backups and moving work between browsers or devices.

### Import JSON

Use **Import JSON** to restore a previous Trace export.

Imported data is normalized to the current schema. Trace attempts to repair missing fields, invalid enum values, duplicate IDs, and legacy structures.

### CSV Export

Trace can export:

- Evidence CSV
- Claims CSV

Use CSV when you want to share the ledger, review data in a spreadsheet, or archive the investigation in tabular form.

### Evidence CSV Import

Trace supports importing evidence from a CSV-style format. For best results, use headers similar to:

```text
title,type,direction,claim,source,reliability,strength,dateObserved,quote,notes,tags,fileRef
```

The `claim` field should match an existing claim title if you want the evidence linked automatically.

---

## Fast Capture

Fast Capture is designed for field use when speed matters more than completeness.

You can capture:

- Evidence / observation
- Claim
- Uncertainty
- Action

Fast Capture supports:

- Title
- Observation or statement
- Claim linkage
- Evidence direction
- Reliability
- Strength
- Source
- Date observed

Use **Save + Add Another** when entering several field notes in a row.

---

## Templates

Trace includes investigation templates for common workflows:

- Engineering Troubleshooting
- Facilities Incident
- Policy Review
- Site Visit
- Root Cause Investigation
- Vendor/Product Evaluation

Templates create a new investigation with starter claims, actions, and an initial uncertainty.

---

## Map View

The Map View is intended to show relationship structure, not just decoration.

### Map layout

- Evidence appears on the left.
- Claims appear in the center.
- Questions, actions, and decisions flow to the right.

### Relationship types

- Supports
- Contradicts
- Neutral context
- Question
- Action
- Decision

### Map controls

- **Minus** reduces zoom.
- **Fit** returns the map to a useful scale and position.
- **Plus** increases zoom.
- **Full Screen Map** expands the map workspace.
- **Exit Full Screen** returns to the normal app layout.
- Drag the map area to pan.
- Click a node to inspect it without recentering the map.

### Map modes

- All
- Contested only
- Unsupported only
- Evidence islands

### Node-type toggles

You can show or hide:

- Evidence
- Questions
- Actions
- Decisions

---

## Review View

The Review view is used to decide whether the investigation is ready to rely on.

### Health

Health checks look for issues such as:

- Claims with no evidence
- Evidence with no source
- Evidence not linked to a claim
- Decisions not linked to claims
- Open uncertainties
- Open actions

### Contradictions

The Contradictions tab surfaces claims that have both support and opposition, or claims marked as contested.

Use this before turning claims into findings.

### Closeout

Closeout checks whether the investigation has enough structure to be closed.

It considers:

- Summary finding
- Final decision
- Accepted or supported claims
- Contradictions addressed
- High-priority uncertainties resolved or acknowledged
- Decisions linked to evidence or claims
- Follow-up actions assigned

Closeout can mark the investigation closed, save a closeout snapshot, and generate a final package.

---

## Reports

The Report Builder turns the investigation into a readable output.

### Report sections

Selectable sections include:

- Executive summary
- Guiding question
- Claim table
- Evidence ledger
- Contested claims
- Open uncertainties
- Recommended actions
- Decision trail
- Appendix

### Report actions

- **Copy Report** copies a Markdown-style text report to the clipboard.
- **Download HTML** exports a standalone HTML report.
- **Print** opens the browser print dialog.
- **Evidence CSV** downloads the evidence ledger.
- **Claims CSV** downloads the claim table.

---

## Keyboard Shortcuts

| Shortcut | Action |
|---|---|
| `N` | New investigation |
| `C` | Add claim |
| `E` | Add evidence |
| `/` | Focus search |
| `M` | Open Map |
| `V` | Open Review |
| `R` | Open Report Builder |
| `F` | Fast Capture |
| `Esc` | Exit full-screen map or close modal |
| `Cmd/Ctrl + S` | Force local save and prompt JSON export |

Shortcuts are disabled while typing in form fields.

---

## Data Model

Trace uses a JSON document with this general structure:

```json
{
  "version": "3.2.3",
  "theme": "light",
  "activeView": "board",
  "activeInvestigationId": "inv_example",
  "investigations": [
    {
      "id": "inv_example",
      "title": "Investigation title",
      "question": "Guiding question",
      "context": "Background context",
      "status": "Exploring",
      "summaryFinding": "Current finding",
      "finalDecision": "Final decision",
      "claims": [],
      "evidence": [],
      "uncertainties": [],
      "actions": [],
      "decisions": [],
      "snapshots": []
    }
  ]
}
```

The app normalizes imported data, so older exports and partial records can usually be loaded safely.

---

## Recommended Use Practices

### Write claims as testable statements

A claim should be specific enough that evidence can support or contradict it.

### Link every evidence item to a claim when possible

Unlinked evidence is not always bad, but it should be intentional.

### Treat contradiction as useful

Contradicting evidence does not mean the board is failing. It means the investigation is becoming more honest.

### Record sources clearly

A note without a source is harder to rely on later.

### Use confidence carefully

Confidence should reflect the evidence, not just intuition.

### Use snapshots at milestones

Save a snapshot before major status changes, before closeout, or after adding important evidence.

### Export JSON regularly

Autosave is convenient. JSON export is the safer backup.

---

## Troubleshooting

### My data disappeared

Trace stores data in browser `localStorage`. If browser storage was cleared, the local autosave copy may be gone. Restore from a JSON export if available.

### I opened Trace on another device and my data is not there

Trace is local-first and does not sync automatically. Export JSON from the first device and import it on the second.

### The layout looks wrong after an update

Try a hard refresh. If problems persist, export JSON, clear the browser cache for the page, reload, and import the JSON backup.

### The map is hard to navigate

Use **Fit** to reset the view. Use zoom controls and drag-to-pan. Use claim focus and node-type toggles to reduce visual complexity.

### Imported JSON does not look right

Make sure it came from Trace or an earlier Evidence Board export. The app repairs many legacy fields, but heavily edited JSON may not import cleanly.

### CSV evidence did not link to claims

The CSV `claim` value should match an existing claim title. You can still manually link imported evidence from the inspector.

---

## Deployment

Trace is a single static file.

### Local use

Open `trace.html` directly in a browser.

### Website deployment

Upload `trace.html` to any static web host.

Examples:

- Personal website
- Shared intranet folder
- GitHub Pages
- Cloudflare Pages
- Netlify
- Static Apache/Nginx directory

No server-side code is required.

### Privacy note

Trace does not intentionally transmit investigation data. It runs in the browser and stores data locally. However, if you host the HTML file on a third-party platform, that platform may still log ordinary web access metadata.

---

## Version History

### v3.2.3

- Moved Map callout boxes below the map to give the visual map more horizontal space.
- Preserved full-screen map controls and map navigation behavior.

### v3.2.2

- Fixed map node selection so clicking a node opens the inspector without recentering or resetting map position.
- Added selected-node highlighting.

### v3.2.1

- Fixed full-screen map stacking so controls stay visible above the map.
- Improved full-screen map scrolling.

### v3.2

- Major UI stabilization pass.
- Improved dark-mode readability.
- Fixed scrolling behavior across major views.
- Cleaned up Report Builder layout.

### v3.1

- Data cleanup and streamlining pass.
- Moved storage to `fi060-trace-v3`.
- Added stronger migration, normalization, duplicate ID cleanup, and stale selection cleanup.
- Consolidated Board Health, Contradictions, and Closeout into Review.

### v3.0

- Added map interaction, evidence strength, status recommendations, report builder, templates, snapshots, board health, contradiction review, fast capture, keyboard shortcuts, known/unknown/assumed classification, hypothesis testing fields, and closure workflow.

### v2.x

- Renamed app to Trace.
- Added Trace View and a true Map View.
- Added full-screen map mode and collapsible menu.
- Improved relationship visualization.

### v1.0

- Initial local-first Evidence Board concept with claims, evidence, autosave, import/export, sample data, dashboard, and report export.

---

## License and Attribution

Trace is part of the Field Instruments series.

```text
FI060 Trace | M.B. Parks, Green Shoe Garage (c) 2026. All rights reserved.
```

