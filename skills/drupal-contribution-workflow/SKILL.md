---
name: drupal-contribution-workflow
description: Prepare a Drupal.org contribution from an issue or GitLab work item through a shared issue fork, tests, and merge request. Guide independent review and maintainer handoff or explicitly approved merge and closeout. Use for upstream contributions; releases are outside scope.
---

# Drupal contribution workflow

Start with the project or issue URL, the requested change, and the contributor's intended role. A contributor can finish this workflow by handing a tested merge request (MR) to a maintainer. Follow the target project's contribution guide, review rules, and branch conventions.

## Establish the scope

1. Follow the project page's **Issues** link to the active tracker. Read the full discussion, including prior decisions and linked work. Resolve the issue's *project and number* together. GitLab work item numbers can repeat across projects. Use full URLs across trackers. [Drupal issue queues and work items](https://www.drupal.org/docs/develop/issues/gitlab-issues-for-drupalorg-projects)
2. Identify the canonical target branch, existing issue fork, active branches, open MRs, and any maintainer instructions. Reuse the matching work. Coordinate with an existing MR's author before adding AI-assisted changes to their branch. Create missing records only when the requested scope includes those actions.
3. Agree on an observable result, such as which failing test will pass or which documented behavior will change. For a planning request, return the proposed change, tests, and open questions.

Before using automation to change anything on Drupal.org or its project infrastructure, verify the infrastructure team's approval covers the tool and use case, the project permits the operation, and the contributor has authorized it. A working access token confirms authentication only. Respect limits on passive reads, including rate limits and blocks. When approval or access is missing, work from local files or material the contributor supplies. Prepare the diff, tests, branch details, and drafts for a human to submit manually. [Drupal automation policy](https://www.drupal.org/drupalorg/docs/apis/use-of-automation-tools-including-ai)

## Prepare the change

1. Use the shared fork associated with the issue. Inspect its remote and branch before committing or pushing. Push implementation commits only to the agreed branch in that fork. Preserve other contributors' changes and authorship across rebases or backports.
2. Implement the agreed behavior. Run the project's relevant tests and static checks. For a bug fix, show what fails on the base revision and what passes with the change when reproducible. Investigate failed CI and retest the affected change. If a pipeline runs only after an MR opens, use a draft until required checks pass. Record untested environments and blockers explicitly.
3. Before public submission, have the responsible contributor inspect and verify the proposed code and text, dependencies, and licensing. Have them describe the change in their own words and respond to reviewer feedback. For significant AI-generated code or text, ask them to write the disclosure for the project's template or the corresponding submission. Keep public reports focused on reproducible results and public links. [Drupal AI contribution policy](https://www.drupal.org/docs/develop/issues/issue-procedures-and-etiquette/policy-on-the-use-of-ai-when-contributing-to-drupal)
4. Open or update the MR from the issue-fork branch to the verified canonical branch. Link the issue and MR, use the project's title and description conventions, and record the resulting change, tests, and remaining work. Set the appropriate review state when ready. Read the saved issue and MR to confirm their branches, links, and state.

## Hand off for review

Give the reviewer the issue and MR links and titles, source and target branches, tested head SHA, CI result, and any unresolved discussions or coverage gaps. End here for a contributor. Under this workflow the MR is the decision point before any merge.

The project determines who can mark work reviewed and tested by the community (RTBC), approve, and merge. Obtain a real review of the current change by an eligible independent reviewer. Record RTBC and GitLab approval separately where both are required. An agent's review, another login for the same implementer, or a successful pipeline cannot establish independent human review. When the user requests only a review, report findings tied to the actual diff and tests.

## Complete a maintainer-authorized merge

1. Check credit and attribution with the maintainer. Use the project's commit format and contribution record to prepare the squash message, including its body and contributor trailers. Present the entire message with the MR, target, and reviewed head, and obtain explicit approval to merge with that text. [Drupal maintainer merge guide](https://www.drupal.org/docs/develop/git/git-for-drupal-project-maintainers/reviewing-and-merging-merge-requests)
2. Immediately before merging, recheck the source SHA, target, required CI, approvals, conflicts, and open discussions. If the head, target branch, or message differs from the approved proposal, stop. Review and retest affected changes and obtain approval for the revised proposal. If a condition fails or permissions are missing, report the specific blocker and the person who can resolve it.
3. After the authorized squash merge, read the target commit and verify its SHA, exact message, accepted changes, and post-merge CI where configured. Update the issue's resolution and linked tasks according to project practice. The maintainer confirms credit for actual contributions in the Drupal.org contribution record. Reopen the saved records and report any outstanding action. [Drupal contribution credit](https://www.drupal.org/docs/develop/issues/issue-procedures-and-etiquette/granting-credit-to-issue-contributors)
4. Clean up only confirmed local work for the accepted change. With squash merges, verify the merged MR and changes on the target before retiring a local branch. Preserve shared issue forks, other contributors' branches, release tags, and unmerged work. Finish with the issue and MR links, target commit, CI result, credit status, and any handoff.
