# Contributing

This repository relates to activities in the Internet Engineering Task Force
([IETF](https://www.ietf.org/)). All material in this repository is considered
Contributions to the IETF Standards Process, as defined in the intellectual
property policies of IETF currently designated as
[BCP 78](https://www.rfc-editor.org/info/bcp78),
[BCP 79](https://www.rfc-editor.org/info/bcp79) and the
[IETF Trust Legal Provisions (TLP) Relating to IETF Documents](http://trustee.ietf.org/trust-legal-provisions.html).

Any edit, commit, pull request, issue, comment or other change made to this
repository constitutes Contributions to the IETF Standards Process
(https://www.ietf.org/).

You agree to comply with all applicable IETF policies and procedures, including,
BCP 78, 79, the TLP, and the TLP rules regarding code components (e.g. being
subject to a Simplified BSD License) in Contributions.

## Working Group Information

Discussion of this work occurs on the [Preparation and Comparison of Internationalized Strings
Working Group mailing list](mailto:precis@ietf.org)
([archive](https://mailarchive.ietf.org/arch/browse/precis/),
[subscribe](https://www.ietf.org/mailman/listinfo/precis)).
In addition to contributions in GitHub, you are encouraged to participate in
discussions there.

**Note**: Some working groups adopt a policy whereby substantive discussion of
technical issues needs to occur on the mailing list.

You might also like to familiarize yourself with other
[Working Group documents](https://datatracker.ietf.org/wg/precis/documents/).

## GitHub Workflow

Here is how we (Takahiro Nemoto and Peter Saint-Andre) work on this document:

1. File a GitHub issue.

2. Assign the issue to @fightingnemo or @stpeter.

3. The assignee creates a branch for that issue, such as:

   git checkout -b issue123

4. The assignee works in that branch and then checks in changes:

   git commit -m "commit message here" draft-nemoto-precis-unicode

   git push --set-upstream origin issue123

5. The assignee creates a pull request and requests a review from the other person.

6. After the other person approves the pull request, the assignee merges it into main.

That's it!
