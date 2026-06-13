---
version: alpha
name: internal-devops-control-plane-design-system
description: >-
  A dense, neutral-first DevOps design system for approval workflows, code review, release governance, and scanning. It       
  combines Primer's structural token model and list density, Helios's semantic surface and action hierarchy, and Geist's 
  sharp type scale, high-contrast UI logic, and deployment-oriented status treatment. The result is a design system optimized 
  for operator workflows: blocked-state visibility, explicit gating, typed destructive confirmation, sticky decision zones, 
  and reusable domain components such as Merge Readiness, Gate Summary, Deployment Status, Approval Chain, and Finding Rows.

platforms:
  - desktop web
  - narrow laptop web

references:
  - name: GitHub Primer
    url: https://primer.style/
    contribution:
      - semantic color token naming
      - dense table and page structure
      - primitives and component breadth
  - name: HashiCorp Helios
    url: https://helios.hashicorp.design/
    contribution:
      - surface and foreground semantic pairing
      - button organization patterns
      - typography defaults for data-dense interfaces
  - name: Vercel Geist
    url: https://vercel.com/geist/introduction
    contribution:
      - high-contrast color ladders
      - button content rules
      - deployment status and destructive modal patterns
  - name: DESIGN.md structure reference
    url: https://getdesign.md/mongodb/design-md
    contribution:
      - frontmatter-first documentation format

token_strategy:
  approach: merged-semantic-system
  principles:
    - use Primer-like semantic naming for colors and sizes
    - use Helios-like foreground-surface-border triplets for component states
    - use Geist-like text sizes and component state progression for developer tooling
    - minimize brand colors and maximize operational semantics

colors:
  source_tokens:
    primer:
      fg-accent: "#0969da"
      fg-attention: "#9a6700"
      fg-default: "#1f2328"
      fg-disabled: "#818b98"
      fg-muted: "#59636e"
      fg-on-emphasis: "#ffffff"
      fg-open: "#1a7f37"
      bg-accent-emphasis: "#0969da"
      bg-accent-muted: "#ddf4ff"
      bg-attention-emphasis: "#9a6700"
      bg-attention-muted: "#fff8c5"
      bg-danger-emphasis: "#cf222e"
      bg-danger-muted: "#ffebe9"
      bg-default: "#ffffff"
      bg-disabled: "#eff2f5"
    helios:
      foreground-strong: "#0c0c0e"
      foreground-primary: "#3b3d45"
      foreground-faint: "#656a76"
      foreground-disabled: "#8c909c"
      foreground-action: "#1060ff"
      foreground-critical: "#e52228"
      surface-primary: "#ffffff"
      surface-faint: "#fafafa"
      surface-strong: "#f1f2f3"
      surface-success: "#f2fbf6"
      surface-warning: "#fff9e8"
      surface-critical: "#fff5f5"
      border-strong: "#3b3d4566"
      border-success: "#cceeda"
      border-warning: "#fbeabf"
      border-critical: "#fbd4d4"
      focus-action-internal: "#0c56e9"
      focus-action-external: "#5990ff"
      focus-critical-internal: "#c00005"
      focus-critical-external: "#dd7578"
    geist:
      note: Geist publishes scaled color ladders and a two-background model rather than a short semantic token table.
      adopted_behavior:
        - background-1 for default canvas
        - background-2 for secondary separation
        - colors-1-to-3 for component backgrounds
        - colors-4-to-6 for border states
        - colors-7-to-8 for high-contrast surfaces
        - colors-9-to-10 for text and icon contrast
  merged_tokens:
    canvas-default: "#ffffff"
    canvas-subtle: "#f6f8fa"
    surface-default: "#ffffff"
    surface-subtle: "#fafafa"
    surface-muted: "#f1f2f3"
    surface-inset: "#eef2f6"
    surface-info: "#ddf4ff"
    surface-success: "#f2fbf6"
    surface-warning: "#fff9e8"
    surface-danger: "#fff5f5"
    text-strong: "#0c0c0e"
    text-default: "#1f2328"
    text-secondary: "#3b3d45"
    text-muted: "#59636e"
    text-faint: "#656a76"
    text-disabled: "#818b98"
    text-on-emphasis: "#ffffff"
    text-link: "#0969da"
    text-success: "#1a7f37"
    text-warning: "#9a6700"
    text-danger: "#cf222e"
    border-default: "#d0d7de"
    border-muted: "#e5e7eb"
    border-strong: "#b6bec8"
    border-success: "#cceeda"
    border-warning: "#fbeabf"
    border-danger: "#fbd4d4"
    fill-info-bold: "#0969da"
    fill-success-bold: "#1a7f37"
    fill-warning-bold: "#9a6700"
    fill-danger-bold: "#cf222e"
    focus-default-inner: "#0c56e9"
    focus-default-outer: "#5990ff"
    focus-danger-inner: "#c00005"
    focus-danger-outer: "#dd7578"

