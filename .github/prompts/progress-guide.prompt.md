# AI Prompt: Guiding Updates for `document/progress.md`

## 1. Objective

This prompt guides an AI assistant in accurately and consistently updating the project's progress tracking document, located at `document/progress.md`. The goal is to maintain a real-time, structured overview of project advancements, tasks, and overall health.

## 2. Core Document: `document/progress.md`

- **Location**: `document/progress.md`
- **Purpose**: To provide a centralized, AI-managed record of current project progress, active tasks, upcoming milestones, and a general assessment of project health.
- **Key Characteristic**: This document is **self-documenting**. Its precise structure, including YAML frontmatter, section formats, and table column definitions, is explicitly defined within a commented block at the beginning of the `document/progress.md` file itself. **Always refer to this embedded definition before making any updates.**

## 3. AI Update Responsibilities & Workflow

When tasked with updating `document/progress.md` (e.g., based on new information from user interactions, version control commits, task management systems, or other inputs), the AI assistant must adhere to the following:

### 3.1. Read and Adhere to Embedded Structure Definition

- **Crucial First Step**: Before any modification, parse and understand the structure definition provided in the initial comment block of `document/progress.md`. This definition is the single source of truth for formatting.

### 3.2. Update YAML Frontmatter

- **`updated`**: Change this field to the current date (YYYY-MM-DD) of the update.
- **`version`**: If the update corresponds to a new project iteration (e.g., start of a new Sprint, new version release), update this field accordingly. Otherwise, leave it unchanged.
- **`ai_managed`**: This should remain `true`.
- **`title`**: This should remain `\"项目进度\"`.

### 3.3. Update "Overall Progress" Section

- **`## 总体进度`**: This section requires updates to the following list items:
  - **`当前焦点` (Current Focus)**: Reflect the primary objective or area of concentration for the current project phase.
  - **`下一里程碑` (Next Milestone)**: Update with the next significant checkpoint, deliverable, or phase, including its target date.
  - **`整体健康度` (Overall Health)**: Assess and update the project's health status (`Green`, `Yellow`, `Red`) based on task completion rates, delays, identified blockers, and overall sentiment from available data. Provide a brief justification if changing to `Yellow` or `Red`.

### 3.4. Update "Task List" Table

- **`## 任务清单 (Tasks)`**: This Markdown table is the core of the progress tracking.
  - **Adding New Tasks**:
    - Assign a unique `ID` (e.g., `TASK-XXX`, `DOC-XXX`).
    - Provide a clear `任务描述 (Description)`.
    - Assign a `负责人 (Assignee)` (e.g., `@username`, `AI`, `Frontend Team`).
    - Set initial `状态 (Status)` (usually `To Do`).
    - Define a `截止日期 (Due Date)`.
    - Set a `优先级 (Priority)` (`High`, `Medium`, `Low`).
    - If applicable, link to `关联PRD (Related PRD)` (e.g., `prd-filename.md#section-ref`).
    - If applicable, pre-generate or leave space for `关联报告条目 (Related Report Entry)` (e.g., `SR-TASK-XXX`).
  - **Updating Existing Tasks**:
    - Modify `状态 (Status)` as tasks progress (e.g., `In Progress (X%)`, `Done`, `Blocked`, `Pending Review`, `QA`, `Deployed`). Ensure the status matches the defined enums in `document/progress.md`.
    - Update completion percentages for `In Progress` tasks.
    - Adjust `截止日期 (Due Date)` if schedules change.
    - Update `负责人 (Assignee)` if task ownership changes.
    - Add/update `关联报告条目 (Related Report Entry)` when corresponding entries are made in `status-report.md`.
  - **Removing Tasks**: Only remove tasks if they were created in error or are explicitly cancelled and deemed no longer relevant for tracking. Completed tasks should remain with `Status: Done`.
  - **Table Integrity**: Ensure the Markdown table formatting remains correct.

### 3.5. Maintain Consistency

- Use the exact column names and status enums as defined in `document/progress.md`.
- Ensure dates are in YYYY-MM-DD format.
- Maintain clear and concise language.

## 4. Information Sources for Updates

The AI should be prepared to synthesize information from various sources to update `progress.md`, including but not limited to:

- Direct user instructions.
- Analysis of new or updated PRDs, module documents, or other project documentation.
- Information from version control (commit messages, branch merges).
- (If integrated) Updates from external task management tools (Jira, Trello, etc.).
- Summaries of meetings or discussions.

## 5. Example Scenario

**User Prompt**: \"We\'ve just started working on the new user authentication UI. Please add this to the progress doc. It\'s high priority and assigned to @frontend_dev, due next Friday. This relates to PRD-005.\"

**AI Actions (Simplified)**:

1. Read structure from `document/progress.md`.
2. Update `updated` date in YAML.
3. Add new row to \"Task List\":
   - `ID`: (Generate new, e.g., `TASK-008`)
   - `任务描述`: \"Implement new user authentication UI\"
   - `负责人`: \"@frontend_dev\"
   - `状态`: \"To Do\"
   - `截止日期`: (Calculate next Friday\'s date)
   - `优先级`: \"High\"
   - `关联PRD`: \"prd-005.md\" (or more specific if PRD-005 is a file)
   - `关联报告条目`: (Leave blank or note for future update)
4. Potentially update `当前焦点` if this is a major new focus.

## 6. Final Check

Before concluding the update, mentally review if the changes accurately reflect the new information and adhere to all structural and formatting guidelines derived from `document/progress.md` itself.
