---

title: Milestones
layout: full-width

---

{% for project in site.data.projects %}
  {% capture milestones %}
    {% for milestone in project.milestones %}
      {{ milestone.milestone_date }}|{{ milestone.description }}|{{ milestone.owner }}
      {% if not forloop.last %}::{% endfor %}
    {% endfor %}
  {% endcapture %}
{% endfor %}
{% assign milestone_array = milestones | split: '::' %}
{% for milestone in milestone_array %}
{{ milestone[0] }}, {{ milestone[1] }} [{{ milestone[2] }}]
{% endfor %}
