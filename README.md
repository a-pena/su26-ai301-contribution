# Contribution 1: USACO FAQ CF Ratings

**Contribution Number:** 1
**Student:** Andrea Pena
**Issue:** https://github.com/cpinitiative/usaco-guide/issues/5024
**Status:** Phase IV Complete

---

## Why I Chose This Issue

I chose issue #5024, “USACO FAQ CF Ratings,” because it is a documentation/content issue in the USACO Guide project and is a good fit for my first open-source contribution. The issue focuses on reviewing and clarifying how Codeforces ratings correspond to USACO divisions, which is specific enough for me to explain clearly and work on within the scope of this program.

This issue matches my current skills and learning goals because it involves MDX/content editing rather than deep backend, systems, or infrastructure work. I want to learn how open-source documentation is maintained, how contributors propose careful educational content changes, and how maintainers review improvements to public learning resources. I also chose this issue because it is labeled as a good first issue, has no assignee, and does not appear to have an open pull request already solving it.

---

## Understanding the Issue

### Problem Description

The USACO Guide FAQ includes a section that compares Codeforces ratings to USACO divisions. The issue suggests that some of the current rating ranges may be inaccurate or may need clarification, especially because Codeforces and USACO contests have different formats and time constraints.

The original issue notes that some rating upper bounds, such as Bronze, Silver, and Gold, may be too low. For example, the issue suggests that the Silver upper bound might need to be higher because a student may not solve a 2300-rated Codeforces problem during a Codeforces contest, but might be able to solve a similar problem during a USACO contest because USACO provides more time per problem.

Later in the discussion, there is also a maintainer note suggesting that Bronze and Silver may currently be reasonably accurate for the season, so the exact scope of the update may need clarification before changing the numbers.

### Expected Behavior

The FAQ should provide clearer and more accurate guidance about how Codeforces ratings roughly correspond to USACO divisions. It should make clear that these ranges are approximate because Codeforces and USACO contests differ in contest structure, time limits, number of problems, and problem style.

### Current Behavior

The current FAQ provides approximate Codeforces rating ranges for USACO divisions, but the issue discussion suggests that some ranges may be too low or not clearly explained. This could confuse students who are trying to compare their Codeforces experience with USACO division difficulty.

During Phase II reproduction, I confirmed that the current FAQ displays these rough estimates:

* Bronze: `<1300` competitors / `900–1500` problems
* Silver: `1200–1500` competitors / `1200–1900` problems
* Gold: `1500–1800` competitors / `1500–2200` problems
* Platinum: `1650+` competitors / `1900+` problems

### Affected Components

The affected component is the USACO Guide FAQ content page.

The relevant source file is:

```text
content\1_General\USACO_FAQs.mdx
```

The affected area is specifically the FAQ question:

```text
Q: What Codeforces rating corresponds to each of the USACO divisions?
```

---

## Reproduction Process

### Environment Setup

During Phase I, local setup was not required. For Phase I, I reviewed the GitHub issue, selected issue #5024, announced my claim in the CodePath issue-selection Slack channel, forked the USACO Guide repository, and created this public Contribution README.

For Phase II, I set up the USACO Guide project locally on Windows using PowerShell.

I cloned my fork to my D: drive because my C: drive has limited storage:

```powershell
D:
cd CodePath
git clone https://github.com/a-pena/usaco-guide.git
cd usaco-guide
```

I created and pushed a working branch for issue #5024:

```powershell
git checkout -b fix-issue-5024-usaco-faq-cf-ratings
git push -u origin fix-issue-5024-usaco-faq-cf-ratings
```

During setup, I found that my original Node version was too old:

```text
node v12.18.4
```

This caused Corepack/Yarn errors because the project requires Yarn 4.9.2. To fix this, I installed `fnm`, installed Node 24, and activated it:

```powershell
winget install Schniz.fnm
fnm install 24
fnm use 24
node -v
```

After updating Node, I confirmed the active version was:

```text
v24.16.0
```

Then I enabled Corepack and activated the Yarn version required by the project:

```powershell
corepack.cmd enable
corepack.cmd prepare yarn@4.9.2 --activate
yarn.cmd -v
```

I confirmed Yarn was using the correct version:

