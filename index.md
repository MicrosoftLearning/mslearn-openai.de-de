---
title: Übungen zu Azure OpenAI
permalink: index.html
layout: home
---

# Übungen zu Azure OpenAI

Die folgenden Übungen sind eine Ergänzung für die Module in [Microsoft Learn](https://learn.microsoft.com/training/browse/?terms=OpenAI).


{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions/Exercises'" %} {% for activity in labs  %}
- [{{ activity.lab.title }}]({{ site.github.url }}{{ activity.url }}) {% endfor %}
