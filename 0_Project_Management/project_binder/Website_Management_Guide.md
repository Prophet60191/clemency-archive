# Your Guide to Managing the Clemency Archive Website

**Purpose:** This is your personal guide to understanding, managing, and updating the project's public-facing website. This document is for your reference and is not part of the public site.

---

## 1. How It Works: The Big Picture (The Book Publisher Analogy)

We have set up an automated system to turn your project's Markdown files into a professional website. Here’s how to think about it:

*   **Your Project Files:** These are your original, master documents. Think of them as the manuscript you are writing.

*   **The `docs/` Directory:** This is a **staging area** for the website. It's a *copy* of your manuscript that you hand over to the publisher. **You should never edit files in this directory directly.**

*   **The `mkdocs.yml` File:** This is the "table of contents" and "cover design" for your book. It tells the system what your site should be called and what the navigation menu should look like.

*   **GitHub Actions:** This is our automated "printing press." When you push changes to GitHub, it automatically takes everything in the `docs/` directory, uses the `mkdocs.yml` file for instructions, and builds a complete website.

*   **GitHub Pages:** This is the "bookstore." It's the public, online location where the finished website is hosted for the world to see.

---

## 2. How to Update the Website Content (Your Workflow)

Follow these steps every time you want to make a change to the website's content (e.g., updating a proposal, fixing a typo, adding a new document).

### Step 1: Edit Your Master Files

Make your changes to the original files in your project, **NOT** the files inside the `docs/` directory. For example, if you want to change the `START_HERE.md` guide, you would edit `/Users/josed/Desktop/Clemency Archive/START_HERE.md`.

### Step 2: Update the `docs/` Directory

After saving your changes, you need to copy them into the `docs/` staging area. Run the following command in your terminal from the `Clemency Archive` directory. This command intelligently copies only the updated Markdown files.

```bash
rsync -a --prune-empty-dirs --include='*/' --include='*.md' --exclude='*' ./ ./docs/
```

### Step 3: Commit and Push Your Changes

Now, save your changes to GitHub. This is the step that triggers the automated "printing press."

```bash
git add .
git commit -m "A brief description of the changes you made"
git push
```

### Step 4: Wait and Verify

That's it! The GitHub Action will now be running. It will take about **1-2 minutes** for the changes to appear on the live website. After a few minutes, visit the site to see your updates.

---

## 3. How to Change the Website's Navigation

If you want to add, remove, or rename an item in the website's top navigation bar or sidebar menu, you only need to edit one file:

*   **File to Edit:** `mkdocs.yml`
*   **What to do:** Modify the `nav:` section in that file. The structure is fairly intuitive. After saving your changes, follow **Steps 2 and 3** from the workflow above to make the changes live.

---

## 4. Quick Reference: Key Links & Files

*   **Live Website URL:** [https://Prophet60191.github.io/clemency-archive/](https://Prophet60191.github.io/clemency-archive/)
*   **GitHub Repository:** [https://github.com/Prophet60191/clemency-archive](https://github.com/Prophet60191/clemency-archive)
*   **Website Configuration File:** `mkdocs.yml`
*   **Automation Workflow File:** `.github/workflows/publish.yml` (You should not need to edit this file).

## 5. Command Cheat Sheet: Common Scenarios

Here are the specific commands you will need for different situations. All commands should be run from the `/Users/josed/Desktop/Clemency Archive` directory in your terminal.

### Scenario 1: You edited an existing file.

This is the most common scenario. You fixed a typo or updated a section in a file like `Clemency_Archive_Proposal.md`.

```bash
# 1. Copy your changes to the docs folder.
rsync -a --prune-empty-dirs --include='*/' --include='*.md' --exclude='*' ./ ./docs/

# 2. Add, commit, and push to GitHub.
git add .
git commit -m "Updated the proposal with new figures"
git push
```

### Scenario 2: You added a new document to the website.

Let's say you created a new file, `New_Partnership_Plan.md`, and you want to add it to the "Project Management" section of the website.

```bash
# 1. Edit the navigation menu.
#    Open the mkdocs.yml file and add a line for your new file in the 'nav:' section.
#    - 'New Partnership Plan': 'New_Partnership_Plan.md'

# 2. Copy the new file to the docs folder.
rsync -a --prune-empty-dirs --include='*/' --include='*.md' --exclude='*' ./ ./docs/

# 3. Add, commit, and push to GitHub.
git add .
git commit -m "Add new partnership plan document to website"
git push
```

### Scenario 3: You removed a document from the website.

Let's say the `New_Partnership_Plan.md` is now obsolete and you want to remove it from the website.

```bash
# 1. Delete the master file.
rm New_Partnership_Plan.md

# 2. Delete the copy in the docs folder.
rm docs/New_Partnership_Plan.md

# 3. Edit the navigation menu.
#    Open the mkdocs.yml file and remove the line for the file you just deleted.

# 4. Add, commit, and push to GitHub.
git add .
git commit -m "Remove obsolete partnership plan from website"
git push
```

---

## 6. Troubleshooting: "My Changes Aren't Live!"

If you've waited a few minutes and your changes aren't showing up, the first place to look is the **Actions tab** in your GitHub repository. 

1.  Go to your repository and click on the **"Actions"** tab.
2.  You will see a list of workflow runs. The top one should correspond to your most recent commit.
3.  If it has a **red X**, it means the build failed. Click on it to see the error message. This will usually tell you exactly what went wrong (e.g., a typo in the `mkdocs.yml` file).
