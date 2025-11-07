# Double-Entry Verification Workflow

**Purpose:** This document outlines the step-by-step process for ensuring the highest possible data accuracy through double-entry verification. This workflow is primarily managed by the Team Leads.

---

## Workflow Roles

*   **Transcriber A:** The first volunteer to transcribe a record.
*   **Transcriber B:** The second volunteer to transcribe the *same* record, without seeing Transcriber A's work.
*   **Team Lead:** The individual responsible for comparing the two transcriptions and resolving any discrepancies.

---

## The 5-Step Process

### Step 1: Assignment
1.  The Team Lead assigns a specific ledger page or batch of records to **Transcriber A**.
2.  The status of these records in the `Master_Assignment_Tracker.md` is marked as `Assigned_A`.

### Step 2: First Transcription (Entry A)
1.  **Transcriber A** completes the data entry for the assigned records.
2.  Upon completion, Transcriber A notifies the Team Lead.
3.  The Team Lead updates the record status to `Transcription_A_Complete`.

### Step 3: Second Transcription (Entry B)
1.  The Team Lead assigns the **exact same** batch of records to **Transcriber B**. It is critical that Transcriber B cannot see Transcriber A's entries.
2.  The record status is updated to `Assigned_B`.
3.  **Transcriber B** completes the data entry.
4.  Upon completion, Transcriber B notifies the Team Lead.
5.  The Team Lead updates the record status to `Transcription_B_Complete`.

### Step 4: Comparison
1.  The Team Lead now has two separate entries for each record.
2.  The Team Lead (or an automated script) compares Entry A and Entry B for each field.
    *   **If all fields match perfectly:** The record is considered verified. Proceed to Step 5.
    *   **If there are any mismatches:** The record requires manual review. Proceed to Step 5.

### Step 5: Verification & Correction
1.  **For matching records:**
    *   The Team Lead updates the `Final_Status` in the tracker to `Verified`.
    *   The process for this record is complete.

2.  **For mismatched records:**
    *   The Team Lead carefully reviews both Entry A and Entry B against the original source document (the scanned ledger page).
    *   The Team Lead determines the correct entry and creates a final, corrected version.
    *   The Team Lead updates the `Final_Status` to `Verified (Corrected)`.
    *   **Optional but Recommended:** The Team Lead provides gentle feedback to the transcriber(s) who made the error, treating it as a learning opportunity (e.g., "Just a heads-up, on page 5, the year was 1886, not 1885. Easy mistake to make!"). This helps improve transcriber accuracy over time.

This structured process is the core of our quality assurance. It ensures that every piece of data is reviewed by at least two sets of eyes, making our final database reliable and trustworthy for researchers.
