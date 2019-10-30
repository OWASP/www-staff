---

title: Milestones
layout: full-width

---

{% for project in site.data.projects %}
  {% capture milestones %}
    {% assign proj_milestones = (project.milestones | sort: 'milestone_date') | reverse %}
    {% for milestone in proj_milestones  %}
      {{ milestone.milestone_date }}|{{ milestone.description }}|{{ milestone.owner }}
      {% if forloop.last == false %}::{% endif %}
    {% endfor %}
  {% endcapture %}
{% endfor %}
{% assign milestone_array = milestones | split: '::' %}
{% for ms in milestone_array %}
   {% assign ms_vals = ms | split: '|' %}
   <div>{{ ms_vals[0] }}, {{ ms_vals[1] }}<h2>{{ ms_vals[2] </h2></div>
{% endfor %}
