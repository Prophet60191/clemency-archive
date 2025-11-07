# Data Management & Backup Plan

**Purpose:** A formal, 1-page document for internal records outlining the storage and security protocols for all project data.

---

## 1. Data Storage

*   **Raw Scans:**
    *   **Location:** [Cloud Storage Provider, e.g., Google Drive, Dropbox]
    *   **Folder Path:** `[Link to specific folder]`
    *   **Access Control:** Access is restricted to the Project Leader and Team Leads.

*   **Database:**
    *   **Provider:** [Cloud Database Provider, e.g., AWS RDS, Heroku Postgres]
    *   **Instance Name:** `[e.g., clemency-project-db-prod]`
    *   **Access Control:** Database credentials are known only to the Project Leader and the lead developer. Application credentials are read-only for the public-facing website.

## 2. Backup Schedule

*   **Frequency:** The production database is backed up **daily**.
*   **Time:** Backups are initiated automatically at **2:00 AM Eastern Time**.
*   **Retention Policy:** Daily backups are retained for **30 days**. After 30 days, they are automatically deleted.

## 3. Restore Protocol

*   **Objective:** To ensure data can be restored in case of corruption or catastrophic failure.
*   **Process:**
    1.  A daily backup is restored to a new, temporary database instance.
    2.  A test script is run to verify data integrity (e.g., `SELECT COUNT(*) FROM records;`).
    3.  The temporary instance is destroyed.
*   **Last Tested Restore:** `[Date]`
*   **Next Scheduled Test:** `[Date]`