```text
4.9.2
```

Then I installed the project dependencies:

```powershell
yarn.cmd install
```

The installation completed successfully with warnings:

```text
Done with warnings
```

Finally, I started the local development server:

```powershell
yarn.cmd dev
```

The project ran successfully at:

```text
http://localhost:3000
```

### Steps to Reproduce

Since this is a documentation/content issue, reproduction means verifying the current wording in the FAQ and comparing it to the concern raised in issue #5024.

1. Clone my fork of the USACO Guide repository:

   ```powershell
   git clone https://github.com/a-pena/usaco-guide.git
   ```

2. Enter the project folder:

   ```powershell
   cd usaco-guide
   ```

3. Check out my working branch:

   ```powershell
   git checkout fix-issue-5024-usaco-faq-cf-ratings
   ```

4. Install the project dependencies:

   ```powershell
   yarn.cmd install
   ```

5. Run the local development server:

   ```powershell
   yarn.cmd dev
   ```

6. Open the local site in a browser:

   ```text
   http://localhost:3000
   ```

7. Navigate to the USACO FAQs page:

   ```text
   http://localhost:3000/general/usaco-faq
   ```

8. Find the FAQ question:

   ```text
   Q: What Codeforces rating corresponds to each of the USACO divisions?
   ```

9. Confirm that the current FAQ displays these rough Codeforces-to-USACO estimates:

   ```text
   Bronze: <1300 competitors / 900–1500 problems
   Silver: 1200–1500 competitors / 1200–1900 problems
   Gold: 1500–1800 competitors / 1500–2200 problems
   Platinum: 1650+ competitors / 1900+ problems
   ```

10. Compare this current FAQ content with GitHub issue #5024, which suggests that the Codeforces rating comparison may need updated ranges or clearer wording.

### Reproduction Evidence

Branch in my fork:

```text
https://github.com/a-pena/usaco-guide/tree/fix-issue-5024-usaco-faq-cf-ratings
```

GitHub issue:

```text
https://github.com/cpinitiative/usaco-guide/issues/5024
```

I located the FAQ source file locally with PowerShell:

```powershell
Get-ChildItem -Recurse -Include *.md,*.mdx | Select-String -Pattern "What Codeforces rating corresponds"
```

The relevant FAQ section is located in:

```text
content\1_General\USACO_FAQs.mdx
```

The section starts around line 214 and contains the current Codeforces rating estimates for Bronze, Silver, Gold, and Platinum.

I also reproduced the issue visually by running the site locally with `yarn.cmd dev` and opening the FAQ page in the browser at:

```text
http://localhost:3000/general/usaco-faq
```

The page displayed the current FAQ section titled:

```text
Q: What Codeforces rating corresponds to each of the USACO divisions?
```

My findings: the FAQ already warns that Codeforces ratings and USACO divisions cannot be directly compared, but issue #5024 raises the concern that the listed ranges may be outdated or may need clearer wording. Because the issue discussion includes some uncertainty about Bronze and Silver, the safest next step is a conservative documentation update unless a maintainer requests specific range changes.

---

## Solution Approach

### Analysis

The likely root cause is that the FAQ gives approximate Codeforces rating ranges without enough clarification about how rough those comparisons are. Codeforces and USACO are not directly equivalent because the contests have different formats. Codeforces contests usually include more problems with less time per problem, while USACO contests usually include fewer problems with more time available.

Because of that difference, a problem’s Codeforces rating may not translate directly to a USACO division. The FAQ may need to better explain that these ranges are estimates rather than strict boundaries.

There is also some uncertainty in the issue thread because a later maintainer comment suggests that Bronze and Silver may already be reasonably accurate. Because of this, I made a conservative documentation change rather than immediately changing all ranges without guidance.

### Proposed Solution

My proposed solution was to make a small, careful update to the FAQ section about Codeforces ratings and USACO divisions.

The implemented solution:

* Clarifies that the rating ranges are approximate estimates.
* Explains that Codeforces competitor ratings and Codeforces problem ratings measure different things.
* Explains that USACO gives more time per problem, so direct comparison to Codeforces ratings is imperfect.
* Avoids making unsupported changes to Bronze, Silver, Gold, or Platinum ranges without maintainer confirmation.
* Preserves the existing FAQ structure and keeps the change focused on the issue.

