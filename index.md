---
layout: home
---

<div class="month-filter">
  <label for="month-select">依年月查看：</label>
  <select id="month-select" onchange="location = this.value;">
    <option value="">選擇年月</option>

    {% assign dates = site.posts | group_by_exp: "post", "post.date | date: '%Y-%m'" %}

    {% for group in dates %}
      <option value="{{ '/archive/' | relative_url }}#{{ group.name }}">
        {{ group.name }}
      </option>
    {% endfor %}
  </select>
</div>
