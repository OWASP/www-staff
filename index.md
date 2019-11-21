---

title: Staff Projects
layout: full-width

---

# Staff Projects

[Milestone View](/www-staff/milestones)

<!-- Place this tag in your head or just before your close body tag. -->
<script async defer src="https://buttons.github.io/buttons.js"></script>
<!-- Place this tag where you want the button to render. --><a class="github-button" href="https://github.com/owasp/www-staff"  data-icon="octicon-eye" data-size="large" data-show-count="true" aria-label="Watch ntkme/github-buttons on GitHub">Watch</a>
<!-- Place this tag where you want the button to render. -->
<a class="github-button" href="https://github.com/owasp/www-staff" data-icon="octicon-star" data-size="large" data-show-count="true" aria-label="Star ntkme/github-buttons on GitHub">Star</a>
<!-- Place this tag where you want the button to render. -->
<a class="github-button" href="https://github.com/owasp/www-staff/issues" data-icon="octicon-issue-opened" data-size="large" data-show-count="true" aria-label="Issue owasp/www-staff on GitHub">Issue</a>

Staff Projects are work products primarily done by staff that require either 40+hrs of staff time or have a financial obligation of more than $10,000. **Active** Staff Projects have written plans that include measurable goals, milestones, and should be linked below.  **Prioritized** Staff Projects are in the formation stages and are listed in rank importance. **Unprioritized** Staff Projects are items that lack a plan and are in a "bucket list" until they get prioritized with a project plan. *Note this project list is not the exhaustive list of staff daily work product. These are the key projects above everyday work that is purposefully planned to deliver on the Foundation Goals. Generally the process we will use to implement our plans are: 

*Concept >> Document >> Socialize >> Iterate >> [Approval if needed] >> Plan >> Implement >> Report >> Revisit*

## Active Projects
* [2020 Operating Plan - DRAFT 3](/www-staff/operating-plan/2020) [Mike]
* 2020 Budget (with monthly forecast) [Mike]
* [Website Relaunch](/www-staff/projects/201912-Website-Launch), [Harold]
* Commerce Platform for Website Launch
  * [Donate Form](/www-staff/projects/201911-donate-form)
  * [Membership Form](/www-staff/projects/201911-membership-form)
  * [Event Registration](/www-staff/projects/201912-events-form)
* [Mailchimp as Member CRM](/www-staff/projects/201912-mailchimp)
* Policy and Handbook Reorganization, [Dawn]
* Leader Agreement (Project, Chapter, Event) [Mike]
* [Email List GDPR & Clean Up](/www-staff/projects/201910-Email-Cleanup)
* [2019-Q4 Marketing](/www-staff/projects/201910-marketing)
* Community Managed Events
  * [AppSec California, 21 January, 2020](/www-staff/projects/2020-event-appsec-california)
  * [OWASP SnowFROC, 5 March, 2020](/www-staff/projects/202003-snowfroc)
* Global Partnerships
  * [BlackHat London Dec 2-5, 2019](/www-staff/projects/201912-Blackhat-London), [Lisa]
  * [BlackHat Asia Mar 31- Apr 3, 2020](/www-staff/projects/202003-Blackhat-Asia), [Lisa]
  * [BlackHat USA Las Vegas 2020 Aug 1-6, 2020](/www-staff/projects/202008-Blackhat-Las-Vegas), [Lisa]
  * [DefCon28 Aug 6-9, 2020](/www-staff/projects/202008-Defcon-28), [Lisa]
* Staff Managed Events
  * [Projects Summit Winter, February 20-22, 2020](/www-staff/projects/202002-Projects-Summit-Q1)
  * [Global AppSec - Dublin, June 15-19, 2020](/www-staff/projects/202006-GlobalAppSec-Dublin)
  * [Projects Summit Summer, date TBD](/www-staff/projects/202007-Projects-Summit-Q3)
  * [Global AppSec - San Francisco, October 19-23, 2020](/www-staff/projects/202010-Global-AppSec-SF)
* [Trademark](/www-staff/projects/201902-Trademarks), [Mike]

## Prioritized Projects
* SalesForce New Instance > Migration
  * Invoice Workflow (SalesForce & JIRA)
  * SalesForce Invoicing
  * SalesForce Sales Pipeline
* Backup plan for Meetup

## Unprioritized Projects
* Bi-Annual Signatory/Password Audit Jan/June
* Submittable download stylesheet for owasp.org website

## Recently Completed Projects
* [AppSec Days Melbourne, 1 November, 2019](https://www.owasp.org/index.php/Staff-Projects/20191101-AppSecDay-Melbourne)

## Templates 
* [Blank Template](/www-staff/projects/202001-template)

## Strategies
* Create and share best practices and tools for InfoSec community
* Increase connectedness and engagement within the community.
* Position the Foundation for growth.
* Professionalize administrative and operational tasks and practices.
* Redesign financial model and membership benefits.

## Foundation Goals for 2020
1. Launch updated version of OWASP Top 10 by June 2020.
1. Continue to optimize business operations to overachieve financial and membership targets.
1. Manage two successful global conferences planning three in 2021.
1. Launch Project Summits and AppSec Days to over 500 attendees
1. Increase relevance and reputation of OWASP measured by 10% increase in web traffic.
1. Improve satisfaction with OWASP by survey measured a 5% increase.
1. Increase all classes of membership by 25%

*Vision: Global and open resource for software security*


## Active Projects
{% assign pages = site.pages | sort: 'title' | limit: 10 %}
{% for page in pages %}
   {% if page.path contains 'projects/' %}* [{{ page.title }}](/www-staff{{ page.url }}){% if page.owner %} [{{ page.owner }}]{% endif %}{% endif %}{% endfor %}