typography:
  source_tokens:
    primer:
      fontStack-monospace: "ui-monospace, SFMono-Regular, SF Mono, Menlo, Consolas, Liberation Mono, monospace"
      fontStack-sansSerif: "-apple-system, BlinkMacSystemFont, 'Segoe UI', 'Noto Sans', Helvetica, Arial, sans-serif"
      text-display-size: "40px"
      text-display-weight: "500"
      text-title-size-large: "32px"
      text-title-weight-large: "600"
    helios:
      display-500: "30px / bold"
      display-400: "24px / bold, semibold, medium"
      display-300: "18px / bold, semibold, medium"
      display-200: "16px / semibold"
      display-100: "13px / medium"
      body-300: "16px"
      body-200: "14px"
      body-100: "13px"
      code-300: "16px"
      code-200: "14px"
      code-100: "13px"
    geist:
      heading-32: "dashboard headings"
      heading-24: "section headings"
      button-16: "largest button"
      button-14: "default button"
      label-14: "most common dense UI label"
      label-12: "tertiary text in busy views"
      copy-16: "modal and roomy content"
      copy-14: "most common text style"
      copy-13: "secondary text"
      copy-13-mono: "inline code mentions"
  merged_tokens:
    font-sans: '"Geist Sans", "PingFang SC", "Noto Sans SC", -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, Arial, sans-serif'
    font-mono: '"Geist Mono", ui-monospace, SFMono-Regular, "SF Mono", Menlo, Consolas, monospace'
    text-display: "32px / 36px / 600"
    text-page-title: "24px / 28px / 600"
    text-section-title: "20px / 24px / 600"
    text-card-title: "16px / 24px / 600"
    text-body-default: "14px / 20px / 400"
    text-body-strong: "14px / 20px / 600"
    text-body-secondary: "13px / 18px / 400"
    text-meta: "12px / 16px / 500"
    text-button-default: "14px / 20px / 600"
    text-button-large: "16px / 24px / 600"
    text-code-default: "13px / 18px / 400"
    text-code-strong: "13px / 18px / 600"

spacing:
  source_tokens:
    primer-base-size:
      size-4: "4px"
      size-8: "8px"
      size-12: "12px"
      size-16: "16px"
      size-20: "20px"
      size-24: "24px"
      size-32: "32px"
      size-40: "40px"
      stack-gap-normal: "16px"
      stack-gap-spacious: "24px"
      overlay-width-small: "320px"
      overlay-width-medium: "480px"
      overlay-width-large: "640px"
      overlay-width-xlarge: "960px"
    helios-guidance:
      default-body-size: "14px"
      large-button-size: "16px"
    geist-guidance:
      dense-ui-defaults:
        - label-14
        - copy-14
        - button-14
  merged_tokens:
    space-1: "4px"
    space-2: "8px"
    space-3: "12px"
    space-4: "16px"
    space-5: "20px"
    space-6: "24px"
    space-8: "32px"
    space-10: "40px"
    section-gap: "24px"
    card-padding-default: "16px"
    card-padding-comfortable: "20px"
    table-cell-inline: "12px"
    table-row-height-default: "44px"
    table-row-height-dense: "40px"
    rail-width-default: "320px"
    overlay-width-sm: "320px"
    overlay-width-md: "480px"
    overlay-width-lg: "640px"
    overlay-width-xl: "960px"

radius:
  merged_tokens:
    radius-sm: "8px"
    radius-md: "10px"
    radius-lg: "12px"

shadows:
  merged_tokens:
    shadow-xs: "0 1px 2px rgba(15, 23, 42, 0.04)"
    shadow-sm: "0 2px 6px rgba(15, 23, 42, 0.06)"
    shadow-md: "0 8px 24px rgba(15, 23, 42, 0.08)"

