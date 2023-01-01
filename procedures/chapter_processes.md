---

title: Chapter Procedures (WIP)
layout: col-sidebar

---
v2021.01.07

## Chapter Processes 
To create a new chapter repository in GitHub and CRM record of chapter and leaders.(minmum of 2 leaders to start)
**Relevant Policy: [Chapter Policy](https://owasp.org/www-policy/operational/chapters)**    

**Chapter Support - Start a New Chapter request subitted.**
* Contact Us or on owasp.org> chapter page click and submit request ticket NFRSD ticket# 
  * Review for a minimum of 2 leaders & all required information is included.

**Leaders owasp.org email address MANUAL creation**
   * Google Admin - Admin Console   
![Chapter Processes Admin]({{site.base_url}}/assets/images/GoogleAdmin_User.png)
   * Click User   
   * Click Add New User   
![Add New User]({{site.base_url}}/assets/images/Add_new_user.png)
    * Pop Box appears
    * Fill in First nam
    * Fill in Last name
    * Primary email john.smith@owasp.org
    * Secondary email is the personal email address 
    * Email User Sign-in Info   
![Email Login]({{site.base_url}}/assets/images/Email_login_info.png)
    * Send   
**The OWASP.org email address that is to be used for the leader in leader.md file in chapter repository.**
 Leader will receive a Google WorkSpace email like below. (link is only good for 48 hours)
![Chapter Processes Admin]({{site.base_url}}/assets/images/GoogleWorkspace_email.png)
  
**Slackbot command "/chapter-create"**
* Generates a templated form to create GitHub chapter repository & CRM records.
   * Chapter City name ONLY
   * Chapter leader’s name
   * Chapter leader owasp.org emails
   * City
   * Country
   * Region -6 choices: Africa, Asia, Europe, North America, Oceania, and South America
* SUBMIT to create the GitHub chapter repository and Copper CRM record.
![Slackbot template]({{site.base_url}}/assets/images/chapter_slackbot_temp.png)

**CRM (Copper) MANAUL Entry**
* Chapter file (OWASP-City) 
  * Add JIRA/NFRSD ticket URL or number in field.
  * Check city, country, and region fields were populated
  * Chapter status is set to Active
  * All leaders are related on rightside under "People"
* People - Leader’s record - MANUAL
   * Enter secondary personal email address
   * Tag as Chapter leader
* Send out a Welcome letter in email to leaders.
* Resolve and Close the JIRA ticket. 
**SLA for first response is 72 hours and 144 working hours to complete; pauses when ticket is set to "Waiting for Customer Response"**
**Issues:**
 * All of the owasp.org emails need to be reviewed and validated that users are current members or leaders.
 * JIRA tickets need a complete overhaul.  Update requirements and use of correct fields and workflows. Stop mass grouping Membership, Chapters, Projects, Corporate Members & Sponsors, Events, Marketing and Other

## Add/Change Chapter Leadership Process - same ticket as New Chapter Request
 Relevant Policy: [Chapter Policy](https://owasp.org/www-policy/operational/chapters) 
    **Remove leader**
    * The Leader(s) stepping down submits the Contact Us - Chapter Support -  Stepping down ticket 
   **Add New leader(s)**
    * Submit Add a new leader to existing chapter ticket 
    * Answer and submit all requested information. (Delay only if the information is missing.)
**SLA for first response is 72 hours and 144 working hours to complete; pauses when ticket is set to "Waiting for Customer Response"**
**Issue:** Membership policy does not address what happens to a complimentary membership if a leader steps down or the chapter is deemed inactive. 
OWASP.org email addresses deactivation did not follow a consistant policy when membership or leadership ended. This was and still is manual process.

## Chapter Reimbursement Process
**Relevant Policy or ED granted:** [Expense Policy](https://owasp.org/www-policy/operational/expense-reimbursement)
  **SLAs:** 
    * To respond to OSD JIRA ticket is 72 working hours.
    * Submit expense for reimbursement within 60 days[Expense Policy](https://owasp.org/www-policy/operational/expense-reimbursement)  
    * AP runs twice a month not sure of the two monthly cut off dates to make the AP run.(Virtual)
**Issue:** SLA reponse from second leader is (7 to 9 days) as listed in Chapter policy for a leaders to respond to the request from the Foundation. 
    
**Request for Shared Services offered to active Chapters at no charge.**
  * Submit ["Contact Us"](https://owasporg.atlassian.net/servicedesk/customer/portal/7/create/72)
    * Chapter Support - Shared Service
    * Description: Type shared service requesting.
     * Zoom (shared account)
     * Google Group
     * Meetup Group (Pro)
 
**SLA for first response is 72 working hours; pauses when ticket is set to "Waiting for Customer Response"**
**Issue:** 
1. Meetup Groups are set up by city location, not region or country. 
2. Some Leaders do not join or use Meetup. 
3. Allowed to use other social media do not post activity on chapter page.
5. Automation not available to truly identify 3 meeting activity but just identifies activity as simply as opening and closing a file in the chapter repository.  







