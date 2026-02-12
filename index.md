---

title: Staff Information and Procedures
layout: col-sidebar

---

The OWASP Foundation is responsible for helping the community to enable the OWASP mission. Information pertaining to the current operating procedures, staff goals, and plans can be found below.

## Operational Policies

{% assign pages = site.pages | sort: 'title' | limit: 1000 %}
<ul>
{% for page in pages %}
 {% if page.path contains 'policy/' %}
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

This page is being retired in the new website.