motion:
  merged_tokens:
    fast: "120ms"
    base: "160ms"
    slow: "180ms"
    easing-standard: "cubic-bezier(0.2, 0, 0, 1)"

layout:
  widths:
    nav: "240px"
    content-readable-min: "960px"
    content-readable-max: "1120px"
    app-max: "1440px"
    right-rail: "280px - 320px"
  breakpoints:
    desktop-wide: ">= 1440px"
    desktop: "1200px - 1439px"
    compact-desktop: "960px - 1199px"
    constrained: "< 960px"

components:
  adopted_patterns:
    primer:
      - PageHeader
      - PageLayout
      - DataTable
      - StateLabel
      - ConfirmationDialog
      - TreeView
    helios:
      - Button organization
      - Form hierarchy
      - Left-first conversational actions in constrained contexts
    geist:
      - Deployment Status
      - Destructive Action Modal
      - Command Menu
      - File Tree
      - Status Dot

patterns:
  critical:
    - blocked state summary strip
    - sticky review decision bar
    - typed destructive confirmation for severe operations
    - clickable gate summary with explicit resolution text
    - right rail for approvals, blockers, and audit context
---


## Overview

This document defines the design system for an internal DevOps platform covering:

- Approval and release control
- Code review
- Deployment governance
- Code and dependency scanning
- Audit and policy enforcement

This is not a PRD. It is a UI system spec.

The output of this document should be directly usable for:

- Figma foundations and components
- Frontend token implementation
- Reusable layout shells
- Shared interaction rules
- Consistent state mapping across review, release, and scan pages
---

## Product UI Principles

### 1. State is always visible

Every critical screen must expose:

- Object identity
- Current status
- Blocking conditions
- Allowed next actions

No primary workflow should require users to click into a hidden panel to know whether something is blocked.

### 2. Dense, not noisy

This product should support expert users working all day. Density is acceptable. Visual noise is not.

Use:

- Thin borders
- Stable alignment
- Small status elements
- Clear typography hierarchy

Avoid:

- Large colored cards
- Oversized empty states
- Decorative gradients in core workflows
- Excessive icon usage

### 3. One primary action per context

Each screen, panel, modal, or card should have a single dominant action.

Examples:

- Change Request: `Approve` or `Merge`
- Release: `Approve Release` or `Deploy`
- Finding: `Resolve` or `Accept Risk`

### 4. Risk increases friction

The higher the operational risk, the stronger the confirmation pattern.

- Low risk: inline action or toast
- Medium risk: confirmation modal
- High risk: confirmation + reason input + audit disclosure

### 5. Components must encode governance

The design system must not be neutral toward process safety. It must natively support:

- Required approvals
- Blocking gates
- Exception paths
- Permission-based actions
- Audit reasons

---

## Visual Direction

### References adopted from live systems

From Primer:

- Clear page framing
- Strong use of borders as structure
- Dense list and table patterns
- Semantic color usage over decorative color usage

From Helios:

- Calm surface hierarchy
- Restrained page chrome
- Operational clarity over brand expression
- Conservative spacing and layout predictability

From Geist:

- Crisp high-contrast typography
- Tight developer tooling feel
- Sharp, simple status presentation
- Clean action hierarchy

### Direction summary

The product UI should feel like:

- A controlled operating console
- A review workspace
- A release decision tool

It should not feel like:

- A sales dashboard
- A generic enterprise CRUD backend
- A monitoring wallboard

---

## Foundations

## Color

The canonical tokens are defined in the frontmatter `colors.merged_tokens`.

They are intentionally derived from:

- Primer semantic naming
- Helios foreground / surface / border state pairs
- Geist high-contrast ladder behavior

### Canonical merged color tokens

