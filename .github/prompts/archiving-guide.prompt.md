# AI Prompt: Guiding Archiving of Progress and Status Reports

## 1. Objective

This prompt guides an AI assistant in the systematic archiving of `document/progress.md` and `document/status-report.md`. This process typically occurs upon the completion of a project version or a significant milestone, ensuring a historical record of project states.

## 2. Core Documents & Locations

- **Source Documents**:
  - `document/progress.md`
  - `document/status-report.md`
- **Archive Destination Directory**:
  - `document/archive/`
- **Archive Index File (to be updated)**:
  - `document/archive/_index.md`
- **Key Characteristic of `document/archive/_index.md`**: This document is self-documenting. Its structure, including YAML frontmatter and table definitions, is defined within `document/archive/_index.md` itself (or was recently established based on `document/document-guide.md`). **Always refer to its defined structure before updating.**

## 3. AI Archiving Responsibilities & Workflow

When instructed to archive the current progress and status reports (usually with a specified version number):

### 3.1. Identify Version Number

- The user prompt should provide a version number (e.g., "v1.0.0", "Sprint-3-End"). Clarify with the user if it's missing.

### 3.2. Create Archive Files

- **Naming Convention**:
  - `document/archive/v[VersionNumber]_progress.md`
  - `document/archive/v[VersionNumber]_status-report.md`
    (Replace `[VersionNumber]` with the actual version, e.g., `v1.0.0_progress.md`)
- **Action**:
  1.  Read the entire current content of `document/progress.md`.
  2.  Create a new file in `document/archive/` with the correct name (e.g., `v[VersionNumber]_progress.md`) and write the copied content into it.
  3.  Read the entire current content of `document/status-report.md`.
  4.  Create a new file in `document/archive/` with the correct name (e.g., `v[VersionNumber]_status-report.md`) and write the copied content into it.

### 3.3. Update Archive Index File (`document/archive/_index.md`)

- **Crucial Step**: First, read and understand the existing structure of `document/archive/_index.md`, particularly its "归档清单" (Archive List) table format.
- **Update YAML Frontmatter**:
  - Set the `updated` field to the current date (YYYY-MM-DD).
- **Add New Entry to "归档清单" Table**:
  - Add a new row to the table with the following information:
    - **`版本号` (Version Number)**: The version number used for archiving (e.g., `v1.0.0`).
    - **`进度报告 (链接)` (Progress Report Link)**: The relative path to the newly archived progress file (e.g., `v[VersionNumber]_progress.md` or `archive/v[VersionNumber]_progress.md` depending on how links are structured in the index).
    - **`状态报告 (链接)` (Status Report Link)**: The relative path to the newly archived status file (e.g., `v[VersionNumber]_status-report.md` or `archive/v[VersionNumber]_status-report.md`).
    - **`归档日期` (Archiving Date)**: The current date (YYYY-MM-DD).
- **Table Integrity**: Ensure the Markdown table formatting remains correct.

## 4. Information Sources

- User instruction, including the version number for the archive.
- Current content of `document/progress.md`.
- Current content of `document/status-report.md`.
- Existing structure and content of `document/archive/_index.md`.

## 5. Example Scenario

**User Prompt**: "We have just released version v0.9.1. Please archive the current progress and status reports."

**AI Actions (Simplified)**:

1.  **Identify Version**: `v0.9.1`.
2.  **Create Archive Files**:
    - Copy content of `document/progress.md` to `document/archive/v0.9.1_progress.md`.
    - Copy content of `document/status-report.md` to `document/archive/v0.9.1_status-report.md`.
3.  **Update `document/archive/_index.md`**:
    - Update `updated` date in YAML to current date.
    - Add a new row to the "归档清单" table:
      `| v0.9.1 | v0.9.1_progress.md | v0.9.1_status-report.md | 2025-05-21 |`
      _(Assuming links in `_index.md` are relative to the `archive` directory itself. Adjust path if links are relative to project root, e.g. `archive/v0.9.1_progress.md`)_

## 6. Final Check

- Verify that new archive files are created in the `document/archive/` directory with the correct names and content.
- Confirm that `document/archive/_index.md` is updated with the correct new entry and its YAML `updated` date is current.
- Ensure no accidental modifications were made to the live `document/progress.md` or `document/status-report.md` (unless explicitly part of a post-archiving reset, which is not covered by this specific prompt).
