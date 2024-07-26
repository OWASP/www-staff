---

title: Staff Information and Procedures
layout: col-sidebar

---

The OWASP Foundation is responsible for helping the community to enable the OWASP mission. Information pertaining to the current operating procedures, staff goals, and plans can be found below.

## Operational Policies

{% assign pages = site.pages | sort: 'title' | limit: 1000 %}
<ul>
{% for page in pages %}
 {% if page.path contains 'policies/' %}
 <li><a href="/www-staff{{ page.url | replace: '.html', '' }}">{{ page.title }}</a></li>
 {% endif %}
{% endfor %}
</ul>


<!-- rebuild 7 -->
## OWASP Foundation Workflow Procedures

{% assign pages = site.pages | sort: 'title' | limit: 1000 %}
<ul>
{% for page in pages %}
 {% if page.path contains 'procedures/' %}
 <li><a href="/www-staff{{ page.url | replace: '.html', '' }}">{{ page.title }}</a></li>
 {% endif %}
{% endfor %}
</ul>

## Strategies from the operating plan

- OWASP is run by the community, for the benefit of the community
- OWASP Foundation enables the mission, not does the mission
- All mission areas must be profitable in their own right, able to earn, and transparently and accountably spend approved funds
- Prioritize and focus on community and outreach activities that drive our mission

## 2024 Draft Operational Plan & Budget

- [2024 Operating Plan](operating-plan/2024/)
- [2024 Budget](budget/2024)

## Foundation Goals for 2024

- [ ] Continue adding Membership value and benefits; increasing student, individual, and lifetime memberships to 7000
- [ ] Three Global AppSecs
- [ ] Define and execute a comprehensive marketing and outreach program
- [ ] Define and execute a comprehensive community management plan
- [ ] Hire a Director of Community Development, responsible for fundraising, grant writing, and community outreach