```css
:root {
  --canvas-default: #ffffff;
  --canvas-subtle: #f6f8fa;
  --surface-default: #ffffff;
  --surface-subtle: #fafafa;
  --surface-muted: #f1f2f3;
  --surface-inset: #eef2f6;
  --surface-info: #ddf4ff;
  --surface-success: #f2fbf6;
  --surface-warning: #fff9e8;
  --surface-danger: #fff5f5;

  --text-strong: #0c0c0e;
  --text-default: #1f2328;
  --text-secondary: #3b3d45;
  --text-muted: #59636e;
  --text-faint: #656a76;
  --text-disabled: #818b98;
  --text-on-emphasis: #ffffff;
  --text-link: #0969da;
  --text-success: #1a7f37;
  --text-warning: #9a6700;
  --text-danger: #cf222e;

  --border-default: #d0d7de;
  --border-muted: #e5e7eb;
  --border-strong: #b6bec8;
  --border-success: #cceeda;
  --border-warning: #fbeabf;
  --border-danger: #fbd4d4;

  --fill-info-bold: #0969da;
  --fill-success-bold: #1a7f37;
  --fill-warning-bold: #9a6700;
  --fill-danger-bold: #cf222e;

  --focus-default-inner: #0c56e9;
  --focus-default-outer: #5990ff;
  --focus-danger-inner: #c00005;
  --focus-danger-outer: #dd7578;
}
```

### Component state token pattern

Each semantic state should support at least:

- foreground
- background or surface
- border
- focus ring

Example:

```css
:root {
  --status-success-fg: var(--text-success);
  --status-success-bg: var(--surface-success);
  --status-success-border: var(--border-success);

  --status-warning-fg: var(--text-warning);
  --status-warning-bg: var(--surface-warning);
  --status-warning-border: var(--border-warning);

  --status-danger-fg: var(--text-danger);
  --status-danger-bg: var(--surface-danger);
  --status-danger-border: var(--border-danger);
}
```

### Rules

- White is the default canvas.
- Light gray organizes sections, not entire workflows.
- Red is reserved for failure, blocking, destructive actions.
- Green means passed, approved, deployed, or healthy.
- Amber means pending risk, requested changes, or requires attention.
- Blue means informational progress, active selection, or current context.

### Prohibited color usage

- No large saturated green success panels
- No red page backgrounds
- No multiple accent button colors on one screen
- No rainbow status tags

## Typography

The canonical tokens are defined in the frontmatter `typography.merged_tokens`.

```css
:root {
  --font-sans: "Geist Sans", "PingFang SC", "Noto Sans SC", -apple-system,
    BlinkMacSystemFont, "Segoe UI", Helvetica, Arial, sans-serif;
  --font-mono: "Geist Mono", ui-monospace, SFMono-Regular, "SF Mono", Menlo,
    Consolas, monospace;

  --text-display: 32px;
  --text-page-title: 24px;
  --text-section-title: 20px;
  --text-card-title: 16px;
  --text-body-default: 14px;
  --text-body-secondary: 13px;
  --text-meta: 12px;
}
```

### Type scale usage

- `32/36/600`: dashboard title only
- `24/28/600`: page title
- `20/24/600`: section title
- `16/24/600`: card title and emphasized labels
- `14/20/400`: default body
- `13/18/400`: dense secondary text
- `12/16/500`: metadata, badges, helper text

### Mono usage

Use `font-mono` for:

- Commit SHA
- Branch names
- File paths
- Rule IDs
- Environment IDs
- Inline code

## Spacing

```css
:root {
  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-5: 20px;
  --space-6: 24px;
  --space-8: 32px;
  --space-10: 40px;
  --section-gap: 24px;
  --card-padding-default: 16px;
  --card-padding-comfortable: 20px;
  --table-cell-inline: 12px;
  --table-row-height-default: 44px;
  --table-row-height-dense: 40px;
}
```

### Spacing rules

- Section gap: `24px`
- Card padding: `16px` or `20px`
- Form control vertical gap: `12px`
- Table cell horizontal padding: `12px`
- Header action gap: `8px`
- Right rail width target: `320px`

## Radius

```css
:root {
  --radius-sm: 8px;
  --radius-md: 10px;
  --radius-lg: 12px;
}
```

### Radius rules

- Inputs and buttons: `8px`
- Cards: `10px`
- Modal and drawer: `12px`
- Avoid radii above `12px`

## Shadow

```css
:root {
  --shadow-xs: 0 1px 2px rgba(15, 23, 42, 0.04);
  --shadow-sm: 0 2px 6px rgba(15, 23, 42, 0.06);
  --shadow-md: 0 8px 24px rgba(15, 23, 42, 0.08);
}
```

### Shadow rules

- Cards default to border only
- Dropdowns may use `--shadow-sm`
- Modals and command surfaces may use `--shadow-md`

## Motion

