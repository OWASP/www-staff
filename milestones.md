---

title: Milestones
layout: full-width

---

{% for project in site.data.projects %}
  {% capture milestones %}
    {% for milestone in project.milestones %}
      {{ milestone.milestone_date }}|{{ milestone.description }}|{{ milestone.owner }}
      {% if forloop.last == false %}::{% endif %}
    {% endfor %}
  {% endcapture %}
{% endfor %}
{% assign milestone_array = milestones | split: '::' %}
{% for ms in milestone_array %}
   {% assign ms_vals = ms | split: '|' %}
   {{ ms_vals[0] }}, {{ ms_vals[1] }} {{ ms_vals[2] }}
{% endfor %}
