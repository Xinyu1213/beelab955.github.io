---
layout: page
permalink: /Jobs/
title: Jobs
description: Edit the `_data/Jobs.yml` and change the `github_users` and `github_repos` lists to include your own GitHub profile and repositories.
nav: true
nav_order: 5
---

## GitHub users

{% if site.data.Jobs.github_users %}
<div class="Jobs d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for user in site.data.Jobs.github_users %}
    {% include repository/repo_user.html username=user %}
  {% endfor %}
</div>
{% endif %}

---

## GitHub Repositories

{% if site.data.Jobs.github_repos %}
<div class="Jobs d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for repo in site.data.Jobs.github_repos %}
    {% include repository/repo.html repository=repo %}
  {% endfor %}
</div>
{% endif %}
