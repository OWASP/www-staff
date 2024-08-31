---

title: Getting a list of non-member leaders
layout: col-sidebar
permalink: /leader_list/

---

## Preparation

You'll need WSL or Linux, and dos2unix, git, and jq installed. You'll also need a copy of the OWASP website repo.

```bash
sudo apt install git jq dos2unix
git clone https://github.com/OWASP/owasp.github.io
```

## Obtain a full member list

Login to Stripe
Search for the following strings in the search bar, and export each of the results to a CSV file:

- [https://dashboard.stripe.com/search?query=metadata%3Amembership_type%3Done](https://dashboard.stripe.com/search?query=metadata%3Amembership_type%3Done)
- [https://dashboard.stripe.com/search?query=metadata%3Amembership_type%3Dtwo](https://dashboard.stripe.com/search?query=metadata%3Amembership_type%3Dtwo)
- [https://dashboard.stripe.com/search?query=metadata%3Amembership_type%3Dcomplimentary](https://dashboard.stripe.com/search?query=metadata%3Amembership_type%3Dcomplimentary)
- [https://dashboard.stripe.com/search?query=metadata%3Amembership_type%3Dlifetime](https://dashboard.stripe.com/search?query=metadata%3Amembership_type%3Dlifetime)

Import the CSV files into Excel. You want only the Email, Name, membership_end_date, and OWASP Email columns, the rest can be deleted. For One, Two, and Complimentary members, filter the membership_end_date to be after today's date. You can filter/hide/delete any rows that have a membership_end_date before today's date. Lifetime members will always be valid members, so they don't need to be filtered for end date.

Once you have the list of members, copy their primary and OWASP email addresses to a plain text file in WSL or Linux, called /tmp/members.txt

### De-dupe the membership list and sort it alphabetically

```bash
dos2unix /tmp/members.txt
cat /tmp/members.txt | tr '[:upper:]' '[:lower:]' | sort -u > /tmp/members2.txt
mv /tmp/members2.txt /tmp/members.txt
```

## Get the list of leaders, de-dupe and sort it

```bash
cd owasp.github.io/
git pull
cat _data/leaders.json | jq '.[] | .email ' > /tmp/leaders.txt
dos2unix /tmp/leaders.txt
cat /tmp/leaders.txt | tr '[:upper:]' '[:lower:]' | sort -u > /tmp/leaders2.txt
mv /tmp/leaders2.txt /tmp/leaders.txt
```

## Create a list of non-members

```bash
grep -vFf /tmp/members.txt /tmp/leaders.txt > /tmp/non-member-leaders.txt
```

## Find the non-email addresses

These MUST be fixed. Fix the relevant leaders.md file. You'll need to go back to the Excel CSV file to get the correct name. Look them up in Copper, Stripe, Linked In, X, or whatever, and get their email address.

```bash
grep -v "@" /tmp/non-member-leaders.txt
```

## Find the non-OWASP email addresses

These MUST be owasp.org emails. Fix the relevant leaders.md file. You'll need to go back to the Excel CSV file to get the correct name. Look them up in Stripe or Copper first, and then look to Linked In, X, or whatever, and get their email address.

```bash
grep -v "@owasp.org" /tmp/non-member-leaders.txt
```

## Update Leaders and the Board on the latest numbers

Open the [this sheet](https://docs.google.com/spreadsheets/d/1CbapOU2P_lp9S6mDX-9E9UfvViA99Qtd73YmiWzezVc/edit?usp=sharing) (you will need access, and it won't be granted unless you are a staff or board member) and update the numbers in the relevant cells, and copy and paste the graph on Slack to #board and #leaders.

```bash
wc /tmp/leaders.txt /tmp/non-member-leaders.txt
```

The first number is the total unique leaders. The second number is the total non-member leaders.

Remind leaders to become members by September 30th, 2024. With the Board, let them know what percentage of leaders are not members, and ask them to remind anyone they meet to become a member.

## Send a reminder to the non-member leaders

In Mailchimp, update the audience list with the contents /tmp/non-member-leaders.txt. Send them a reminder to join OWASP as a leader. You can re-use the previous email.

## Problems (and Solutions)

- Some leaders may be members, but their owasp.org email address is not in their Stripe record. Add it as owasp_email in metadata.
- Some leaders may be members, but they used a different email address to pay for it. Look up their Copper records, and add the owasp_email to their Stripe record.
- Some leaders may be members, but they have two Copper records, and these records don't match their Stripe record. Merge the Copper records, and add the owasp_email to their Stripe AND Copper records. Make sure the end date is accurate across both Copper and Stripe.