```css
:root {
  --motion-fast: 120ms;
  --motion-base: 160ms;
  --motion-slow: 180ms;
  --ease-standard: cubic-bezier(0.2, 0, 0, 1);
}
```

### Motion rules

- Hover: `120ms`
- Collapse and expand: `160ms`
- Drawer or modal entry: `180ms`
- No bounce
- No large spring motions

---

## Layout System

## Global Shell

```text
+----------------------------------------------------------------------------------+
| Top Bar                                                                          |
+----------------------+-----------------------------------------------------------+
| Left Navigation      | Page Frame                                                |
|                      |                                                           |
+----------------------+-----------------------------------------------------------+
```

### Top Bar

Contains:

- Workspace switcher
- Global search
- Command trigger
- Quick create
- Notifications
- User menu

### Left Navigation

Rules:

- Fixed width `240px`
- Text-first, icon-second
- Active item has left indicator or strong background
- Max 8 top-level entries visible at once

### Page Frame

Standard page frame sections:

- Page header
- Context row
- Main content
- Optional right rail
- Sticky bottom action bar

## Widths

- App max width: `1440px`
- List pages: fluid within frame
- Readable detail content: `960px` to `1120px`
- Right rail: `280px` to `320px`

## Page Templates

### List page

Use for:

- Changes
- Releases
- Scans
- Audit

Structure:

- Header
- Filter bar
- Result table or list
- Batch action bar when selection exists

### Detail page

Use for:

- Change Request
- Release
- Finding
- Policy rule

Structure:

- Title and actions
- Status strip
- Tabs
- Main content
- Sticky right rail

### Workspace page

Use for:

- Review workspace
- Deployment execution workspace

Structure:

- Toolbar
- Left pane
- Center work surface
- Right context pane

### Settings page

Use for:

- Policy configuration
- Environment rules
- Repository integration settings

Structure:

- Section nav
- Form or table body
- Sticky save bar

## Responsive behavior

- `>= 1440`: full desktop layout
- `1200 - 1439`: tighter rail spacing
- `960 - 1199`: right rail becomes drawer
- `< 960`: read-only or limited task mode

---

## Information Hierarchy

Each important page should render information in this order:

1. Object identity
2. Current state
3. Blocking reasons
4. Primary action
5. Secondary context
6. Historical detail

### Required header fields

For Change, Release, Finding, and Policy pages:

- Title
- Context metadata
- Status
- Updated time
- Primary action

### Required blocking treatment

If blocked, the page must show:

- Blocking summary at the top
- Gate or blocker count
- Direct links to each blocker
- Explicit unlock condition

Example:

```text
Blocked
1 critical finding and 2 required reviews are still open.
Resolve findings or request approval from Platform reviewers.
```

---

## Component Taxonomy

### Foundations

- Color tokens
- Typography tokens
- Spacing tokens
- Radius tokens
- Shadow tokens
- Motion tokens

### Primitive components

- Button
- IconButton
- Input
- Textarea
- Select
- Combobox
- Checkbox
- Radio
- Switch
- Tabs
- Badge
- Tooltip
- Popover
- DropdownMenu
- Modal
- Drawer
- Toast
- Divider
- Skeleton

### Structural components

- AppShell
- TopBar
- SideNav
- PageHeader
- ContextBar
- FilterBar
- DataTable
- DetailLayout
- RightRail
- StickyActionBar
- EmptyState

### Domain components

- StatusPill
- StatusDot
- MergeReadinessCard
- ReviewDecisionBar
- DiffViewer
- FileTree
- CheckRunList
- ApprovalChain
- GateSummary
- DeploymentStatusCard
- EnvironmentBadge
- RiskSummaryStrip
- FindingRow
- AuditTimeline
- RuleBlock

---

## Primitive Components

## Button

### Variants

- `primary`
- `secondary`
- `subtle`
- `danger`
- `ghost`

### Sizes

- `sm`
- `md`
- `lg`

### States

- default
- hover
- active
- focus-visible
- disabled
- loading

### Rules

- Only one `primary` button per local context
- `danger` only for destructive operations
- `ghost` only for low-emphasis utilities
- Min height `32px`
- Loading state keeps width stable

### Interaction

- Hover changes background or border only
- Focus uses visible outline, not only shadow
- Disabled state must provide reason when action is blocked

## Input

### Anatomy

- Label
- Field
- Helper text
- Error text
- Prefix or suffix

