---

title: Milestones
layout: full-width

---

<div class='milestones'>
<ul>
{% for milestone in site.data.milestones %}
    <li><div class='milestone_header'>{{ milestone.milestone_date }}: {{ milestone.project_name }}</div>
        <div class='milestone_project'>{{ milestone.description }}</div>
        <div>Owner: <i>{{ milestone.owner }}</i>
        </div>
    </li>
{% endfor %}
</ul>    
</div>
