---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

Like most things in my life, this site is a work in progress. I plan to discuss projects that I picked up in my personal time which I thought were cool or introduced me to some cool technology and blog about random tech or tech adjacent things.

I also am a fan of Sudoku and plan to start making content on work I have done in that space as well, so stay tuned if you're into that!

# Recent Projects

{% assign sorted-posts = site.projects | sort: 'date' | reverse %}
{% for project in sorted-posts limit: 2 %}
  <h2>
    <a href="{{ project.url }}">
      {{ project.name }}
    </a>
  </h2>
  <p>{{ project.excerpt | markdownify }}</p>
{% endfor %}