### Rules

- Label is always visible
- Placeholder is never the only label
- Error state uses text + border + optional icon
- Use `14px` body text

## Select and Combobox

### When to use Select

- Small static choices
- Environment pickers
- Sort order

### When to use Combobox

- Repository selection
- Reviewer assignment
- Large saved views

### Rules

- Multi-select selections must remain visible as chips or summary text
- Search within Combobox after 8 options or more

## Tabs

Use for peer content sections only.

Good:

- Overview
- Diff
- Checks
- Findings
- Audit

Bad:

- Stepper workflows
- Nested filter states

### Rules

- Active tab needs visible underline or background
- Tab switching should preserve page skeleton
- Avoid more than 6 top-level tabs before collapsing

## Modal

Use for:

- Approval confirmation
- Reject with reason
- Exception request
- Small create flows

Do not use for:

- Long logs
- Large diff viewing
- Multistep operational workflows

## Drawer

Use for:

- Secondary detail
- Right rail replacement on narrow screens
- Quick scan finding preview

## Toast

Use only for:

- Small success feedback
- Non-blocking failure feedback with next action

Do not use Toast as the only failure explanation for critical operations.

---

## Structural Components

## PageHeader

### Anatomy

- Title
- Metadata row
- Status area
- Primary action
- Secondary actions

### Layout

- Left: title and context
- Right: actions

### Rules

- Primary action always visible without scrolling
- Metadata never competes visually with title

## FilterBar

### Anatomy

- Search field
- Facet filters
- Saved view selector
- Reset action
- Sort control

### Rules

- Filter state must be visible and removable
- Multiple active filters must wrap cleanly
- Saved view naming uses concise operational language

## DataTable

### Purpose

Operational tables for dense, scan-friendly tasks.

### Row height

- Standard: `44px`
- Dense optional: `40px`
- Expanded row: `56px+`

### Column principles

- Left align by default
- Status near object name
- Timestamps right side
- Actions on hover or final column

### Table rules

- Support row selection
- Support batch action mode
- Do not use zebra stripes by default
- Use border separators, not cardized rows

## DetailLayout

```text
+-------------------------------------------+--------------------------------------+
| Main Content                               | Right Rail                           |
|                                            |                                      |
+-------------------------------------------+--------------------------------------+
```

### Rules

- Right rail remains sticky on desktop
- Main content owns tabs and long body
- Rail owns status, approvals, blockers, key metadata

## EmptyState

### Anatomy

- Title
- One-line explanation
- Single primary action
- Optional secondary link

### Rules

- No illustrations in core operational pages
- Avoid motivational copy

Example:

- `No pending reviews`
- `All reviews in this workspace have been completed.`
- `View recent changes`

## StickyActionBar

Use when a decision may happen after long scrolling.

Examples:

- Review decision
- Release approval
- Save policy changes

Rules:

- Appears only when needed
- Never covers critical content
- Contains primary and cancel actions

---

## Domain Components

## StatusPill

### Supported statuses

- Draft
- Open
- In Review
- Pending Approval
- Blocked
- Ready
- Approved
- Deploying
- Succeeded
- Failed
- Archived

### Visual rules

- Text always present
- Optional icon or dot
- Semantic color only
- Consistent mapping across all modules

### Mapping

```text
Draft -> neutral
Open -> info
In Review -> info
Pending Approval -> warning
Blocked -> danger
Ready -> success
Approved -> success
Deploying -> info
Succeeded -> success
Failed -> danger
Archived -> neutral
```

## StatusDot

Use in:

- Timelines
- Row summaries
- Environment health
- Child task lists

Never use it as the only explanation of a critical state.

## MergeReadinessCard

This component determines whether a change can move forward.

### Anatomy

- State title
- Summary sentence
- Readiness checklist
- Primary action
- Secondary action

### Content requirements

Must answer:

1. Can this merge now
2. What blocks it
3. Who can fix it
4. What action should be taken now

### Example

```text
Blocked
1 critical finding and 2 required reviews are still open.

[ ] Required checks passed
[ ] Platform review approved
[x] Branch up to date
[ ] Critical findings resolved

Primary: Request review
Secondary: View blocking findings
```

### Interaction rules

- Checklist items are clickable
- Each blocking item deep-links to its resolution context
- Primary CTA changes with state

