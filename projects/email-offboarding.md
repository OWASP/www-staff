---

title: ORG Domain Email Offboarding
layout: full-width

---

# ORG Domain Email Offboarding

## Overview

To reduce manual work, this project's primary deliverable is a robot that can be nightly run to hygeine the OWASP.org email domain. Notably the primary script will disable owasp.org email addresses of former members and outgoing Leaders. The process will NOT onboard nor reactive "lost" emails as that process is outside the scope of this project. Additionally this project includes a small amount of clean up work with regard to our Stipe Instance. All of these projects will be written in Python and hosted in the OWASP Azure instance.

## Goals

1. On-demand script to convert email address in Stripe to lowercase
2. On-demand script to remove "non-customers" from Stripe
3. Script that can be ran nightly to disable owasp.org email address which are no longer members or Leaders

## Milestones

- [x] 2020-09-17, Contract signed in Upwork and project underway, [Mike]
- [x] 2020-09-18, Kickoff call [Mike]
- [x] 2020-09-18, Onboard Christian to Azure and Stripe, [Harold]
- [ ] 2020-09-23, Update leaders.json to include "Date Created information", [Harold]
- [ ] 2020-09-27, Project "A" Complete ready for deployment, [Christian]
- [ ] 2020-09-29, Project "A" Regression testing complete, [Harold]
- [ ] 2020-10-01, Deploy Project "A" into production, [Harold]
- [ ] 2020-10-05, Project "B" Complete ready for deployment, [Christian]
- [ ] 2020-10-07, Project "B" Regression testing complete, [Harold]
- [ ] 2020-10-08, Deploy Project "B" into production, [Harold]
- [ ] 2020-10-15, Validation of six-days of production for errors, [Harold]
- [ ] 2020-10-16, Remove Stripe customers marked cleanup-customer = "true", [Harold]
- [ ] 2020-10-16, Project Complete, [Mike]


## Leadership
* [Harold Blankenship - Lead](mailto:Harold.blankenship@owasp.com?subject=Project:%20Domain%20Email%20Offboarding)

## Project A - Stripe Clean
1. Export Stripe customer data as a backup and load into local store for development
2. Add meta-data to local store customer data
  1. cleanup-case
  2. cleanup-customer
3. Validate #2 had no errors
4. Run #2 against production environment
5. Modify Azure functions to injest email data entry as lowercase prior to saving in Stripe or Mailchimp
  1. [Donation Form](https://github.com/OWASP/owasp.github.io/blob/master/pages/donate.md)
  2. [Join Form](https://github.com/OWASP/owasp.github.io/blob/master/pages/membership.md)
  3. [Manage-membership Form](https://github.com/OWASP/owasp.github.io/blob/master/pages/manage-membership.md)
  4. Events Form - Harold we need link
  

## Project B - Email Hygiene
1. Export Google owasp.org email domain and load into local store for development
2. Using production leaders.json file and Stripe userdata, add meta-data to local store
  1. cleanup-disable
  2. cleanup-date
3. While processing data check for the following errors:
  1. leaders.json file should be date-stamped from yesterday
  2. validate connection to Google Groups
  3. validate connection to Stripe
3. Using Sendgrid send email to admin@owasp.com with the following:
  1. Subject: Daily Email Cleanup, x errors, y addresses disabled
  2. Body: leaders.json date yyyy-mm-dd [OK/Fail]
  3.       Connection to Google Groups  [OK/Fail]
  4.       Connection to Stripe         [OK/Fail]
  5.
  6.       Processing started yyyy-mm-dd hh:mm:ss and completed yyyy-mm-dd hh:mm:ss
  7.       Addresses Disable: y
  8.       Log File of Disabled Addresses:
  9.       email address 1
  10.      email address 2
4. Run in test mode for one week on local store



## Metadata schema
1. cleanup-case = "fix" or "okay"
  a. "Fix" records will have their email address convered to lowercase
2. cleanup-customer = "true" or "false"
  a. False records will be DELETED
3. cleanup-disable = "nonmember" or "nonleader" or "valid"
  a. Email is disabled if email not (in leaders.json OR in Stripe)
4. cleanup-date = date of metadata update in yyyy-mm-dd format


## Budget
Project rate of $2,500

