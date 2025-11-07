# Appendix A: Data Schema / Data Dictionary

**Purpose:** This is the single most important technical document of the project. It is the definitive blueprint for the database. It is not human-readable; it is a technical spec.

---

| Field Name (Internal) | Field Label (Human) | Data Type | Description | Rules & Examples | Required? | Controlled Vocabulary? | Dublin Core Mapping |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| `source_ledger_id` | Source Ledger ID | TEXT | The unique identifier for the archival ledger volume. | e.g., 'A0629_Vol_B' | Yes | No | `dc:source` |
| `source_page_number` | Source Page Number | INTEGER | The page number within the ledger where the record is found. | | Yes | No | `dc:source` |
| `given_name` | Applicant's First Name | TEXT | The given name of the individual petitioning for clemency. | If multiple names, separate with a semicolon. If illegible, leave blank and check 'Needs_Review'. e.g., 'John;William' | Yes | No | `dc:creator` |
| `family_name` | Applicant's Last Name | TEXT | The family name of the individual petitioning for clemency. | | Yes | No | `dc:creator` |
| `application_date` | Application Date | DATE | The date the application was filed, in YYYY-MM-DD format. | | Yes | No | `dc:date` |
| `conviction_county` | County of Conviction | TEXT | The county where the individual was convicted. | Use a standardized list of NYS counties. | Yes | Yes | `dc:coverage` |
| `crime_original_text` | Original Crime Text | TEXT | The exact, verbatim description of the crime from the ledger. | Transcribe exactly as written. | Yes | No | `dc:description` |
| `crime_type` | Type of Crime | TEXT | The category of the crime. | Based on `crime_original_text`. | Yes | For crime_type, must be one of: [Felony, Misdemeanor, Unknown]. | `dc:subject` |
| `sentence_term` | Sentence Term | TEXT | The length of the sentence. | e.g., '5 years', 'Life' | No | No | `dc:description` |
| `prison_name` | Prison Name | TEXT | The name of the prison or penitentiary. | | No | Yes (standardize names) | `dc:coverage` |
| `decision_type` | Clemency Decision | TEXT | The final outcome of the application. | | Yes | Must be one of: [Pardon, Commutation, Reprieve, Restoration, Denied, Term Expired, Other]. | `dc:rights` |
| `decision_date` | Decision Date | DATE | The date the clemency decision was made, in YYYY-MM-DD format. | | No | No | `dc:date` |
| `notes` | Notes | TEXT | For any other relevant details, such as conditions of a pardon or names of petitioners. | | No | No | `dc:description` |
| `needs_review` | Needs Review | BOOLEAN | Flag if the record has illegible or questionable data. | This is internal admin data; not mapped. | Yes | True/False | `N/A` |
