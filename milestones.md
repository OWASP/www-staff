---

title: Milestones
layout: full-width

---

{% assign owners_unique = site.data.milestones | map: 'owner' | join: ',' | split: ',' | uniq | sort %}

<div>
<h2>Milestones By Member</h2>
<ul>
   {% for owner in owners_unique %}
    <li><a href="#{{ owner | replace: ' ', '-'}}">{{ owner }}</a></li>
   {% endfor %}
</ul>
</div>


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

{% for owner in owners_unique %}
<section id="{{ owner | replace: ' ', '-' }}">
<h2>{{ owner }}'s Milestones</h2>
<ul>
    {% for milestone in site.data.milestones %}
        {% if milestone.owner == owner %}
        <li><div class='milestone_header'>{{ milestone.milestone_date }}: {{ milestone.project_name }}</div>
            <div class='milestone_project'>{{ milestone.description }}</div>
            <div>Owner: <i>{{ milestone.owner }}</i>
            </div>
        </li>
        {% endif %}
    {% endfor %}
</ul>
</section>
{% endfor %}
</div>