If the maintainers request more specific rating changes during review, I can update the pull request during the iteration process.

### Implementation Plan

For this documentation issue, my implementation plan is organized into the main steps I followed before making and submitting the change:

#### Understand

During Phase I, I selected issue #5024 because it is a documentation/content issue in the USACO Guide FAQ. The issue focuses on the FAQ section that compares Codeforces ratings to USACO divisions.

The problem is that the current FAQ comparison may be inaccurate, outdated, or unclear for students trying to understand how Codeforces difficulty roughly maps to USACO levels. The FAQ already explains that Codeforces and USACO cannot be directly compared, but issue #5024 raises the concern that the listed ranges may need updated wording or clarification.

For Phase II, I reproduced the issue locally by running the USACO Guide site, opening the USACO FAQs page, and confirming the current Codeforces rating estimates shown in the FAQ.

#### Match

This is a documentation update, so I matched the existing style, tone, formatting, and MDX structure used in the USACO Guide FAQ file.

The relevant file is:

```text
content\1_General\USACO_FAQs.mdx
```

The relevant section is:

```text
Q: What Codeforces rating corresponds to each of the USACO divisions?
```

I kept the change focused on this FAQ section instead of making unrelated edits.

#### Plan

My planned approach was:

1. Review the current FAQ wording and the surrounding FAQ entries to preserve the same style and formatting.

2. Re-read issue #5024 and the maintainer discussion before making changes.

3. Avoid making unsupported changes to all rating ranges without maintainer confirmation.

4. Since the issue discussion includes uncertainty about whether Bronze and Silver are already reasonably accurate, make a conservative documentation update unless a maintainer requests specific range changes.

5. Clarify that Codeforces ratings and USACO divisions are only rough comparisons and should not be treated as exact equivalents.

6. Avoid changing the existing rating values until maintainers provide more specific guidance.

7. Run the project locally again with:

   ```powershell
   yarn.cmd dev
   ```

8. Check the rendered FAQ page in the browser to make sure the updated text displays correctly.

9. Review the Git diff to confirm that the change is small, focused, and limited to the FAQ documentation.

#### Implement

During Phase III, I implemented the documentation update in:

```text
content\1_General\USACO_FAQs.mdx
```

The change updates the FAQ question:

```text
Q: What Codeforces rating corresponds to each of the USACO divisions?
```

I clarified that the listed ranges are only rough comparisons, not exact cutoffs. I also added wording to explain that Codeforces problem ratings and Codeforces competitor ratings measure different things. In addition, I clarified that because USACO contests give more time per problem, students may be able to solve a higher-rated Codeforces-style problem in a USACO contest setting.

I also changed the Bronze wording from `<1300 rated on CF` to `below 1300 rated on CF` to avoid an MDX rendering issue caused by the `<` character.

My working branch for this issue is:

```text
https://github.com/a-pena/usaco-guide/tree/fix-issue-5024-usaco-faq-cf-ratings
```

The implementation commit is:

```text
ca57383f - Clarify Codeforces rating comparison in USACO FAQ
```

#### Review

Before committing the change, I reviewed the update to make sure:

* The wording is clear and helpful for students.
* The FAQ still clearly states that Codeforces and USACO are significantly different.
* The change does not present the rating ranges as exact boundaries.
* The MDX formatting is correct.
* The diff is focused only on the Codeforces rating FAQ section.
* The update follows the style of the existing USACO Guide documentation.
* No generated files were included in the commit.

#### Evaluate

I evaluated the change by running the site locally and checking the rendered FAQ page in the browser.

The local page I used for validation is:

```text
http://localhost:3000/general/usaco-faq
```

I confirmed that the updated FAQ section rendered correctly and addressed the concern raised in issue #5024.

Phase III status: implementation is complete, the relevant FAQ section was updated, the site was tested locally, the change was committed, and the commit was pushed to my working branch.

---

## Testing Strategy

### Phase II Reproduction Checks

