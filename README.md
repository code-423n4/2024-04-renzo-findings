# Renzo Audit

Audit findings are submitted to this repo.

Unless otherwise discussed, this repo will be made public after audit completion, sponsor review, judging, and issue mitigation window.

**Contributors to this repo:** prior to report publication, please review the [Agreements & Disclosures](../../issues/1) issue.

**Note that when the repo is public, after all issues are mitigated, your comments will be publicly visible; they may also be included in your C4 audit report.**

---

# Review phase

Sponsors have three critical tasks in the audit process: Reviewing the two lists of curated issues, and once you have mitigated your findings, sharing those mitigations. 

1. [Respond to curated High- and Medium-risk submissions ↓](#1-respond-to-curated-high--and-medium-risk-submissions)
2. [Respond to curated Low/Non-critical submissions and Gas optimizations ↓](#2-respond-to-curated-lownon-critical-submissions)
3. [Share your mitigation of findings (optional) ↓](#3-share-your-mitigation-of-findings-optional)

Note: It’s important to be sure to **only review issues from the curated lists.** There are two lists of curated issues to review, which filter out duplicate issues that don't require your attention.

<hr>
<details>
<summary>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<h2>Types of findings</h2> (expand to read more)</summary>

### High or Medium risk findings

Wardens submit issues without seeing each other's submissions, so keep in mind that there will always be findings that are duplicates. For all issues labeled `3 (High Risk)` or `2 (Medium Risk)`, these have been pre-sorted for you so that there is only one primary issue open per unique finding. All duplicates have been labeled `duplicate`, linked to a primary issue, and closed.

### QA reports

Any warden submissions in the QA category are submitted as bulk listings of issues and recommendations:

- **[QA reports](https://docs.code4rena.com/awarding/judging-criteria#qa-reports-low-non-critical)** include *all* low severity and non-critical findings from an individual warden.
</details>
<hr>

## 1. Respond to curated High- and Medium-risk submissions

### [High/Medium-risk findings for review →](../../issues?q=is%3Aopen+is%3Aissue+label%3A%222+(Med+Risk)%22%2C%223+(High+Risk)%22+-label%3A%22unsatisfactory%22%2C%22insufficient+quality+report%22%2C%22sponsor+acknowledged%22%2C%22sponsor+confirmed%22%2C%22sponsor+disputed%22+)

<sup>This curated list will shorten as you work. [View the original, longer list →](../../issues?q=is%3Aopen+is%3Aissue+label%3A"2+(Med+Risk)"%2C"3+(High+Risk)"+-label%3A"unsatisfactory"%2C"insufficient+quality+report")</sup>

For each curated High or Medium risk finding, please:

### 1. Label as one of the following:

- `sponsor confirmed`, meaning: "Yes, this is a problem and we intend to fix it."
- `sponsor disputed`, meaning either: "We cannot duplicate this issue" or "We disagree that this is an issue at all."
- `sponsor acknowledged`, meaning: "Yes, technically the issue is correct, but we are not going to resolve it for xyz reasons."

Add any necessary comments explaining your rationale for your evaluation of the issue. Judges have the ultimate discretion in determining validity and [severity](https://docs.code4rena.com/roles/wardens/judging-criteria#estimating-risk-tl-dr) of issues, as well as whether/how issues are considered duplicates. However, sponsor input is a significant criterion.

Note: Adding or changing labels other than those in this list will be automatically reverted by our bot, which will note the change in a comment on the issue.

<hr>

## 2. Respond to curated Low/Non-critical submissions

### [Low/Non-critical submissions for review →](../../issues?q=is%3Aopen+is%3Aissue+-label%3A"sponsor+acknowledged"%2C"sponsor+confirmed"%2C"sponsor+disputed"+label%3A"QA+(Quality+Assurance)"+sort%3Acreated-asc)

<sup>This curated list will shorten as you work. [View the original, longer list →](../../issues?q=is%3Aopen+is%3Aissue+label%3A"QA+(Quality+Assurance)"+sort%3Acreated-asc)</sup>

- Leave a comment for the judge on any reports you consider to be particularly high quality. (These reports will be awarded on a curve.)
- Add the `sponsor disputed` label to any reports that you think should be _completely_ disregarded by the judge, i.e. the report contains no valid findings at all.

## Once Step 1 and 2 are complete

When you have finished labeling and responding to findings, drop the C4 team a note in your private Discord backroom channel and let us know you've completed the sponsor review process. At this point, we will pass the repo over to the judge to review your feedback while you work on mitigations.


<hr>

## 3. Share your mitigation of findings (Optional)

*Note: this section does not need to be completed in order to finalize judging. You can continue work on mitigations while the judge finalizes their decisions and even beyond that. Ultimately we won't publish the final audit report until you give us the OK.*

For each finding you have confirmed, you will want to mitigate the issue before the contest report is made public.

### If you are planning a Code4rena mitigation review:

1. In your own Github repo, create a branch based off of the commit you used for your Code4rena audit, then
2. Create a separate Pull Request for each **High or Medium risk** C4 audit finding (e.g. one PR for finding H-01, another for H-02, etc.)
3. Link the PR to the issue that it resolves within your contest findings repo.

Most C4 mitigation reviews focus exclusively on reviewing mitigations of High and Medium risk findings. Therefore, QA and Gas mitigations should be done in a separate branch. If you want your mitigation review to include QA or Gas-related PRs, please reach out to C4 staff and let’s chat!

If several findings are inextricably related (e.g. two potential exploits of the same underlying issue, etc.), you may create a single PR for the related findings.

### If you aren’t planning a mitigation review

1. Within a repo in your own GitHub organization, create a pull request for each finding.
2. Link the PR to the issue that it resolves within your contest findings repo.

This will allow for complete transparency in showing the work of mitigating the issues found in the contest. If the issue in question has duplicates, please link to your PR from the open/primary issue.
