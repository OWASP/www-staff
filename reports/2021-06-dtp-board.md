---

title: 2021-06 Director of Technology and Projects Board Report
date: 2021-06
author: Harold L. Blankenship
layout: col-generic
image: https://owasp.org/assets/images/people/staff_harold.jpg
---
![Harold Image]({{page.image}}){:width='75px'} {{ page.author }}

## Projects
Project status can always be found at the [Projects Status](/projects/status/) page

To re-iterate:

|---|---|
| Number of Projects | 221 |
| New Projects | 9 |
| Projects Needing Website Update | 90 |

[Project Committee](https://owasp.org/www-committee-project/) is continuing its work on the Project Graduation procedures (top priority), Project Policy, Contribution policies for projects, and the project handbook.

## Technology
### Membership Portal
Membership Portal will be rolling out July 1st.  If you have feedback for additions to add for Membership Resources, please let me know.

### OWASP Email Clean-up
The OWASP Email inventory is currently saturated with email addresses for non-members and non-leaders and it does not provide a clear picture of persons actively engaged in OWASP. As an owasp email address and the Google services that come with it are a membership benefit, these email addresses are to be restricted to one of the following groups:
* Leaders of chapters, projects, events, and committees
* Members

As part of the clean-up process, beginning July 1st, persons having access to Google services through an owasp email address that are not members of the above, will be notified that their @owasp.org email address will be deactivated within 15 days. They will receive a further such communication at 7 days and a final one at 1 day. After that, the email will be deactivated (not deleted). The person who owns the @owasp.org email address will be given the opportunity to become a member or a leader in order to retain their @owasp.org email address.  This process will continue to run, once initiated, such that people who drop away from membership/leadership will have their associated email address deactivated. This process has been communicated through numerous channels including @owasp.org email, the Mailchimp OWASP Main audience, Slack, Twitter, LinkedIn, and Facebook. Communications have gone out, thus far on 6/7 and 6/8, 6/14 and 6/15, 6/21 and 6/22. The remaining schedule of communication is as follows:

- 6/25/2021	Email owasp.org, OWASP Main Audience
- 6/26/2021	Twitter, Slack, Facebook, and LinkedIn
- 6/30/2021	Email owasp.org, OWASP Main Audience
- 6/30/2021	Email OWASP Main Audience		FALSE
- 6/30/2021	Twitter, Slack, Facebook, and LinkedIn

#### Email Clean-up Deep-dive
The following is a simplified procedure for this process:

```
for each user in Google for OWASP Foundation
    if user has active membership or user is leader
       skip
    end if

    if user has not been notified
       send 15 day notice
       update notification information
    else if user has been notified 1 time and days since last notification >= 8:
       send 7 day notice
       update notification information
    else if user has been notified 2 times and days since last notification >= 6:
       send 1 day notice
       update notification information
    else if user has been notified 3 times
        deactivate user
    end if
end for
```

Separately, when a person becomes a member of one of the above groups, the data for the above notifications gets removed/cleaned.

This process has been tested with the following groups of people
* Active members
* Leaders with active membership
* Leaders with non-active membership
* Non-members

Tests involving the above groups were correctly identified:
* Do not deactivate
* Do not deactivate
* Do not deactivate
* Deactivate after 3 notifications

Further, there is a failsafe capability such that, if something goes awry, the whole process can be disabled with a single configuration change.  In addition, the data can be cleaned and re-started, if necessary.