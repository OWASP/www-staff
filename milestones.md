---

title: Milestones
layout: full-width

---
<div class='milestones'>
<ul>
{% for milestone in site.data.milestones %}
    <li><strong>{{ milestone.project_name }}:{{ milestone.milestone_date }}</strong>{{ milestone.description }}<i>{{ milestone.owner }}</i></li>
{% endfor %}
</ul>    
</div>