| Status   | Reproduction Check                                                                         |
| -------- | ------------------------------------------------------------------------------------------ |
| Complete | Confirmed that the project can be cloned locally.                                          |
| Complete | Created and pushed a working branch in my fork.                                            |
| Complete | Installed the required project dependencies with Yarn.                                     |
| Complete | Started the local development server successfully.                                         |
| Complete | Opened the USACO Guide site locally at `http://localhost:3000`.                            |
| Complete | Navigated to the USACO FAQs page.                                                          |
| Complete | Confirmed that the Codeforces ratings FAQ section renders locally.                         |
| Complete | Verified the current Bronze, Silver, Gold, and Platinum rating estimates shown in the FAQ. |

### Phase III Testing Approach

This contribution was a documentation-only MDX change to the USACO Guide FAQ. It did not modify application logic, backend behavior, algorithms, UI components, data models, or user-facing interactive features.

Because the change only updated explanatory FAQ text, I did not add automated unit tests. For this type of non-code documentation contribution, manual documentation validation was the appropriate testing approach. The goal was to confirm that the edited FAQ page still rendered correctly, that the updated wording appeared as expected, and that the change stayed limited to the relevant documentation section.

### Manual Test Cases

| Test Case                         | Steps Performed                                                                                           | Expected Result                                                   | Result |
| --------------------------------- | --------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------- | ------ |
| Local site starts successfully    | Ran `yarn.cmd dev` from the USACO Guide project directory.                                                | The local development server starts without blocking errors.      | Passed |
| FAQ page loads locally            | Opened `http://localhost:3000/general/usaco-faq` in the browser.                                          | The USACO FAQ page loads successfully.                            | Passed |
| Edited FAQ section appears        | Located the FAQ question: `Q: What Codeforces rating corresponds to each of the USACO divisions?`         | The edited FAQ section is visible on the page.                    | Passed |
| Updated clarification appears     | Checked that the FAQ says the ranges are “rough comparisons, not exact cutoffs.”                          | The new clarification appears in the rendered page.               | Passed |
| Rating-type clarification appears | Checked that the FAQ explains that CF problem ratings and CF competitor ratings measure different things. | The new explanation appears in the rendered page.                 | Passed |
| MDX formatting renders correctly  | Confirmed the heading displayed normally and did not show extra `##` characters.                          | The heading renders as a normal FAQ heading.                      | Passed |
| Bullet list renders correctly     | Checked the Bronze, Silver, Gold, and Platinum bullet list.                                               | The bullet list displays correctly.                               | Passed |
| MDX parsing issue resolved        | Replaced `<1300 rated on CF` with `below 1300 rated on CF`.                                               | The page renders without the MDX parsing issue caused by `<1300`. | Passed |
| Nearby FAQ sections still display | Checked the next FAQ section after the edited section.                                                    | Nearby FAQ content still renders normally.                        | Passed |
| Diff is scoped to the issue       | Reviewed the Git diff before committing.                                                                  | Only the relevant FAQ documentation file was included.            | Passed |
| Generated files excluded          | Restored `public/usaco-divisions.json` after local generation.                                            | Generated local files were not included in the commit.            | Passed |

### Automated Testing Decision

No new automated unit test was added because this PR only changed documentation text in an MDX FAQ page. There was no application logic, function behavior, API behavior, or UI component behavior to unit test.

Instead, I documented the manual validation process that a future maintainer or contributor could use to confirm that the FAQ remains accurate and renders correctly. This includes checking the local FAQ page, the edited section wording, the MDX formatting, the bullet list formatting, and the Git diff scope.

### Existing Project Validation

I validated the documentation change locally by running:

```powershell
yarn.cmd dev
```

Then I opened:

```text
http://localhost:3000/general/usaco-faq
```

I confirmed that:

* The USACO FAQ page loaded successfully.
* The edited Codeforces rating FAQ section displayed the updated wording.
* The heading rendered correctly without extra Markdown characters.
* The bullet list rendered correctly.
* The wording did not present the rating ranges as exact cutoffs.
* The MDX parsing issue caused by `<1300` was resolved by changing the wording to `below 1300`.
* The change was limited to `content/1_General/USACO_FAQs.mdx`.
* No generated local files were included in the implementation commit.

I also ran a Git whitespace validation check on the implementation commit:

