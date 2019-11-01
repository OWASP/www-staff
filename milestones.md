---

title: Milestones
layout: full-width

---
{{ site.time }}

   {% assign owners_unique = site.data.milestones | map: 'owner' | join: ',' | split: ',' | uniq | sort %}

<div style='display:block;'>
<h2>Organizational View</h2>
<ul class='milestone_members'>
   {% for owner in owners_unique %}
    <li><a href="#{{ owner | replace: ' ', '-'}}">{{ owner }}</a></li>
   {% endfor %}
</ul>
</div>
<div class='milestones'>
<ul>
{% for milestone in site.data.milestones %}
    {% assign project = site.data.projects | where: 'name', milestone.project_name | first %}
   <li>{{ milestone.milestone_date }} - <a href='{{ project.url }}'>{{ milestone.project_name }}</a>, {{ milestone.description }}, [{{ milestone.owner }}]</li>
   {% endfor %}
</ul> 

{% for owner in owners_unique %}
<section id="{{ owner | replace: ' ', '-' }}">
<h2>{{ owner }}'s Milestones</h2>
<ul>
    {% for milestone in site.data.milestones %}
    {% assign project = site.data.projects | where: 'name', milestone.project_name | first %}
        {% if milestone.owner == owner %}
          <li>{{ milestone.milestone_date }} - <a href='{{ project.url }}'>{{ milestone.project_name }}</a>, {{ milestone.description }}, [{{ milestone.owner }}]
         </li>
        {% endif %}
    {% endfor %}
</ul>
</section>
{% endfor %}
</div>
