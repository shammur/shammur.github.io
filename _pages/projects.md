---
layout: page
title: Projects
permalink: /projects/
description: Current and past research projects.
nav: true
nav_order: 3
display_categories: [Funded_Projects, QCRI_Projects, Past_Projects]
---

<div class="projects-page">
  <p class="projects-intro">
    A selected record of funded research programs, QCRI research initiatives, platforms, and earlier collaborative projects.
  </p>

  {% for category in page.display_categories %}
    {% assign categorized_projects = site.projects | where: "category", category %}
    {% assign sorted_projects = categorized_projects | sort: "importance" %}
    {% if sorted_projects.size > 0 %}
      <section class="project-group" id="{{ category }}">
        <h2>
          {% case category %}
            {% when "Funded_Projects" %}Funded Projects
            {% when "QCRI_Projects" %}QCRI Projects
            {% when "Past_Projects" %}Past Projects
            {% else %}{{ category | replace: "_", " " }}
          {% endcase %}
        </h2>

        <div class="project-list">
          {% for project in sorted_projects %}
            {% if project.redirect %}
              {% assign project_href = project.redirect %}
            {% else %}
              {% assign project_href = project.url | relative_url %}
            {% endif %}
            <article class="project-row">
              <a class="project-row__media" href="{{ project_href }}" {% if project.redirect %}target="_blank" rel="noopener"{% endif %} aria-label="{{ project.title }}">
                {% if project.img %}
                  <img src="{{ project.img | relative_url }}" alt="{{ project.title }} logo">
                {% else %}
                  <span class="project-row__placeholder">{{ project.title | slice: 0, 2 }}</span>
                {% endif %}
              </a>
              <div class="project-row__body">
                <div class="project-row__meta">
                  <span>
                    {% case project.category %}
                      {% when "Funded_Projects" %}Funded Project
                      {% when "QCRI_Projects" %}QCRI Project
                      {% when "Past_Projects" %}Past Project
                      {% else %}{{ project.category | replace: "_", " " }}
                    {% endcase %}
                  </span>
                </div>
                <h3>
                  <a href="{{ project_href }}" {% if project.redirect %}target="_blank" rel="noopener"{% endif %}>{{ project.title }}</a>
                </h3>
                <p>{{ project.description }}</p>
              </div>
            </article>
          {% endfor %}
        </div>
      </section>
    {% endif %}
  {% endfor %}
</div>
