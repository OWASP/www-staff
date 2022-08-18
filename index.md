---

title: Staff Information and Procedures
layout: col-sidebar

---

The OWASP Foundation Staff are responsible for helping the community to enable the OWASP mission. Information pertaining to the current operating procedures, staff goals, and plans can be found below.

<!-- rebuild 6 -->
## Staff Workflow Procedures

{% assign pages = site.pages | sort: 'title' | limit: 1000 %}
<ul>
{% for page in pages %}
 {% if page.path contains 'procedures/' %}
 <li><a href="/www-staff{{ page.url | replace: '.html', '' }}">{{ page.title }}</a></li>
 {% endif %}
{% endfor %}
</ul>

## 2022 Draft Operational Plan & Budget

- [2022 Operating Plan](operating-plan/2022/)
- [2022 Budget](budget/2022)

## 2021 Operational Plans & Budget

- [2021 Operating Plan](operating-plan/2021/intro-2021)
- [2021 Budget](budget/2021)

## 2020 Operational Plans & Budget

- [2020 Operating Plan](operating-plan/2020/2020)
- [2020 Budget COVID-19 Response (Model Z)](/www-staff/budget/2020-modelz)
- [Original 2020 Budget](/www-staff/budget/2020)

## Strategies from the operating plan

- Run by the community, for the community
- OWASP Foundation enables the mission, not does the mission
- All mission areas (chapters, membership, projects, events, etc) must be profitable in their own right, able to earn and spend funds on mission in an accountable way
- Prioritize and focus on community and outreach activities that drive our mission, deprioritizing costly or stopping unnecessary activities

## Foundation Goals for 2022

- [ ] Continue adding Membership value and benefits; increasing student, individual, and lifetime memberships to 7000
- [ ] Run at least two Global AppSecs in 2022, including San Francisco
- [ ] Help drive project, event, membership, and outreach goals by implementing OWASP's first marketing plan
- [ ] Complete a comprehensive customer experience (CX) improvement program
- [ ] Evaluate and replace our Association Management System with a cloud based system, preferably able to handle chapters and events to dramatically reduce costs

## Foundation Goals for 2021

- [x] Emerge from 2021 a stronger, more cohesive community, with increased chapter and project activity, with more member benefits. *We made a small profit in 2021, up from a projected loss*
- [x] Ensure we raise sufficient funds to put on two Global AppSecs in 2022. *We have sufficient funds to put on AppSec Global San Francisco*
- [x] Increase student, individual, and lifetime memberships to 4000. *We blew past our membership goal, ending the year with 5486 financial members*
- [x] Recruit active leaders to all inactive chapters, and increase chapter activity by 25% over 2020 levels. *We completed a chapter reactivation program, one of the busiest years for RSVPs ever*
- [x] Simplify and minimize administrative costs and overheads. *We were able to reduce our overheads by more than 70% compared to 2019*
