---

title: Staff Information and Procedures
layout: col-sidebar

---

The OWASP Foundation Staff are responsible for helping the community to enable the OWASP mission. Information pertaining to the current operating procedures, staff goals, and plans can be found below.

<!-- rebuild 6 -->
## Staff Workflow Procedures (in development)
{% assign pages = site.pages | sort: 'title' | limit: 1000 %}
<ul>
{% for page in pages %}
 {% if page.path contains 'procedures/' %}
 <li><a href="/www-staff{{ page.url | replace: '.html', '' }}">{{ page.title }}</a></li>
 {% endif %}
{% endfor %}
</ul>

## 2021 Operational Plans & Budget

- [2021 Operating Plan](/www-staff/operating-plan/info)
- [2021 Budget - TBA]()

## 2020 Operational Plans & Budget

- [2020 Operating Plan](/www-staff/operating-plan/2020)
- [2020 Budget COVID-19 Response (Model Z)](/www-staff/budget/2020-modelz)
- [Original 2020 Budget](/www-staff/budget/2020)

## Strategies from the operating plan

* Run by the community, for the community
* OWASP Foundation enables the mission, not does it
* All chapters, projects, committees, and all mission areas should be their own profit and loss, able to earn and spend funds on mission in an accountable way
* Developers and Testers must be a key target for all mission activities 
* Automation of all BAU, or if automation is not possible, single touch processes that are fair, community supported, and repeatable outcomes

## Foundation Goals for 2021

1. Emerge from 2021 a stronger, more cohesive community, with increased chapter and project activity, with more member benefits
2. Ensure we raise sufficient funds to put on two Global AppSecs in 2022
3. Increase student, individual, and lifetime memberships to 4000
4. Recruit active leaders to all inactive chapters, and increase chapter activity by 25% over 2020 levels
5. Simplify and minimize administrative costs and overheads

*Vision: TBA after Board strategy meeting*
