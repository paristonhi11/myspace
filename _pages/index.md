---
layout: page
title: Home
id: home
permalink: /
---

{% assign root_folder = site.pages | where_exp: "page", "page.path contains 'notes/' and page.path | split: '/' | size == 2" %}
<ul>
  {% for page in root_folder %}
    <li>
      <span class="folder-toggle" onclick="toggleFolder(this)">&#9660;</span>
      <strong>{{ page.title }}</strong>
      <ul class="folder-content">
        {% assign folder_path = page.path | append: '/' %}
        {% for note in site.pages %}
          {% if note.path contains folder_path %}
            {% capture relative_path %}{{ note.path | remove: folder_path }}{% endcapture %}
            {% if relative_path contains '/' %}
              {% assign folder_name = relative_path | split: '/' | first %}
              <li>
                <span class="folder-toggle" onclick="toggleFolder(this)">&#9660;</span>
                <strong>{{ folder_name }}</strong>
                <ul class="folder-content">
                  {% for sub_note in site.pages %}
                    {% if sub_note.path contains folder_path %}
                      {% if sub_note.path contains folder_name %}
                        <li><a class="internal-link" href="{{ sub_note.url }}">{{ sub_note.title }}</a></li>
                      {% endif %}
                    {% endif %}
                  {% endfor %}
                </ul>
              </li>
            {% else %}
              <li><a class="internal-link" href="{{ note.url }}">{{ note.title }}</a></li>
            {% endif %}
          {% endif %}
        {% endfor %}
      </ul>
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
