# NYS Executive Clemency Archive - Project Notes

This document will be used to keep track of our discussions, decisions, and action items.

## Next Steps (2025-11-06)

*   [x] Define data schema based on sample ledger.
*   [x] Discuss database technology options.
    *   **Decision:** We will use PostgreSQL for this project.
*   [ ] Set up the development environment.

## Project Leadership & Strategy

This section outlines the key strategic areas for the project leader to focus on during the planning phase.

### 1. Core Responsibilities of Project Leader
-   **Data Custodian:** Ensure all decisions prioritize the quality, accuracy, and consistency of the data. The data schema is the project's constitution.
-   **Mission-Driven Technology:** Select and use technology as a tool to serve the project's goal of making information accessible, not for its own sake.
-   **Volunteer Management:** Create a clear, positive, and productive environment for volunteers, as they are the engine for the data entry phase.
-   **Scope Management:** Maintain a clear distinction between 'must-have' and 'nice-to-have' features to stay on track and within budget.

### 2. Key Strategic Decisions
-   **Data Entry Workflow:** Design a clear, step-by-step process for transcribing and verifying data. A double-entry system is highly recommended for accuracy.
-   **Hosting & Maintenance:** Determine the long-term hosting plan for the database and website. This has budget and sustainability implications.
-   **Data Privacy & Ethics:** Establish a formal policy for handling sensitive information, including PII (Personally Identifiable Information) and details of criminal cases.
-   **Legal & Copyright:** Confirm in writing with the NYS Archives any use restrictions or copyright on the source materials.

### 3. Volunteer Organization & Management
-   **Onboarding Kit:** Develop a 'Data Entry Kit' for volunteers, including a detailed Data Entry Guide based on the schema, clear work assignments, and access to the data entry tool.
-   **Tiered Roles:** Consider creating roles like 'Transcriber,' 'Verifier,' and 'Team Lead' to match volunteers' skills and experience.
-   **Communication Plan:** Establish a regular communication channel (e.g., newsletter, Slack) to keep volunteers engaged and informed.
*   [ ] Outline high-level platform architecture.
*   [ ] Brainstorm volunteer workflow for data entry.

## Data Schema (Final Draft v1)

Here is a proposed structure for the data based on the spreadsheet headers. This will help organize the information for the database.

### 1. Person
-   `PersonID` (Unique Identifier)
-   `Name`

### 2. Case
-   `CaseID` (Unique Identifier)
-   `PersonID` (links to Person table)
-   `Crime`
-   `TrialPlace`
-   `TrialDate`
-   `SentenceDate`
-   `SentenceMinYears`
-   `SentenceMinMonths`
-   `SentenceMinDays`
-   `SentenceMaxYears`
-   `SentenceMaxMonths`
-   `SentenceMaxDays`
-   `TermExpiresDate`
-   `FineAmount`
-   `EndsWithFine` (Boolean)
-   `EndsWithoutFine` (Boolean)
-   `PrisonReceptionDate`
-   `CaseType` (e.g., Capital, Life, Less Than Life)

### 3. Clemency Application
-   `ApplicationID` (Unique Identifier, from `Application #`)
-   `CaseID` (links to Case table)
-   `EventType`
-   `RecordDate`
-   `ApplicationDate`
-   `PossibleCommutation` (Boolean)

### 4. Application Decision
-   `DecisionID` (Unique Identifier)
-   `ApplicationID` (links to Application table)
-   `DecisionDate`
-   `DecisionStage` (e.g., 1st, 2nd, 3rd)
-   `DecisionType` (See list below)

**Decision Types (Pending Confirmation):**
-   `G`: Granted
-   `D`: Denied
-   `R`: Recommended
-   `N.R.` / `NR`: No Recommendation
-   `Exp'd`: Expired
-   `E`: *Meaning Unconfirmed*

### 5. Discharge
-   `DischargeID` (Unique Identifier)
-   `CaseID` (links to Case table)
-   `ActualDischargeDate`
-   `DischargeYears`
-   `DischargeMonths`
-   `DischargeDays`
-   `WritTo`

### 6. Archival Source
-   `SourceID` (Unique Identifier)
-   `ApplicationID` (links to Application table)
-   `DataSource`
-   `JournalNumber`
-   `PageNumber`
-   `BoxNumber`
-   `DocumentTitle`
-   `DateRange`
-   `VolumeNumber`

### 7. Notes
-   `NoteID` (Unique Identifier)
-   `ApplicationID` (links to Application table)
-   `Comments`
-   `LogInformation`

Here is a proposed structure for the data based on the spreadsheet headers. This will help organize the information for the database.

### 1. Person
-   `PersonID` (Unique Identifier)
-   `Name`

### 2. Case
-   `CaseID` (Unique Identifier)
-   `PersonID` (links to Person table)
-   `Crime`
-   `TrialPlace`
-   `TrialDate`
-   `SentenceDate`
-   `SentenceMinYears`
-   `SentenceMinMonths`
-   `SentenceMinDays`
-   `SentenceMaxYears`
-   `SentenceMaxMonths`
-   `SentenceMaxDays`
-   `TermExpiresDate`
-   `FineAmount`
-   `EndsWithFine` (Boolean)
-   `EndsWithoutFine` (Boolean)
-   `PrisonReceptionDate`
-   `CaseType` (e.g., Capital, Life, Less Than Life)

### 3. Clemency Application
-   `ApplicationID` (Unique Identifier, from `Application #`)
-   `CaseID` (links to Case table)
-   `EventType`
-   `RecordDate`
-   `ApplicationDate`
-   `PossibleCommutation` (Boolean)

### 4. Application Decision
-   `DecisionID` (Unique Identifier)
-   `ApplicationID` (links to Application table)
-   `DecisionDate`
-   `DecisionType` (e.g., Granted, Denied, Recommended, No Recommendation, Expired) - **NEEDS CLARIFICATION**
-   `DecisionStage` (e.g., 1st, 2nd, 3rd)

### 5. Discharge
-   `DischargeID` (Unique Identifier)
-   `CaseID` (links to Case table)
-   `ActualDischargeDate`
-   `DischargeYears`
-   `DischargeMonths`
-   `DischargeDays`
-   `WritTo`

### 6. Archival Source
-   `SourceID` (Unique Identifier)
-   `ApplicationID` (links to Application table)
-   `DataSource`
-   `JournalNumber`
-   `PageNumber`
-   `BoxNumber`
-   `DocumentTitle`
-   `DateRange`
-   `VolumeNumber`

### 7. Notes
-   `NoteID` (Unique Identifier)
-   `ApplicationID` (links to Application table)
-   `Comments`
-   `LogInformation`
