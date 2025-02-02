# Guide for Editors

## Editor in Chief

The Editor in Chief serves for 3 months or a time agreed to by all members of
the editorial board. The Editor in Chief fulfills the following roles:

- Watches all issues posted to the software-review repo.
- Assigns package submissions to other editors, including self, to handle. For the most part, this position rotates among pyOpenSci editors. However, in some cases, an editor may be assigned if the Editor in Chief thinks someone is particularly well-suited to the contents of a package, or if an editor is not able to support the review process at that time due to time or other conflicts.
- Raises scope/overlap issue with all editors if they see an ambiguous case. This may also be done by handling editors (see below). To initiate discussion, this is posted to the pyOpenSci Slack software review channel, tagging all editors.
- Responds to pre-submission inquiries and `meta` issues posted to the software-review and software-review-meta repos, similarly pinging channel if discussion is needed. Any editor should feel free to step in on these. See [this section](#responding-to-out-of-scope-submissions) about how to respond to out-of-scope (pre-) submissions.
- Responds to referrals from JOSS or other publication partners.
- Monitors the review process pace and reminds other editors to move packages along as needed.

## Editor Checklist

- Tag issue with `1/editor-checks` tag and assign a main editor. Please strive to finish the checks and start looking for reviewers within 1 week.
- Use the [editor template](../appendices/templates#editors-template) to guide initial checks and record your response to the submission.
- Check that template has been properly filled out.
- Check against policies for [fit](aims_scope#package-categories) and [overlap](aims_scope#package-overlap). If reject, see [this section](#responding-to-out-of-scope-submissions) about how to respond.
- Check that mandatory parts of template are complete.  If not, direct authors toward appropriate instructions.
- Run automated tests: spelling, linting, etc ... will be filled in later.
- For packages needing continuous integration on multiple platforms ([criteria in this section of the packaging chapter](../packaging/packaging_guide#continuous-integration)) make sure the package gets tested on multiple platforms (having the package built on both Travis and AppVeyor for instance).
- Wherever possible when asking for changes, direct authors to automatic tools and online resources.
- If initial checks show major gaps, request changes before assigning reviewers.
- If the package raises a new issue for pyOpenSci policy, create an issue on [pyOpenSci's governance repo](https://github.com/pyOpenSci/governance)

### Look for and assign reviewers:

#### Tasks

- Use the [email template](../appendices/templates#review-request-template) if needed for inviting reviewers
    -  When inviting reviewers, include something like "if I don't hear from you in a week, I'll assume you are unable to review," so as to give a clear deadline when you'll move on to looking for someone else.
- Assign a due date 3 weeks after all reviewers have been found.
- Once two or more reviewers are found, assign reviewers by tagging in the issue with the following format:
```  
Reviewer: @githubname1
Reviewer: @githubname2
Due date: YYYY-MM-DD
```
-   Switch numbered tag `to 3/reviewers-assigned` once reviewers are assigned.

#### Where to look for reviewers?

As a (guest) editor, use:
* the potential suggestions made by the submitter(s), (although submitters may have a narrow view of the types of expertise needed.  We suggest not using more than one of suggested reviewers).
* the authors of [pyOpenSci packages](https://github.com/pyOpenSci/).

When these sources of information are not enough:
* ping other editors for ideas.
* look for users of the package or of the data source/upstream service the package connects to (via their opening issues in the repository, starring it, citing it in papers, talking about it on Twitter).
* You can also search for authors/maintainers of related packages on [PyPI](https://pypi.org/search/).

#### Criteria for choosing a reviewer

Here are criteria to keep in mind when choosing a reviewer. You might need to piece this information together by searching CRAN and the potential reviewer’s GitHub page and general online presence (personal website, Twitter).

* Has not reviewed a package for us within the last 6 months.
* Some package development experience.
* Some domain experience in the field of the package or data source.
* No [conflicts of interest](peer_review_proc#conflict-of-interest).
* Try to balance your sense of the potential reviewer’s experience against the complexity of the package.
* Diversity - with two reviewers both shouldn’t be cis white males.
* Some evidence that they are interested in openness or Python community activities, although blind emailing is fine.

Each submission should be reviewed by _two_ package reviewers. Although it is fine for one of them to have less package development experience and more domain knowledge, the review should not be split in two.  Both reviewers need to review the package comprehensively, though from their particular perspective.  In general, at least one reviewer should have prior reviewing experience, and of course inviting one new reviewer expands our pool of reviewers.

### During review:

-   Check in with reviewers and authors occasionally. Offer clarification and help as needed.
-   In general aim for 3 weeks for review, 2 weeks for subsequent changes, and 1 week for reviewer approval of changes.
-   Upon all reviews being submitted, change the review status tag to `4/review-in-awaiting-changes` to update the reminder bot.
-   If the author stops responding, refer to [the policies](peer_review_proc#review-process-guidelines) and/or ping the other editors in the Slack channel for discussion. Importantly, if a reviewer was assigned to a closed issue, contact them when closing the issue to explain the decision, thank them once again for their work, and make a note in our database to assign them to a submission with high chances of smooth software review next time (e.g. a package author who has already submitted packages to us).
-   Upon changes being made, change the review status tag to `5/awaiting-reviewer-response`.

### After review:

-   Change the status tag to `6/approved`.
-   You can use the [approval comment template](../appendices/templates#approval-comment-template).
-   Add review/er information to the review database.
-   Ask authors to migrate to `pyOpenSci`
    -   Create a two-person team in pyOpenSci's "pyOpenSci" GitHub organization, named for the package, with yourself and the package author as members.
    -   Have the author transfer the repository to `pyOpenSci`
    -   Go to the repository settings in the "pyOpenSci" GitHub organization and give the author "Admin" access to the repository.
-   Ask author to:
    -   Change any needed links, such those for CI badges
    -   Re-activate CI services
        -  For Travis, activating the project in the pyOpenSci account should be sufficient
        -  For AppVeyor, tell the author to update the GitHub link in their badge, but do not transfer the project: AppVeyor projects should remain under the authors' account. The badge is `[![AppVeyor Build Status](https://ci.appveyor.com/api/projects/status/github/pyOpenSci/pkgname?branch=master&svg=true)](https://ci.appveyor.com/project/individualaccount/pkgname)`.
        -  For Codecov, the webhook may need to be reset by the author.
-   Add a "peer-reviewed" topic to the repo.
-   Close the software-review issue.


### Responding to out-of-scope submissions
Thank authors for their submission, explain the reasons for the decision, and direct them to other publication venues if relevant, and to the pyOpenSci governance repo issues for discussion. Use wording from Aims and scope in particular regarding the evolution of scope over time, and the overlap and differences between unconf/staff/software-review development.
