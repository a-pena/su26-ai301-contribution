# Contribution 1: USACO FAQ CF Ratings

**Contribution Number:** 1
**Student:** Andrea Pena
**Issue:** https://github.com/cpinitiative/usaco-guide/issues/5024
**Status:** Phase III Complete

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

If the maintainers request more specific rating changes during review, I can update the PR in Phase IV.

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

### Unit Tests

This issue is a documentation/content issue, so traditional unit tests are not required.

For this documentation change, I treated documentation checks as the closest equivalent to unit tests:

| Status   | Check                                                                                              |
| -------- | -------------------------------------------------------------------------------------------------- |
| Complete | Confirmed that the edited FAQ file has valid Markdown/MDX formatting.                              |
| Complete | Confirmed that the change is limited to the relevant Codeforces ratings FAQ section.               |
| Complete | Confirmed that the updated wording does not make unsupported claims about exact rating boundaries. |
| Complete | Confirmed that the `<1300` wording was changed to `below 1300` to avoid an MDX parsing issue.      |

### Integration Tests

For this documentation issue, integration testing means checking that the documentation site still runs and renders the edited FAQ page correctly.

| Status   | Check                                                              |
| -------- | ------------------------------------------------------------------ |
| Complete | Ran the local development server after editing the FAQ.            |
| Complete | Opened the rendered FAQ page in the browser.                       |
| Complete | Confirmed that the updated FAQ section displays correctly.         |
| Complete | Confirmed that nearby FAQ sections and page navigation still work. |

### Manual Testing

Manual testing included opening the FAQ page locally, finding the Codeforces ratings FAQ section, reading the wording as a student/user, and checking that the explanation is clear, accurate, and not misleading.

I confirmed that the change does not affect unrelated FAQ sections and that the page still renders correctly at:

```text
http://localhost:3000/general/usaco-faq
```

I also reviewed the final Git status and diff before committing to make sure the implementation commit included only the intended FAQ file and did not include generated local files.

---

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

---

## Pull Request

**PR Link:** Not submitted yet.

**PR Description:** Draft idea:

This PR updates the USACO FAQ section that compares Codeforces ratings to USACO divisions. The goal is to clarify that the rating ranges are approximate and that Codeforces and USACO contests are not directly comparable because of differences in contest structure, time per problem, and problem style.

The PR keeps the existing rating ranges and focuses on making the explanation clearer. It also clarifies that Codeforces competitor ratings and Codeforces problem ratings are different types of ratings.

**Maintainer Feedback:**

* No maintainer feedback received yet.

**Status:** Not submitted yet. Phase III focused on implementing, testing, committing, and pushing the documentation update. The pull request will be submitted in Phase IV.

---

## Learnings & Reflections

### Technical Skills Gained

During Phase I, I learned how to evaluate open-source issues more carefully before choosing one. I practiced checking for assignees, linked pull requests, recent comments, maintainer activity, labels, scope, and whether an issue is realistic for a first contribution.

During Phase II, I learned how to set up a larger open-source project locally on Windows using PowerShell. I practiced cloning a fork, creating a Git branch, installing dependencies, running a local development server, and finding the relevant source file for a documentation issue.

I also learned more about the difference between a forked project repository and a separate Contribution README repository for tracking my CodePath progress.

During Phase III, I practiced making a focused documentation change in an MDX file, testing the rendered documentation locally, reviewing a Git diff, committing only the intended file, and pushing my branch to GitHub.

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

### What I'd Do Differently Next Time

Next time, I would check the project’s required Node and package manager versions earlier before trying to install dependencies. I would also look at the repository’s setup requirements before beginning local reproduction so I can avoid setup issues more quickly.

For issue selection, I would continue checking GitHub issue comments, assignees, and linked pull requests before getting attached to an issue. I would also compare several issues side by side using the CodePath checklist before making a final choice.

After Phase III, I would also be more careful with MDX-specific syntax, especially characters like `<`, because they can be interpreted differently than normal Markdown text.

---

## Resources Used

* GitHub issue: https://github.com/cpinitiative/usaco-guide/issues/5024
* Original repository: https://github.com/cpinitiative/usaco-guide
* My fork: https://github.com/a-pena/usaco-guide
* My working branch: https://github.com/a-pena/usaco-guide/tree/fix-issue-5024-usaco-faq-cf-ratings
* Implementation commit: https://github.com/a-pena/usaco-guide/commit/ca57383f
* Local FAQ source file: `content\1_General\USACO_FAQs.mdx`
* Local reproduction page: `http://localhost:3000/general/usaco-faq`
* CodePath AI301 Phase I instructions
* CodePath AI301 Phase II instructions
* CodePath AI301 Phase III instructions
* CodePath issue-selection Slack channel
* PowerShell
* Git
* Node / fnm
* Corepack
* Yarn
