---

title: Website Re-launch
layout: full-width

---

## Overview

Before December 20, 2019, the Foundation will launch a new website designed to engage visitors and professionally convey the value of our collective work. Rather than just re-skinning our current wiki or placing a simplified landing page in front of our site, we plan to migrate to an entirely new platform. 

The project must better connect with our developer audience and be valuable when visited on a variety of devices. It must be possible for elements of our site to be managed by our communities or through automation and any platform change must retain these attributes as well as ensuring continuity of analytics, permissions design, and redirect of inbound links. A proof of concept will be complete by July 1. Once the new website is launched, the wiki will be archived through 2020 for historical purposes.

Upon the completion of this project, OWASP.org will be hosted in Github. The architecture will place a repository for each logical entity of the foundation in one organizational account. For instance, there would be a repo for each chapter, project, event, and several other organizational entities. This design will increase source control and allow us to connect visitors with the content that is of interest to them.

## Prioritized User Journeys
1. Discover and connect with a local chapter
1. Learn, engage, or contribute to an OWASP project
1. Decide to attend an OWASP sponsored event
1. Learn more about the Foundation
1. Donate money to OWASP
1. Become an individual member of OWASP
1. Become a corporate member of OWASP
1. Review the policies, financial, and governance design/practices of the Foundation
1. Decide to host a project with OWASP
1. Subscribe to emails from the Foundation

## Goals
* Launch Website on or before Dec 20, 2019
* Ensure top 500 pages are migrated before Dec 11, 2019
* Redirect for inbound search traffic ready at launch
* Boost visitor engagement with chapters, projects, and membership
* Static Mediawiki instance launched Dec 11, 2019
* Retire full Mediawiki instance before Dec 15, 2020

## Milestones
* [ ] 2019-10-10, Staff Projects migrated and in production
* [ ] 2019-10-30, Events pages migrated and in production
* [ ] 2019-10-30, Policy pages migrated and ready for Board Approval
* [ ] 2019-11-28, Corporate pages migrated (not production)
* [ ] 2019-12-06, Chapter pages migrated (not production)
* [ ] 2019-12-06, Project pages migrated (not production)
* [ ] 2019-12-13, Redirect system in place and ready for launch
* [ ] 2019-12-13, Validate in-bound search redirect working on events/policy pages
* [ ] 2019-12-20, Website Launch [Harold]
* [ ] 2019-12-18, Validate Google Analytics instance running
* [ ] 2019-12-18, Validate search redirect working site-wide
* [ ] 2020-01-15, Validate Meetup Connector
* Donation Form
* Membership Form
* Events Form
* [ ] In an unordered list (billeted) list major milestones in chronological order
* [ ] Use the syntax of 2019-01-19, Milestone name, [Name of Owner]
* [x] When milestones are completed, mark them with an "x"
* [ ] A milestone isn't everyone’s to-do list, it is the high level tasks of the project
* [ ] If you have more than 20 milestones, you’re being too granular
* [ ] 2020-01-01, New Year's Eve Holiday, [All]
* [ ] 2020-07-04, Independence Day (US) Holiday, [All]


## Milestones (Completed)
* 2019-06-01, Proof of concept complete validating Requirements (below)
* 2019-06-03, Site Map designed
* 2019-06-15, Draft wireframe Complete https://www.owasp.org/images/5/5d/Owasp_wireframes.pdf
* 2019-06-10, Template Selected and design underway for non-supported pages
* 2019-07-08, Draft template installed on site
* 2019-09-01, v2 Template installed
* 2019-09-01, Determine site-wide Search tool/solution [Harold]
* 2019-09-05, Rollout for Leaders starting at Global AppSec DC and continuing at AMS


## Leadership

* [Harold Blankenship, Project Leader](mailto:harold.blankenship@owasp.com?Subject=Website%20Relaunch)
* [Mike McCamon](mailto:mike.mccamon@owasp.com?Subject=Website%20Relaunch)

##  Requirements
1. https
1.  Custom domain - owasp.org
1. Continued use of Google Analytics or similar functionality
1. Maintain inbound search love with redirect at launch
1. Inherited navigation for information hierarchy
1. Credential management
  1. Committees - only an org email
  2. Control who is repo owner
1. Cannot have advertisements unless controlled by OWASP
1. Restrict cross-domain scripting (except Analytics)
1. Google crawlers successfully use rendered content of page
1. Ability to embed YouTube videos
1. Move to a SaaS provider and no longer host ourselves
1. Free or close to free
1. Nice to have: Decorate rendered certain pages with WATCH/STAR repo tools
1. Nice to have: Search content in site
1. Nice to have: ability to duplicate Meetup widget functionality (pull in Meetup JSON and render "future meetings")

##  Required Templates
* Home page
* Chapter
* Project
* Event
* Entity Meta (landing page for chapters or projects or events)
* Documentation Page
* Article (blog)

## Repo Naming Top level
* owasp.github.io - home/landing pages, board & staff, about us, careers, finance, governance (By-Laws), About Membership
* www-site-theme - master json for menus, templates, common assets, header, footer
* www-board - board meetings
* www-staff - staff projects
* www-policy - overview, membership, sponsorship, finance, donations, handbooks, guidelines
* www-community - future "free and open" space
* www-members - future place for member pages
* www-event-2020-GlobalAppSecSF
* www-event-2020-GlobalAppSecDublin
* www-event-2020-AppSecDaysCalifornia
* www-chapter-los-angeles
* www-chapter-amsterdam
* www-chapter-melbourne
* www-project-zap
* www-project-topten
* www-committee-wia
* www-committee-projects

