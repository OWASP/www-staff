---

title: Milestones
layout: full-width

---

{% assign owners_unique = site.data.milestones | map: 'owner' | join: ',' | split: ',' | strip | uniq | sort %}

<div class='milestones'>
<h2>Organizational View</h2>
<div>
<nav>
<ul>
   {% for owner in owners_unique %}
    <li><a href="#{{ owner | replace: ' ', '-'}}">{{ owner }}</a></li>
   {% endfor %}
</ul>
</nav>
</div>
<div class='milestones'>
<ul>
{% for milestone in site.data.milestones %}
    {% assign project = site.data.projects | where: 'name', milestone.project_name | first %}
   <li class='{{ milestone.status }}'>
        {{ milestone.milestone_date }}:&nbsp;&nbsp;<a href='{{ project.url }}'>{{ milestone.project_name }}</a>&nbsp;&nbsp;{{ milestone.description }}&nbsp;&nbsp;Owner: {{ milestone.owner }}
    </li>
{% endfor %}
</ul> 

{% for owner in owners_unique %}
<section id="{{ owner | replace: ' ', '-' }}">
<h2>{{ owner }}'s Milestones</h2>
<ul>
    {% for milestone in site.data.milestones %}
    {% assign project = site.data.projects | where: 'name', milestone.project_name | first %}
        {% if milestone.owner == owner %}
        <li class='{{ milestone.status }}'> {{ milestone.milestone_date }}:&nbsp;&nbsp;<a href='{{ project.url }}'>{{ milestone.project_name }}</a>&nbsp;&nbsp;
            {{ milestone.description }}&nbsp;&nbsp;
            Owner: {{ milestone.owner }}
        </li>
        {% endif %}
    {% endfor %}
</ul>
</section>
{% endfor %}
</div>
