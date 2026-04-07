---
layout: page
title: Openings
permalink: /projects/
description:
nav: true
nav_order: 3
# display_categories: [work, Life]
# display_categories: [Opening, Research]
display_categories: []
horizontal: false
---

### 🚀 **Join MIRoC Lab — PhD / RA / Intern Openings**

Our **Medical Intelligence and Robotic Cognition(MIRoC) Lab** is looking for
highly motivated students to join our team working on **intelligent medical robotics, robot learning, and multimodal AI for healthcare**.

We welcome applications for:<br>

- 🎓 PhD Students
- 👩‍💻 Research Assistants (RA)
- 🌱 Research Interns (Undergraduate / Master / Visiting or remote PhD Students)

---

#### 📬 **How to Apply**

Please send the following materials via email: <br>

- Transcript (optional)
- CV (with reserach/project experience)
- Short description of research interests

**Email subject**: MIRoC Application - Name - PhD/RA/Intern <br>
**Contact**: <a href="mailto:dianye.huang@hku.hk">dianye.huang@hku.hk</a> and/or <a href="mailto:zljiang@hku.hk">zljiang@hku.hk</a>

---

#### 🔬 **Research Topics**

Students will work on cutting-edge research including: <br>

- Medical Image Understanding & AI
- Robotic Ultrasound & Medical Robotics
- Multimodal Large Language Models for Healthcare
- Human-Robot Interaction in Clinical Environments
- Vision-Language-Action Models
- Autonomous Robot Scanning & Planning
- Learning from Demonstration for Robots

---

#### 🎓 **We Are Looking For**

Students with background in:<br>

- Robotics
- Computer Vision
- Medical Image Analysis
- Biomedical Engineering

Requirements:<br>

- Programming skills (Python / PyTorch preferred)
- Solid math and machine learning fundamentals
- Self-motivated and research-oriented
- Prior research experience is a plus (not required)
- Hands-on hardware experience is a plus plus (not required)

_Remote internship is possible for outstanding candidates_

---

#### 🎁 **What We Offer**

- Work on **real robotic medical systems**
- Opportunities to publish in **top-tier venues (RSS, ICRA, TRO, TMI, MICCAI, etc.)**
- Hands-on experience with **robot learning & medical AI**
- Collaboration with clinicians and hospitals
- Strong recommendation letters for PhD / academia
- Possibility to continue as **PhD student**

---

#### 🌍 **Who Should Apply**

You are encouraged to apply if you: <br>

- Are interested in **Robotics + AI + Healthcare**
- Plan to pursue a **PhD in robotics / AI**
- Want to work on impactful real-world research
- Enjoy both theory and system building

---

#### 📍 **Location**

MIRoC Lab, <br>
Depart. of Mech. Eng., <br>
The University of Hong Kong, <br>

Room G10, Haking Wong Building, <br>
Pokfulam Road, Hong Kong SAR, China

<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