## ReviewDecisionBar

### Actions

- Comment
- Request changes
- Approve
- Merge

### Rules

- Action priority depends on state
- If blocked, `Merge` becomes disabled with reason
- If approval is allowed, `Approve` remains visible
- Dangerous merge bypass requires modal + reason

## DiffViewer

### Required modes

- Unified
- Split

### Required features

- File tree synchronization
- Line numbers
- Inline comments
- Syntax highlighting
- Context folding
- Scan highlight overlays

### Visual rules

- Added and removed lines use soft backgrounds
- Comment anchors stay visible on hover
- File headers remain sticky when scrolling long diffs

## FileTree

### Required metadata

- File name
- Change type
- Comment count
- Risk indicator

### Rules

- Support collapse by directory
- Support filter by changed, commented, risky
- Active file visibly selected

## CheckRunList

### Row fields

- Check name
- Type
- State
- Duration
- Updated time
- View logs
- Retry

### Rules

- Failures sort first
- Same provider checks may group
- Long logs stay out of main page body

## ApprovalChain

### States

- Pending
- Approved
- Rejected
- Skipped
- Expired
- Bypassed

### Row fields

- Approver
- State
- Timestamp
- Reason
- Source role

### Interaction

- Rejection expands reason inline
- Bypass is always visually distinct from approval

## GateSummary

The universal blocker summary component.

### Gate types

- Review gate
- Check gate
- Scan gate
- Environment gate
- Release window gate
- Policy gate

### Rules

- Sorted by severity
- Every gate has resolution text
- Every gate deep-links to the blocking object

## DeploymentStatusCard

### Anatomy

- Status dot
- Environment
- State label
- Commit or release ref
- Actor
- Started time
- View logs

### Layout behavior

- Compact in list mode
- Expanded in detail mode

### Rules

- Healthy state is concise
- Failure state exposes retry or rollback action

## EnvironmentBadge

### Variants

- `dev`
- `test`
- `staging`
- `prod`

### Rules

- Use restrained neutral styles with slight semantic variation
- `prod` can use stronger border or text treatment, not bright fills

## RiskSummaryStrip

Use near page top for scan and release contexts.

Fields:

- Critical count
- High count
- Medium count
- Accepted risk count

Rules:

- Use text and count, not only colored chips
- Clicking a count filters the finding list

## FindingRow

### Fields

- Severity
- Rule category
- Short title
- File or repository
- Linked change
- Assignee
- Current state
- Quick actions

### Quick actions

- Assign
- Mark fixed
- Dismiss
- Accept risk

### Rules

- Severity is visible without entering detail
- Accepted risk needs a reason capture flow

## AuditTimeline

### Fields

- Actor
- Action
- Object
- Reason
- Time
- Before or after snapshot link

### Rules

- Strictly chronological
- Minimal but scan-friendly
- Bypass and override events visually elevated

## RuleBlock

### Fields

- Rule name
- Scope
- Condition
- Enforcement
- Exception path
- Last updated

### Rules

- Written in plain operational language
- Must show what happens when rule is violated

---

## Interaction Patterns

## Review Pattern

Recommended order of operations:

1. See readiness state
2. Scan file tree and hotspots
3. Review diff
4. Check automated results
5. Decide

### UI requirements

- Review decision remains accessible
- File tree, diff, and comment panel are linked
- New commits visibly invalidate stale approval when applicable

## Approval Pattern

Use for:

- Release approvals
- Exception approvals
- Policy bypass approvals

### Required content

- What is being approved
- Why approval is required
- Risk summary
- Impact scope
- Approval decision

### High-risk requirements

- Reason input
- Audit disclosure
- Permission statement

## Blocking Pattern

Blocked is a first-class system state.

### Required UI treatment

- Top summary strip
- Disabled or downgraded primary action
- Resolution path for each blocker
- Right rail gate summary

## Bulk Action Pattern

Use for:

- Assign findings
- Update finding state
- Re-run checks
- Apply labels or owners

### Rules

- Batch bar appears only after selection
- Selection count always visible
- Destructive bulk actions require confirmation

## Search Pattern

Two levels:

- Global search: cross-object navigation
- Local search: within table, file tree, diff, or findings

Suggested structured filters:

- `repo:payment state:blocked reviewer:me`
- `env:prod approval:pending`
- `severity:critical state:open`