```powershell
git diff --check HEAD~1 HEAD
```

Result:

```text
Passed. The command returned no whitespace errors for the implementation commit.
```

I also reviewed the commit summary with:

```powershell
git show --stat ca57383f
```

This confirmed that the implementation commit only changed the intended FAQ file:

```text
content/1_General/USACO_FAQs.mdx
```

The commit summary showed:

```text
1 file changed, 10 insertions(+), 16 deletions(-)
```


### Future Validation Instructions

To validate this documentation section in the future, a reviewer can:

1. Run the project locally with:

   ```powershell
   yarn.cmd dev
   ```

2. Open:

   ```text
   http://localhost:3000/general/usaco-faq
   ```

3. Find the FAQ section:

   ```text
   Q: What Codeforces rating corresponds to each of the USACO divisions?
   ```

4. Confirm that the section explains that Codeforces-to-USACO ranges are rough comparisons, not exact cutoffs.

5. Confirm that the section explains that Codeforces problem ratings and Codeforces competitor ratings measure different things.

6. Confirm that the Bronze wording uses `below 1300 rated on CF` rather than the MDX-unsafe `<1300 rated on CF`.

7. Confirm that the FAQ heading, paragraphs, and bullet list render correctly.

8. Review the Git diff to confirm that the change is scoped only to the relevant documentation section.

### Testing Rubric Mapping

| Phase III Testing Rubric Item | How This README Addresses It |
|---|---|
| At least one new test exists that exercises the fix | Because this was a documentation-only MDX change, I documented the manual documentation validation test cases used for this fix instead of adding automated unit tests. These manual test cases exercise the fix by checking the rendered FAQ page, the updated wording, the heading formatting, the bullet list, the MDX parsing fix, nearby FAQ rendering, and diff scope. |
| Existing test suite still passes or student explains why failure is unrelated | This PR did not change application logic, backend behavior, API behavior, algorithms, or UI components, so there was no directly applicable unit test suite for this FAQ text change. I validated the existing documentation page by running `yarn.cmd dev`, opening the FAQ page locally, confirming the page rendered correctly, and running `git diff --check HEAD~1 HEAD`, which returned no whitespace errors. |
| Tests follow patterns from the project's existing test files | For this documentation-only MDX change, I followed the repository’s documentation validation pattern: edit the MDX content file, run the local documentation site, inspect the rendered page, verify Markdown/MDX formatting, confirm nearby content still displays correctly, and review the Git diff to ensure the change is scoped to the intended documentation file. |

## Implementation Notes

### Week 1 Progress

During Phase I, I reviewed the CodePath curated issue list and inspected several possible issues. I rejected issues that appeared already claimed, had linked pull requests, had broad scope, or required deeper technical knowledge than was realistic for a first contribution.

I selected USACO FAQ CF Ratings #5024 because it is a good first issue, focused on documentation/content, and appears manageable for the program timeline. I announced my claim in the CodePath issue-selection Slack channel, forked the USACO Guide repository under my GitHub account, and created this public Contribution README repository.

### Week 2 Progress

During Phase II, I set up the USACO Guide project locally on Windows using PowerShell.

I cloned my fork to my D: drive, created a working branch, installed the required dependencies, and successfully ran the project locally.

My working branch is:

```text
https://github.com/a-pena/usaco-guide/tree/fix-issue-5024-usaco-faq-cf-ratings
```

I found the relevant FAQ source file:

```text
content\1_General\USACO_FAQs.mdx
```

I confirmed that the Codeforces ratings FAQ section starts around line 214 and contains the current rough estimates for Bronze, Silver, Gold, and Platinum.

I also ran the site locally with:

```powershell
yarn.cmd dev
```

The site loaded successfully at:

```text
http://localhost:3000
```

I opened the USACO FAQs page locally and confirmed that the current Codeforces ratings FAQ section renders in the browser.

### Week 3 Progress

During Phase III, I implemented the documentation clarification for issue #5024.

I edited the FAQ source file:

```text
content\1_General\USACO_FAQs.mdx
```

The update clarifies that the Codeforces-to-USACO comparison is only approximate and should not be treated as exact cutoffs. I also clarified that Codeforces problem ratings and Codeforces competitor ratings measure different things, and that USACO contests allow more time per problem than Codeforces contests.

