---

title: Staff Projects
layout: full-width

---

<!-- rebuild 3 -->

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


## 2021 Operational Plans & Budget

- [2021 Operating Plan](/www-staff/operating-plan/)
- [2021 Budget - TBA]()

## 2020 Operational Plans & Budget

- [2020 Operating Plan](/www-staff/operating-plan/2020)
- [2020 Budget COVID-19 Response (Model Z)](/www-staff/budget/2020-modelz)
- [Original 2020 Budget](/www-staff/budget/2020)

## Active Projects

{% assign pages = site.pages | sort: 'title' | limit: 1000 %}
<ul>
{% for page in pages %}
 {% if page.path contains 'projects/' %}
 <li><a href='/www-staff{{ page.url }}'>{{ page.title }}</a>{% if page.date %}, {{ page.date }}{% endif %}</li>
 {% endif %}
{% endfor %}
</ul>

## Prioritized Projects

* 2021 Budget
* Board Strategy Meeting, including setting a new mission statement
* Finance Reform, including Grants, Awards and Scholarships
* Fundraising and grant seeking 

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

## Recently Completed Projects

{% assign pages = site.pages | sort: 'title' | limit: 1000 %}
<ul>
{% for page in pages %}
 {% if page.path contains 'projects-historical/' %}
 <li><a href='/www-staff{{ page.url }}'>{{ page.title }}</a></li>
 {% endif %}
{% endfor %}
</ul>

## Templates 
* [Blank Template](/www-staff/projects/202001-template)
