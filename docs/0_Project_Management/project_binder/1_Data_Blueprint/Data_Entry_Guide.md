# Data Entry Guide

**Purpose:** This is the human-readable version of the Data Schema, designed to train volunteers. This is the cornerstone of the Volunteer Onboarding Kit.

---

## Section 1: Getting Started

### How to Get an Assignment

*Instructions on how volunteers are assigned a batch of records.*

### How to Open the Data Entry Tool

*Link and instructions for accessing the data entry form or software.*

## Section 2: Field-by-Field Guide

This is your primary reference for entering data. Please follow these instructions carefully. When in doubt, check the `needs_review` box and add a comment in the `notes` field.

---

*   **Field: Source Ledger ID (`source_ledger_id`)**
    *   **What to enter:** The unique ID of the ledger volume you are working from. This will be provided to you with your assignment (e.g., `A0629_Vol_B`).
    *   **Common issues:** If you are unsure of the Ledger ID, please ask your Team Lead. It is critical for tracking our sources.

*   **Field: Source Page Number (`source_page_number`)**
    *   **What to enter:** The page number of the record within the ledger.
    *   **Common issues:** If a page is unnumbered, do your best to estimate based on the surrounding pages and make a note in the `notes` field.

*   **Field: Applicant's First Name (`given_name`)**
    *   **What to enter:** The first or given name(s) of the person applying for clemency.
    *   **Common issues:**
        *   If there are multiple first names (e.g., "John William"), separate them with a semicolon: `John;William`.
        *   If the name is difficult to read, make your best guess and set the `needs_review` flag to `True`.
        *   If the name is completely illegible, leave this field blank and set `needs_review` to `True`.

*   **Field: Applicant's Last Name (`family_name`)**
    *   **What to enter:** The last or family name of the person applying for clemency.
    *   **Common issues:** Same as the first name field. If illegible, leave blank and set `needs_review` to `True`.

*   **Field: Application Date (`application_date`)**
    *   **What to enter:** The date the application was filed. Please use `YYYY-MM-DD` format.
    *   **Common issues:** If only a month and year are given, use the first day of the month (e.g., `1885-03-01`). If only a year is given, use the first day of the year (e.g., `1885-01-01`).

*   **Field: County of Conviction (`conviction_county`)**
    *   **What to enter:** The county where the conviction occurred.
    *   **Action:** You **must** use the official name from the **`Controlled_Vocabularies.md`** document. For example, even if the ledger says "Brooklyn," you must enter `Kings (Brooklyn)`.
    *   **Common issues:** If the county is not on the list or is illegible, leave the field blank, set `needs_review` to `True`, and write the original text in the `notes` field.

*   **Field: Original Crime Text (`crime_original_text`)**
    *   **What to enter:** Transcribe the description of the crime **exactly as it is written** in the ledger, preserving original spelling and capitalization.
    *   **Why:** This captures the raw data. Another team member will categorize it later.

*   **Field: Type of Crime (`crime_type`)**
    *   **What to enter:** The general category of the crime.
    *   **Action:** Choose one of the three options from the **`Controlled_Vocabularies.md`** document: `Felony`, `Misdemeanor`, or `Unknown`.
    *   **Common issues:** Do not guess. If you are not absolutely sure, select `Unknown`.

*   **Field: Sentence Term (`sentence_term`)**
    *   **What to enter:** The length of the sentence as written in the ledger (e.g., `5 years`, `Life`, `10 months`).

*   **Field: Prison Name (`prison_name`)**
    *   **What to enter:** The name of the prison or penitentiary.
    *   **Action:** Whenever possible, use an official name from the **`Controlled_Vocabularies.md`** document. If the name is not on the list, enter it as written and flag it in the `notes` field so we can add it to the list.

*   **Field: Clemency Decision (`decision_type`)**
    *   **What to enter:** The final outcome of the application.
    *   **Action:** This is a critical field. You **must** use one of the official terms from the **`Controlled_Vocabularies.md`** document (e.g., `Pardon`, `Commutation`, `Denied`).

*   **Field: Decision Date (`decision_date`)**
    *   **What to enter:** The date the decision was made. Please use `YYYY-MM-DD` format.
    *   **Common issues:** Same as `application_date`.

*   **Field: Notes (`notes`)**
    *   **What to enter:** Use this field to record any other relevant details, such as conditions of a pardon, names of petitioners, or to flag issues for the review team. Be concise but clear.

*   **Field: Needs Review (`needs_review`)**
    *   **What to enter:** A simple `True` or `False` value (this may be a checkbox in the data entry tool).
    *   **Action:** Set this to `True` if you are uncertain about **any** piece of data in the record. This is the most important way to ensure data quality.

## Section 3: Paleography Primer (How to Read Old Handwriting)

*Tips, examples, and guides for deciphering difficult handwriting from the historical period.*

*   **Commonly Confused Letters:** (e.g., 's' and 'f')
*   **Examples of Numbers:** ...
*   **Glossary of Abbreviations:** ...
