# Project Description

This document reviews changes in Unicode between version 6.3 and version 15.0.0
in order to determine the impact (if any) on the PRECIS framework specified in
RFC 8264. Essentially this is similar to RFC 9233 for IDNA2008, except for PRECIS.

Note: the filename is draft-nemoto-precis-unicode - do not add a version number 
      such as -01 since that will be added automatically by the tooling.

# Workflow

Here is how we work:

1. File an issue.

2. Assign the issue to @fightingnemo or @stpeter.

3. The assignee creates a branch for that issue, such as:

   git checkout -b issue123

4. The assignee works in that branch and then checks in changes:

   git commit -m "commit message here" draft-nemoto-precis-unicode

   git push --set-upstream origin issue123

5. The assignee creates a pull request and requests a review from the other person.

6. After the other person approves the pull request, the assignee merges it into main.

That's it!
