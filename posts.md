---
layout: page
title: "Schedule"
permalink: /schedule/
main_nav: true
---

{% for category in site.categories %}
  {% capture cat %}{{ category | first }}{% endcapture %}
  <h2 id="{{cat}}">{{ cat | capitalize }}</h2>
  {% for desc in site.descriptions %}
    {% if desc.cat == cat %}
      <p class="desc"><em>{{ desc.desc }}</em></p>
    {% endif %}
  {% endfor %}
  <ul class="posts-list">
  {% for post in site.categories[cat] %}
    <li>
      <strong>
        <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
      </strong>
      <span class="post-date">- {{ post.date | date_to_long_string }}</span>
      <span class="post-date">- {{ post.author }}</span>
    </li>
  {% endfor %}
  </ul>
  {% if forloop.last == false %}<hr>{% endif %}
{% endfor %}
<br>

<h2 class="post-link">Calendar</h2>	
<p dir="auto"> Add the seminar schedule to your <a href="https://calendar.google.com/calendar/embed?src=c_bd56c44a65b9dae27fe531b2b5c684a6c8fdf8a410edb595be2709bc16e55942%40group.calendar.google.com&ctz=America%2FSao_Paulo" rel="nofollow">Google Calendar</a> or <a href="https://calendar.google.com/calendar/ical/c_bd56c44a65b9dae27fe531b2b5c684a6c8fdf8a410edb595be2709bc16e55942%40group.calendar.google.com/public/basic.ics" rel="nofollow">iCal</a> application.
</p>	

<iframe src="https://calendar.google.com/calendar/embed?src=c_bd56c44a65b9dae27fe531b2b5c684a6c8fdf8a410edb595be2709bc16e55942%40group.calendar.google.com&ctz=America%2FSao_Paulo" style="border: 0" width="800" height="600" frameborder="0" scrolling="no"></iframe>

