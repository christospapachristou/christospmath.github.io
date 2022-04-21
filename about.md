---
title: About me
subtitle: Who am I?
layout: default
date: 2022-03-02
keywords: writing
published: true
---
My name is Christos
{% for file in static_files %}
  {%if file.image %}
    <img class="" src="{{file.path}}" alt="{file.name}" />
  {% endif %}
{% endfor %}