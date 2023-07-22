---
layout: page
title: Home
id: home
permalink: /
---

{% assign recent_notes = site.notes | sort: "last_modified_at_timestamp" | reverse %}
<ul>
  {% for note in recent_notes %}
    <li>
      {% if note.path contains '/folder' %}
        <strong>Folder: {{ note.relative_path }}</strong>
      {% endif %}
      <a class="internal-link" href="{{ note.url }}">{{ note.title }}</a>
    </li>
  {% endfor %}
</ul>


# Welcome! It's Telar Karan

## Senior Analyst | Full-Stack Developer

Welcome to my personal Space! I am Telar Karan, a Senior Analyst at Capgemini with a strong focus on full-stack development. My expertise includes front-end technologies like HTML, CSS, JavaScript, as well as frameworks such as React and Angular. Additionally, I have extensive experience in back-end development using Spring Boot. I am passionate about creating seamless and user-friendly experiences that leverage the power of both front-end and back-end technologies.

### Contact Information

- Email: telarkaran@outlook.com

### Education

- Bachelor of Technology (B.Tech) in Electrical Engineering
- Sardar Vallabhbhai National Institute of Technology (SVNIT), Surat

### Professional Experience

- Senior Analyst at Capgemini

### Skills

- Full-Stack Development
- Front-End: HTML, CSS, JavaScript, React, Angular
- Back-End: Spring Boot

### Projects

- Project 1: [Task Manager Application](https://taskmanager-poc.vercel.app/)
- Project 2: [Budget Application](https://telarkaran-budget-app.netlify.app/)

### Interests

- Web Development
- Open-Source Contributions

<strong>Recent uploads</strong>

<ul>
  {% assign recent_notes = site.notes | sort: "last_modified_at_timestamp" | reverse %}
  {% for note in recent_notes limit: 5 %}
    <li>
      <a class="internal-link" href="{{ note.url }}">{{ note.title }}</a>
    </li>
  {% endfor %}
</ul>

<style>
  .wrapper {
    max-width: 46em;
  }
</style>
