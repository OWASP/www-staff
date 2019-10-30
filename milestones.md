---

title: Milestones
layout: full-width

---
<div class='milestones'>
{% capture milestones %}
{% for project in site.data.projects %}
    {% if forloop.last == true %}
    {% assign append_dots = true %}
    {% else %}
    {% assign append_dots = false %}
    {% endif %}
    {% assign proj_milestones = (project.milestones | sort: 'milestone_date') | reverse %}
    {% for milestone in proj_milestones  %}
      {{ milestone.milestone_date }}|{{ milestone.description }}|{{ milestone.owner }}
      ::
    {% endfor %}
{% endfor %}
{% endcapture %}
{% assign milestone_array = ((milestones | split: '::') | sort) | reverse %}
<ul>
{% for ms in milestone_array %}
   {% assign ms_vals = ms | split: '|' %}
   {% if ms_vals[0] %}
    <li><strong>{{ ms_vals[0] }}</strong>, {{ ms_vals[1] }}<i>{{ ms_vals[2] }}</i></li>
   {% endif %}
{% endfor %}
</ul>
</div>
