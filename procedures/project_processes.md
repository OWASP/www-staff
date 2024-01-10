---

title: OWASP Project Procedures
layout: col-sidebar
permalink: /procedures/projects

---

## Archiving a Project
At times it is necessary to archive a project; the project may be old or has become inactive or some other reason (perhaps the leader abandoned the project or no longer has time for it). Archiving a project should follow these general steps:

* In the [OWASP Github](https://github.com/owasp/) find the www-project-[project-name] repository (e.g. https://github.com/owasp/www-projectchapter-example/)
* If the project repository has a README.md file, edit it. Otherwise, create a new README.md file
* Include the following text in the README.md file: 'This project has been archived. The content remains accessible for historical context.'
* Save the file
* Go to the **Settings** tab for the repository
* Find the **Github Pages** section
* Under **Source, Deploy from a branch**, change **Branch** from master or main to None. Save the changes
* On the left, click **Collaborators and Teams**
* Under **Manage Access**, remove everyone listed
* On the left, click on **General**
* Scroll all the way down to the **Danger Zone**
* Click **Archive this repository** and accept warnings



## Creating a Project
When creating a project, the following steps are generally followed:

* Review the JIRA ticket
    * If the ticket has very little information (often the case), just resolve it at Incomplete.
    * Otherwise, change the status to In Progress.
* If the project has anything to do with 'Top 10' or 'Verification Standard' or 'Certification' or 'Server' then flag it for higher evaluation and respond with such.
* If the project does not have anything to do with security or is heavily geared toward offensive security ('hacker-like' activities) choose to either pass on the project (respond with Declined and state reason)
* Otherwise, continue with the following
    * Determine if the leaders already have @owasp.org email addresses and create them if not.
    * perform /project-create in Slack and fill in ALL the details (using the @owasp.org email address for the leader instead of any personal email address).
    * respond to JIRA ticket with Done and the Template for Project created.