I kept the existing rating ranges instead of making broad unsupported rating changes because the issue discussion includes uncertainty about which ranges should change.

I tested the change locally by running:

```powershell
yarn.cmd dev
```

Then I opened:

```text
http://localhost:3000/general/usaco-faq
```

I confirmed that the updated FAQ rendered correctly in the browser. I also reviewed the Git diff and Git status before committing to make sure only the FAQ MDX file was included.

### Code Changes

* **Files modified:** `content/1_General/USACO_FAQs.mdx`
* **Key commit:** `ca57383f - Clarify Codeforces rating comparison in USACO FAQ`
* **Branch:** `fix-issue-5024-usaco-faq-cf-ratings`
* **Branch link:** https://github.com/a-pena/usaco-guide/tree/fix-issue-5024-usaco-faq-cf-ratings
* **Commit link:** https://github.com/a-pena/usaco-guide/commit/ca57383f
* **Approach decisions:** I kept this contribution focused on documentation/content. Because the issue discussion includes uncertainty about whether Bronze and Silver are already reasonably accurate, I made a conservative clarification instead of changing the rating ranges without maintainer guidance.

### Week 4 Progress

During Phase IV, I opened a review-ready pull request to the official USACO Guide repository:

```text
https://github.com/cpinitiative/usaco-guide/pull/6316
```

The PR was opened from my fork branch, `a-pena:fix-issue-5024-usaco-faq-cf-ratings`, into the official repository branch, `cpinitiative:master`.

The pull request was reviewed, approved, merged, and closed by the maintainers. The PR was successfully merged into the official `cpinitiative:master` branch.

---

## Process & Communication Evidence

### Slack Participation

I participated in Slack during the contribution process and posted milestone updates for this USACO FAQ CF Ratings contribution.

For Phase III, I posted a Week 3 Slack update announcing:

```text
Phase III Complete — USACO FAQ CF Ratings #5024
```

That post included my Contribution README link, working branch link, commit link, and a short summary of the implementation work completed.

I have screenshot evidence of this Slack participation available for re-evaluation. The relevant evidence is labeled:

```text
Week 3 slack post — Wednesday, June 17th
```

This post shows that I announced my Phase III milestone during the Phase III period.

---

## Pull Request

**PR Link:** https://github.com/cpinitiative/usaco-guide/pull/6316

**PR Description:**

This PR updates the USACO FAQ section that compares Codeforces ratings to USACO divisions. The change keeps the existing rating ranges but clarifies that they are rough comparisons rather than exact cutoffs.

The PR also explains that Codeforces competitor ratings and Codeforces problem ratings measure different things, and that USACO contests provide more time per problem, so direct comparisons are imperfect.

**Maintainer Feedback:**

* The pull request was reviewed and approved by a maintainer.
* The pull request was merged and closed.
* The change was accepted into the official `cpinitiative/usaco-guide` repository.
* GitHub shows the pull request as successfully merged into `cpinitiative:master`.

**Status:** Pull request merged and closed.

---

## Learnings & Reflections

### Technical Skills Gained

During Phase I, I learned how to evaluate open-source issues more carefully before choosing one. I practiced checking for assignees, linked pull requests, recent comments, maintainer activity, labels, scope, and whether an issue is realistic for a first contribution.

During Phase II, I learned how to set up a larger open-source project locally on Windows using PowerShell. I practiced cloning a fork, creating a Git branch, installing dependencies, running a local development server, and finding the relevant source file for a documentation issue.

I also learned more about the difference between a forked project repository and a separate Contribution README repository for tracking my CodePath progress.

During Phase III, I practiced making a focused documentation change in an MDX file, testing the rendered documentation locally, reviewing a Git diff, committing only the intended file, and pushing my branch to GitHub.

During Phase IV, I learned how to prepare and submit a review-ready pull request to an upstream open-source repository. I practiced checking the base repository, base branch, compare branch, merge status, and PR description before submitting.

I also learned how GitHub pull request templates work and how to write a clearer PR description that explains the purpose of the change, the issue being addressed, the testing completed, and the current status of the contribution.

