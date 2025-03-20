---
layout: page
title: Blog Archive
---

<style>
  body {
    font-family: Arial, sans-serif;
    background-color: #f9f9f9;
    color: #333;
  }

  h3 {
    font-size: 2rem;
    color: #2c3e50;
    margin-bottom: 10px;
  }

  .tag-container {
    background-color: #ffffff;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    margin-bottom: 30px;
    padding: 20px;
  }

  .tag-container h3 {
    margin-top: 0;
  }

  .post-list {
    list-style-type: none;
    padding: 0;
  }

  .post-list li {
    margin-bottom: 15px;
    background-color: #ecf0f1;
    border-radius: 8px;
    padding: 15px;
    transition: background-color 0.3s ease;
  }

  .post-list li:hover {
    background-color: #bdc3c7;
  }

  .post-list a {
    text-decoration: none;
    color: #3498db;
    font-weight: bold;
  }

  .post-list a:hover {
    text-decoration: underline;
  }

  .post-date {
    font-size: 0.9rem;
    color: #7f8c8d;
  }

  .post-title {
    font-size: 1.2rem;
  }
</style>

<div class="archive-container">
  {% for tag in site.tags %}
    <div class="tag-container">
      <h3>{{ tag[0] }}</h3>
      <ul class="post-list">
        {% for post in tag[1] %}
          <li>
            <span class="post-date">{{ post.date | date: "%B %Y" }}</span>
            <br>
            <a href="{{ post.url }}" class="post-title">{{ post.title }}</a>
          </li>
        {% endfor %}
      </ul>
    </div>
  {% endfor %}
</div>