## Notification Pattern

### Notification classes

- Success feedback
- Attention needed
- Blocking event
- Passive update

### Rules

- Critical failures appear in notification center and local page state
- Passive updates should not interrupt the flow
- Release failure, rejected approval, and critical finding creation are high priority

---

## State Design

## Global semantic states

```ts
type SemanticState =
  | "neutral"
  | "info"
  | "success"
  | "warning"
  | "danger"
  | "disabled";
```

## Empty state

Format:

- One-line conclusion
- One-line explanation
- One action

Examples:

- `No pending approvals`
- `All required release approvals have been completed.`
- `View recent releases`

## Loading state

Rules:

- Use skeletons
- Preserve page shell
- Preserve header
- Use local refresh over whole-page refresh

## Error state

Three types:

1. Temporary failure
2. Permission issue
3. Missing object

Examples:

- `Failed to load check results. Retry or open raw logs.`
- `You don't have permission to edit this rule.`
- `This change request was not found.`

## Disabled state

Disabled controls must explain why.

Examples:

- `Merge disabled until required checks pass`
- `Deploy disabled outside production window`

---

## Accessibility

### Required rules

- Color is never the only status signal
- All interactive controls support keyboard access
- Focus-visible is explicit and consistent
- Text contrast meets WCAG AA
- Icon-only buttons have accessible labels

### Modal and drawer behavior

- Focus moves into the overlay on open
- Focus returns to trigger on close
- Escape closes unless action is irreversible and active

### Table and diff behavior

- Tables expose header semantics
- Expand and collapse controls expose state
- Comment controls are keyboard reachable

---

## Frontend Implementation Mapping

## Token layer

Implement these first:

- Color tokens
- Typography tokens
- Spacing tokens
- Radius tokens
- Shadow tokens
- Motion tokens
- Z-index tokens

Suggested z-index:

```css
:root {
  --z-dropdown: 1000;
  --z-sticky: 1100;
  --z-drawer: 1200;
  --z-modal: 1300;
  --z-toast: 1400;
}
```

## Component API layer

Prefer semantic APIs.

Good:

```tsx
<Button variant="danger" />
<StatusPill status="blocked" />
<GateSummary gates={gates} />
```

Bad:

```tsx
<Button red />
<Tag green />
<Panel warning />
```

## Domain pattern layer

Create shared composites for:

- `ReviewLayout`
- `ApprovalModal`
- `MergeReadinessCard`
- `DeploymentStatusCard`
- `FindingTable`
- `AuditTimeline`

## Shared state dictionary

Status text, color, icon, and behavior must resolve from one shared map.

---

## Component Priorities

## P0

- Button
- Input
- Select
- Combobox
- Tabs
- Modal
- Drawer
- Toast
- DataTable
- EmptyState
- Skeleton
- StatusPill
- MergeReadinessCard
- ReviewDecisionBar
- DiffViewer
- CheckRunList
- ApprovalChain
- GateSummary
- DeploymentStatusCard
- FindingRow

## P1

- Command surface
- Saved views
- Batch action bar
- RuleBlock
- AuditTimeline
- Advanced filters

---

## Sources

- Primer: https://primer.style/
- Primer page layout and primitives entry points: https://primer.style/product/primitives and https://primer.style/product/components/page-layout
- HashiCorp Helios: https://helios.hashicorp.design/
- HashiCorp button and foundations entry points: https://helios.hashicorp.design/components/button and https://helios.hashicorp.design/foundations
- Vercel Geist: https://vercel.com/geist/introduction
- GitHub protected branches: https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches
- GitHub code scanning: https://docs.github.com/en/code-security/concepts/code-scanning/code-scanning
- GitHub deployments and environments: https://docs.github.com/en/actions/reference/workflows-and-actions/deployments-and-environments
- Design.md structure reference: https://getdesign.md/mongodb/design-md
- Community examples: https://github.com/VoltAgent/awesome-design-md

---

## Final Direction

This design system should ship as a neutral, high-density, governance-aware UI layer for DevOps work.

Its defining characteristics should be:

- precise color semantics
- stable layout shells
- operationally explicit status handling
- reusable domain components for review, release, and risk
- friction patterns that scale with risk

If implemented correctly, users should always be able to answer three questions immediately:

1. What is the state.
2. What is blocking progress.
3. What action is allowed now.
