# Technical Requirements Document (TRD)

**Purpose:** This document details the exact technical components that need to be built for the project. It is intended for a developer (volunteer or paid).

---

## Part 1: The Comparison Script

*   **Objective:** To automatically compare the data entry from Transcriber A and Transcriber B for the same record and flag any discrepancies.
*   **Logic:**
    *   The script will take two data records (Batch_ID_A, Batch_ID_B) as input.
    *   It will perform a field-by-field comparison.
    *   If `Record_A.field_1` does not equal `Record_B.field_1`, the script will:
        1.  Create a 'Discrepancy' record.
        2.  Log the `Batch_ID`, the `field_name`, `value_A`, and `value_B`.
        3.  Assign the discrepancy to the appropriate Team Lead for manual resolution.
    *   The script should be case-insensitive for text fields but case-sensitive for specific identifiers if noted in the schema.

---

## Part 2: The Database

*   **Technology:** PostgreSQL
*   **Schema:** The database schema must be built to the exact specifications outlined in **Appendix A: Data Schema / Data Dictionary**.
*   **Hosting:** [Specify hosting provider, e.g., AWS RDS, Heroku, etc.]

---

## Part 3: The Public Website

*   **Objective:** To create a simple, fast, and searchable public interface for the verified data.

*   **User Stories (Features):**

    *   **US-01: Search by Last Name**
        *   **As a user,** I want to enter a last name into a search box.
        *   **So that** I can see a list of all records matching that last name.

    *   **US-02: Filter Results**
        *   **As a user,** I want to filter the search results by `County` and a `Date Range`.
        *   **So that** I can narrow down my search to the most relevant records.

    *   **US-03: View Record Details**
        *   **As a user,** I want to be able to click on a result from the list.
        *   **So that** I can see all the publicly-available fields for that specific record.

    *   **US-04: Static 'About' Page**
        *   **As a user,** I want to be able to navigate to an 'About' page.
        *   **So that** I can understand the project's mission, methodology, and the context of the records.

    *   **US-05: Static 'Data' Page**
        *   **As a user,** I want to be able to navigate to a 'Data' page.
        *   **So that** I can view the public version of the data dictionary and understand what each field means.
