---
layout: default
title: Home
---

<div class="home">
  <h1>Welcome to the Ansible Project Blog</h1>
  <p>This blog documents the development and usage of my Ansible project.</p>

  <h2>Latest Posts</h2>
  <ul>
    {% for post in site.posts limit:5 %}
      <li>
        <a href="{{ post.url }}">{{ post.title }}</a> - {{ post.date | date: "%b %d, %Y" }}
      </li>
    {% endfor %}
  </ul>

  <h2>Documentation</h2>
  <p>Check out the <a href="/documentation">documentation</a> to get started with the project.</p>

  <h2>Tutorials</h2>
  <p>Explore our <a href="/tutorials">tutorials</a> for step-by-step guides.</p>
</div>
