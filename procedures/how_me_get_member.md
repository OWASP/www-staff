---

title: Getting a Current Member List
layout: col-sidebar
permalink: /member_list/
tags: Charlie-Gordon, Algernon

---
v2021.10.25 

Often it is desirable to get the current list of members. The first and most accurate method involves Stripe. It is more accurate because it is much more automated and most people have a harder time altering the data there. The second is our CRM, Copper. As we have a CRM and that CRM can be used to pull a member list, this then represents the gross steps required to get a full list. 

### Stripe Method
1. Log into [Stripe](https://stripe.com/).
2. Gather the [One Year Members](https://dashboard.stripe.com/search?query=metadata%3Amembership_type%3Done).
3. Export this to Excel, selecting Custom columns and only Email and Name.
4. Gather the [Two Year Members](https://dashboard.stripe.com/search?query=metadata%3Amembership_type%3Dtwo).
5. Export this to Excel, selecting Custom columns and only Email and Name.
6. Gather the [Complimentary Members](https://dashboard.stripe.com/search?query=metadata%3Amembership_type%3Dcomplimentary).
7. Export this to Excel, selecting Custom columns and only Email and Name.
8. Gather the [Lifetime Members](https://dashboard.stripe.com/search?query=metadata%3Amembership_type%3Dlifetime).
9. Export this to Excel, selecting Custom columns and only Email and Name.
10. Open a new Google Sheet or Excel Sheet and call it something useful (year_month_date_membership for instance).
12. Paste the contents of each of the 4 customer excel files into this new sheet, making sure not to copy the headers more than once.
13. Sort the sheet by membership-end date and eliminate all the memberships that are expired (empty = lifetime most of the time).
14. You now have the Stripe list of current members and as money=membership (complimentary aside), this list is the most accurate.

### Copper Method
#### Get a List of Non-Lifetime Members

1. Log into [Copper](https://copper.com/).
2. On the left hand side, click People.
3. Click the Filters drop-down (looks like an upside down pyramid).
4. Make sure you Clear All to clear all current filters.
5. Go down to Membership End and click it. It should produce a pop-up with dates in it.
6. Make sure Fixed Dates is selected.
7. In the From: side of things choose today's date.
8. Leave the To: side of things blank. It will have a date in it that LOOKS like today's date but it is grayed out meaning that it is technically empty.
9. Click Apply.
10. Select All (checkbox at the top left).
11. Click the three dots next to the pencil.
12. Click Export List. This will produce an Excel document.

#### Get a List of Lifetime Members

1. Log into [Copper](https://copper.com/).
2. On the left hand side, click People.
3. Click the Filters drop-down.
4. Make sure you Clear All to clear all current filters.
5. Click Membership Type.
6. Scroll down and select Lifetime
7. Select All (checkbox at the top left).
8. Click the three dots next to the pencil.
9. Click Export List. This will produce an Excel document.

#### Combine the Lists

Use whatever program you like (Google Sheets, Excel, etc) to combine the two lists you just generated.

#### 
