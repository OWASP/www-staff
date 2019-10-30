---

title: Milestones
layout: full-width

---

{% for project in site.data.projects %}
  {% capture milestones %}
    {% for milestone in project.milestones %}
      {{ milestone }}
    {% endfor %}
  {% endcapture %}
  <a href='{{ project.url }}'>{{ project.name }}</a>
{% endfor %}