After submitting the PR, I learned more about the open-source review process. I saw that the repository requires maintainer review before merging and that some workflows may require approval for pull requests from forks. This helped me understand that opening a pull request is not the same as merging code, and that review requirements are a normal part of contributing to protected open-source repositories.

### Challenges Overcome

One challenge in Phase I was that several issues that looked good in the curated list were already being worked on or had recent comments from other contributors. I reviewed multiple options before choosing this issue.

Another challenge was that I could not directly mark the issue as claimed in the course sheet, so I announced my claim in the CodePath issue-selection Slack channel instead.

During Phase II, my original Node version was too old for the project’s required Yarn/Corepack setup. I solved this by installing `fnm`, installing Node 24, activating the newer Node version, enabling Corepack, and using Yarn 4.9.2.

I also had to work around PowerShell script execution restrictions by using `.cmd` commands such as:

```powershell
npm.cmd -v
corepack.cmd --version
yarn.cmd -v
```
During Phase III, I ran into an MDX parsing issue caused by the `<1300` text. Since MDX can treat `<` as the start of a tag, I changed the wording to `below 1300` so the page would render correctly.

I also had to deal with local content caching. After editing the MDX file, the browser initially showed cached content, so I cleaned and rebuilt the local content before confirming the updated FAQ rendered correctly.

Another small Git challenge was that my local Git identity was not configured, so the first commit attempt failed. I fixed this by setting my Git username and noreply GitHub email for the repository, then successfully committed and pushed the change.

During Phase IV, one challenge was making sure the pull request was opened against the correct repository and branch. Since I was working from a fork, I had to confirm that the PR was going from my branch in my fork into the official `cpinitiative/usaco-guide` repository on the `master` branch, instead of accidentally opening a pull request only inside my own fork.

Another challenge was preparing a professional PR description. I needed to replace the default template text with a clear explanation of what the PR does, why the change was made, how it addresses issue #5024, and how I tested it locally. I also had to decide how to reference the issue carefully. Since my change is conservative and focused on clarification, I used wording that addresses the issue without overstating that it fully resolves every possible rating-range concern.

After opening the PR, I also had to understand the GitHub status messages. The PR showed that review is required, merging is blocked, and some workflows are awaiting maintainer approval. I learned that these messages are expected for protected repositories and pull requests from forks, and they do not mean the submission was incorrect.

### What I'd Do Differently Next Time

Next time, I would check the project’s required Node and package manager versions earlier before trying to install dependencies. I would also review the repository’s setup requirements before beginning local reproduction so I can avoid setup issues more quickly.

For issue selection, I would continue checking GitHub issue comments, assignees, and linked pull requests before getting attached to an issue. Comparing several issues side by side with the CodePath checklist helped me choose a realistic first contribution.

I would also be more careful with MDX-specific syntax, especially characters like `<`, because they can be interpreted differently than normal Markdown text.

For the pull request phase, I would review the repository’s pull request template and contribution guidelines earlier so I can plan my final PR description before submission. I would also keep a running list of testing evidence, branch links, commit links, and issue links throughout the project so the final README update is faster.

This phase helped me become more confident about submitting a pull request after carefully checking the branch, base repository, and PR description.

---

## Resources Used

* GitHub issue: https://github.com/cpinitiative/usaco-guide/issues/5024
* Original repository: https://github.com/cpinitiative/usaco-guide
* My fork: https://github.com/a-pena/usaco-guide
* My working branch: https://github.com/a-pena/usaco-guide/tree/fix-issue-5024-usaco-faq-cf-ratings
* Implementation commit: https://github.com/a-pena/usaco-guide/commit/ca57383f
* Pull request: https://github.com/cpinitiative/usaco-guide/pull/6316
* Local FAQ source file: `content\1_General\USACO_FAQs.mdx`
* Local reproduction page: `http://localhost:3000/general/usaco-faq`
* CodePath AI301 Phase I instructions
* CodePath AI301 Phase II instructions
* CodePath AI301 Phase III instructions
* CodePath AI301 Phase IV instructions
* CodePath issue-selection Slack channel
* PowerShell
* Git
* Node / fnm
* Corepack
* Yarn
