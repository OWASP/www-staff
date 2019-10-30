---

title: Milestones
layout: full-width

---
<div class='milestones'>
<ul>
{% for milestone in site.data.milestones %}
    <li><div>{{ milestone.milestone_date }}:{{ milestone.project_name }}</div>
        <div>{{ milestone.description }}</div>
        <div>Owner: <i>{{ milestone.owner }}</i>
        </div>
    </li>
{% endfor %}
</ul>    
</div>
