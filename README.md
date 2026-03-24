# GitHub for Teams: Branch Protection and Collaborative Web Dev

> In this section, you will form a group of two to set up branch protection rules and safely collaborate on our live webpage using Git.

## Scenario:

Your team's `main` branch holds the live production code of your interactive single-page website. It cannot be broken at any time, so we need to naturally block direct code pushes from local branches directly to the `main` branch. Also, we, as a team, would like to review each other's code (like new HTML structure or Tailwind classes) to catch mistakes, improve design, and learn from one another.

## Solution: Branch Protection Rules

Protect the main development branch (`main`) to prevent direct pushes and enforce pull-request code reviews before merging any code changes.

## Steps:

1. Navigate to your GitHub repository.

2. Click on the "Settings" tab located at the right end of the menu bar of your repository.

3. In the left sidebar of the Settings page, click on "Branches."

4. Click the `Add branch protection rule` button.

5. Add `main` to the `Branch name pattern` input.

6. Add a checkmark to the following options:

- Require a pull request before merging
  - Require approvals
- Require status checks to pass before merging
  - Require branches to be up to date before merging
- Do not allow bypassing the above settings

> Browse around to see anything interesting and test out with your team.

7. Save by clicking the `Create` button.

8. Find out how the branch protection rule works for your collaboration with the exercise below.
   **Things to try:**
- Try to push your code change to the `main` branch directly.
- In a Pull Request, try to merge your branch into `main` before getting an approval from your team.
- In a Pull Request, try to merge when your branch is not up to date.

---

# Git Practice Exercise: Collaborative Web Development with Conflict Resolution

> In this practice exercise, you will simulate a collaborative web development project involving two students: Student 1 and Student 2. You'll work through various Git actions directly on the interactive HTML page we built (`index.html`) and focus on resolving conflicts that arise when multiple people edit the Navbar simultaneously. This exercise will guide you through the precise steps of safe conflict resolution in Git.

## Scenario:

You are working on our collaborative single-page website. Each student is in charge of personalizing a section AND updating the `<nav>` at the top of the page. Because both of you will be editing the Navbar at the exact same time, a merge conflict is guaranteed to happen!

## Steps:

### Step 1: Set Up the Repository

- **Student 1 (S1):** Create the GitHub repository and commit the base `index.html` (the interactive webpage with the scroll progress bar and color-changing navbar).
- **S1:** Push this initial code to the `main` branch so your partner can clone it.

### Step 2-1: Student 1 Customizes Section 1 & Navbar

- **Student 1 (S1):** Create a new branch named `feature-s1` for your work.
- **S1:** Open `index.html`. 
- **S1:** Change the `AB` text in the Navbar to your initials.
- **S1:** Add a brand new Tailwind-styled anchor link next to the others: `<a href="#hello-message" class="hover:text-black transition-colors">Demo</a>`.
- **S1:** Customize the `<h1>` tag in **Section 1** to introduce yourself.
- **S1:** Commit your changes to the `feature-s1` branch.
- **S1:** Push the branch to the remote repository.
- **S1:** NOTE: **_DO NOT MERGE YET_**. Create a pull request to merge the `feature-s1` branch into the `main` branch.

### Step 2-2: Student 2 Customizes Section 2 & Navbar

- **Student 2 (S2):** Wait until S1 finishes Step 1 and then clone the repository to your local machine.
- **S2:** Create a new branch named `feature-s2` for your work.
- **S2:** Open `index.html`. 
- **S2:** Change the `YZ` text in the Navbar to your initials.
- **S2:** Customize the `<h1>` tag in **Section 2** to introduce yourself.
- **S2:** Commit your changes to the `feature-s2` branch.
- **S2:** Push the branch to the remote repository.
- **S2:** NOTE: **_DO NOT MERGE YET_**. Create a pull request to merge the `feature-s2` branch into the `main` branch.

### Step 3: Conflict Arises

- **S2:** Merge the `feature-s2` pull request into the `main` branch. (Since this is the first merge, it will go through smoothly).
- **S1:** Now, try to merge your `feature-s1` pull request. GitHub will warn you that it cannot be merged automatically because there is a conflict in the Navbar!
- **S1:** In your local terminal, switch to the `main` branch and `git pull` the recent changes from S2.
- **S1:** Switch back to your `feature-s1` branch and merge the `main` branch into it (`git merge main`).
- **S1:** Resolve the conflict in `index.html` by manually editing the code so that **both** your initials AND S2's initials are kept in the Navbar correctly.
- **S1:** Commit the resolved conflict and push the branch to the remote repository.
- **S1:** Go back to your PR; it should now be "green" and mergeable. Merge it to `main`.

### Step 4: Wrapping Up

- **S1 and S2:** Switch to your `main` branch locally and `git pull`. Confirm that the webpage's Navbar successfully displays both your initials and the new demo link!
- **S1 and S2:** Verify that Section 1 and Section 2 both reflect your personalized changes.
- **S1 and S2:** Delete the feature branches related to your completed contributions.
- **S1 and S2:** Your collaborative Git exercise with conflict resolution is complete!

> **Note:** HTML code conflicts can be tricky because breaking a single tag can break the entire webpage's design! Conflict resolution involves careful consideration, especially around syntax. In real-world scenarios, team members should communicate directly while resolving to ensure no functional Javascript triggers or Tailwind classes are lost in the process!
