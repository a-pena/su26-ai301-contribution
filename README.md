# Contribution 1: USACO FAQ CF Ratings

**Contribution Number:** 1
**Student:** Andy Pena
**Issue:** https://github.com/cpinitiative/usaco-guide/issues/5024
**Status:** Phase I Complete

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

### Affected Components

The affected component is the USACO Guide FAQ content page. The likely file is an MDX documentation/content file in the repository that contains the general FAQ section.

The affected area is specifically the FAQ question:

“What Codeforces rating corresponds to each of the USACO divisions?”

---

## Reproduction Process

### Environment Setup

Local environment setup has not started yet. Phase I does not require local setup, cloning, or code changes. This will happen in Phase II.

For Phase I, I reviewed the GitHub issue, selected the issue, announced my claim in the CodePath issue-selection Slack channel, forked the project repository, and created this public Contribution README.

### Steps to Reproduce

Since this is a documentation/content issue, reproduction means verifying the current wording in the FAQ and comparing it to the issue discussion.

Planned Phase II reproduction steps:

1. Open the USACO Guide repository.
2. Locate the FAQ content file that contains the Codeforces rating comparison section.
3. Review the current Codeforces-to-USACO rating ranges.
4. Compare the current wording to the concerns raised in issue #5024.
5. Document whether the issue requires updated ranges, clearer wording, or both.

### Reproduction Evidence

* **Commit showing reproduction:** Not available yet. This will be added in Phase II if needed.
* **Screenshots/logs:** Not applicable yet.
* **My findings:** From reading the issue thread, I found that the main concern is whether the FAQ’s Codeforces-to-USACO rating comparison needs updated ranges, clearer wording, or both.

---

## Solution Approach

### Analysis

The likely root cause is that the FAQ gives approximate Codeforces rating ranges without enough clarification about how rough those comparisons are. Codeforces and USACO are not directly equivalent because the contests have different formats. Codeforces contests usually include more problems with less time per problem, while USACO contests usually include fewer problems with more time available.

Because of that difference, a problem’s Codeforces rating may not translate directly to a USACO division. The FAQ may need to better explain that these ranges are estimates rather than strict boundaries.

There is also some uncertainty in the issue thread because a later maintainer comment suggests that Bronze and Silver may already be reasonably accurate. Because of this, I plan to make a conservative documentation change rather than immediately changing all ranges without guidance.

### Proposed Solution

My proposed solution is to make a small, careful update to the FAQ section about Codeforces ratings and USACO divisions.

Possible solution options include:

1. Clarifying that the rating ranges are approximate estimates.
2. Explaining that USACO gives more time per problem, so direct comparison to Codeforces ratings is imperfect.
3. Updating Gold and Platinum ranges if maintainers confirm those are the main ranges that need changes.
4. Avoiding major changes to Bronze and Silver unless maintainers request them.

If the maintainers respond with specific guidance, I will follow their preferred scope.

### Implementation Plan

Using UMPIRE framework (adapted):

**Understand:** The problem is that the FAQ’s comparison between Codeforces ratings and USACO divisions may be inaccurate or unclear. The fix should make the FAQ more helpful for students trying to understand how Codeforces difficulty roughly maps to USACO levels.

**Match:** I will look for similar FAQ entries in the USACO Guide repository to match the existing style, tone, formatting, and MDX structure.

**Plan:**

1. Locate the FAQ source file that contains the Codeforces rating comparison.
2. Read the surrounding FAQ entries to understand tone and formatting.
3. Draft a small documentation update that clarifies the approximate nature of the rating ranges.
4. Decide whether to adjust specific ranges based on maintainer feedback or issue discussion.
5. Preview or build the documentation locally if required by the contribution guide.
6. Submit a pull request with a clear summary of the documentation change.

**Implement:** Not started yet. I will add links to my branch and commits once implementation begins in Phase II/III.

**Review:** Before submitting a pull request, I will check that the wording is clear and concise, the change stays focused on the issue, the FAQ matches the USACO Guide writing style, the MDX formatting is correct, and I did not make unsupported claims about exact rating boundaries.

**Evaluate:** I will verify the change by checking the rendered FAQ page, either locally or through the repository’s recommended preview/build process. I will also make sure the updated text addresses the concern raised in issue #5024.

---

## Testing Strategy

### Unit Tests

* [ ] Test case 1: Confirm whether the project requires formatting or lint checks for MDX files.
* [ ] Test case 2: Run any recommended documentation checks from the contribution guide.
* [ ] Test case 3: Confirm that the edited FAQ file has valid Markdown/MDX formatting.

### Integration Tests

* [ ] Integration scenario 1: Build or preview the documentation site if required.
* [ ] Integration scenario 2: Confirm that the FAQ page renders without formatting errors and that internal links/anchors still work.

### Manual Testing

Manual testing will include opening the FAQ page locally or through a preview, finding the Codeforces ratings FAQ section, reading the updated wording as a student/user, checking that the explanation is clear and not misleading, and confirming that the change does not affect unrelated FAQ sections.

---

## Implementation Notes

### Week 1 Progress

During Phase I, I reviewed the CodePath curated issue list and inspected several possible issues. I rejected issues that appeared already claimed, had linked pull requests, had broad scope, or required deeper technical knowledge than was realistic for a first contribution.

I selected USACO FAQ CF Ratings #5024 because it is a good first issue, focused on documentation/content, and appears manageable for the program timeline. I announced my claim in the CodePath issue-selection Slack channel, forked the USACO Guide repository under my GitHub account, and created this public contribution README repository.

### Week 2 Progress

Not started yet. Phase II will focus on setting up the local development environment, locating the FAQ source file, reproducing/confirming the current documentation issue, and creating a more detailed solution plan.

### Code Changes

* **Files modified:** None yet.
* **Key commits:** None yet.
* **Approach decisions:** I chose a documentation/content issue to keep the first contribution focused and realistic while still contributing something useful to an open-source educational project.

---

## Pull Request

**PR Link:** Not submitted yet.

**PR Description:** Draft idea:

This PR updates the USACO FAQ section that compares Codeforces ratings to USACO divisions. The goal is to clarify that the rating ranges are approximate and that Codeforces and USACO contests are not directly comparable because of differences in contest structure and time per problem.

**Maintainer Feedback:**

* No maintainer feedback received yet.

**Status:** Not submitted yet.

---

## Learnings & Reflections

### Technical Skills Gained

So far, I learned how to evaluate open-source issues more carefully before choosing one. I practiced checking for assignees, linked pull requests, recent comments, maintainer activity, labels, scope, and whether an issue is realistic for a first contribution.

I also learned the difference between a forked project repository and a separate contribution README repository for tracking my CodePath progress.

### Challenges Overcome

One challenge was that several issues that looked good in the curated list were already being worked on or had recent comments from other contributors. I reviewed multiple options before choosing this issue.

Another challenge was that I could not directly mark the issue as claimed in the course sheet, so I announced my claim in the CodePath issue-selection Slack channel instead.

### What I'd Do Differently Next Time

Next time, I would check the GitHub issue comments, assignees, and linked pull requests earlier before getting attached to an issue. I would also compare several issues side by side using the CodePath checklist before making a final choice.

---

## Resources Used

* GitHub issue: https://github.com/cpinitiative/usaco-guide/issues/5024
* Original repository: https://github.com/cpinitiative/usaco-guide
* My fork: https://github.com/a-pena/usaco-guide
* CodePath AI301 Phase I instructions
* CodePath issue-selection Slack channel
