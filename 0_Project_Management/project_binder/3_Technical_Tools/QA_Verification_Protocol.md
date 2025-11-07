# Quality Assurance (QA) & Verification Protocol

**Purpose:** To define the human process for ensuring the highest possible data accuracy by systematically resolving discrepancies identified by the comparison script.

---

## 1. The Discrepancy Resolution Workflow

*   **Trigger:** The automated comparison script flags a mismatch between Transcriber A's and Transcriber B's entry for a specific field in a record.
*   **Assignment:** The flagged record is automatically assigned to the designated Team Lead in the Master Assignment Tracker.

*   **Team Lead's Process:**
    1.  **Review the Discrepancy:** The Team Lead will open the record and view the two different values (`value_A` and `value_B`).
    2.  **Consult the Source Document:** The Team Lead will carefully examine the original scanned document to determine the correct value. This is the primary method of resolution.
    3.  **Correct the Record:** The Team Lead will enter the correct value into the final data field, overwriting the incorrect entries.
    4.  **Mark as Resolved:** The Team Lead will update the record's status to "Verified" in the Master Assignment Tracker.

---

## 2. The "Three-Way Tie-Breaker" (Handling Ambiguity)

This protocol is invoked when the source document itself is ambiguous, and it is unclear which transcriber (if either) was correct.

*   **Scenario:** The handwriting is illegible, the document is damaged, or the entry is inherently contradictory.
*   **Protocol:**
    1.  The Team Lead will first consult the **Paleography Primer** and any other project resources.
    2.  If still unclear, the Team Lead will make a **judgment call** based on their experience and contextual clues.
    3.  The Team Lead will enter the chosen value and **must** add a note in a dedicated `resolution_notes` field for that record, explaining the ambiguity and the reason for their choice (e.g., *"Handwriting for last name is unclear. Appears to be 'Smith' but could be 'Smyth'. Chose 'Smith' based on common spelling of the era."*).
    4.  The `needs_review` flag for this record will be set to **True**.

---

## 3. Escalation Path

Team Leads should escalate issues to the Project Leader under the following circumstances:

*   **Systemic Errors:** If a Team Lead notices the same type of error occurring repeatedly across different records or volunteers, suggesting a flaw in the Data Entry Guide or training.
*   **Sensitive Content:** Discovery of unusually sensitive or disturbing content that may require a specific ethical review not covered by the existing policy.
*   **Technical Issues:** If the data entry tool or comparison script is not functioning as expected.

---

## 4. Project Leader Spot-Checks

*   **Purpose:** To ensure the QA process itself is effective and that Team Leads are making consistent, high-quality judgments.
*   **Schedule:** The Project Leader will conduct a random audit of **2%** of all records marked as "Verified" on a **monthly basis**.
*   **Process:** The Project Leader will review the original source, the final value, and any `resolution_notes` to ensure the protocol was followed correctly. Feedback will be provided to Team Leads as needed.
