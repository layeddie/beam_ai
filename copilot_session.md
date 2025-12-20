# CoPilot Session Guidelines

## Purpose
This document outlines the guidelines to ensure full conversations and interactions related to the project are consistently appended or preserved, minimized risk of truncations, and maintained structured logs for posterity.

## Key Practices

1. **Complete Conversation Archival**:
   - Ensure that every interaction made by the team and contributors is recorded comprehensively.
   - Review the logs periodically for any signs of partial or missing interactions. If any are found, rectify immediately.

2. **Appending New Interactions**:
   - Always append new interactions to the previous ones within the established sequence.
   - Avoid overwriting historical data. Historical records provide valuable context and rationale for project decisions.

3. **Avoiding Truncations**:
   - Be vigilant about the size limits of interaction archives to ensure no data loss.
   - Implement chunking of large interactions and log them sequentially if required.

## Structured Logging Guidelines

To facilitate analysis, debugging, and clear retrospective insights:

1. **Log Format**:
   - Use the following structure for each log entry:
     ```
     [YYYY-MM-DD HH:MM:SS UTC] <User>: <Interaction>
     ```
   - e.g., `2025-12-20 17:31:24 UTC layeddie: Updated copilot_session.md`.

2. **Metadata**:
   - Include relevant metadata (e.g., created/updated files, tool used, decision rationale).

3. **Consistency**:
   - Use standardized terminologies and structures to describe interactions.

4. **Storage**:
   - Log files must be systematic and categorized under session folders. Use naming conventions that identify the session name and date.

## Responsibilities
- The contributors and maintainers of this project must collaborate to enforce these practices and ensure logs are up-to-date.
- Each logged session must undergo a quick review by another team member to validate its accuracy.

## Conclusion
Following these guidelines will help the team maintain a reliable and useful repository of project interactions, benefiting both current and future contributors.