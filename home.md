 get all children pages in a unordered list. This is useful to get create a menu of all of the children pages under a parent page. For example on a 'Projects' page, this would give you: project 1, project 2, project 3, project 4...
```twig
<ul>
{% for p in page.children %}
  <li><a href="{{p.url}}">{{ p.title }}</a> </li>
{% endfor %}
</ul>
```

Output the first image which was uploaded to each children page. This is useful for a tile index of all child pages. Think pinterest or a tile style portfolio site. It will get the image and title of the children page and create a link to the child page from the image and title.
```twig
{% for p in page.children %}
{% set first_image = p.media.images|first %}
<div class="project_item">
  <a href="{{p.url}}"> {{ first_image.html }} </a>
  <a href="{{p.url}}">{{ p.title }}</a>
</div>
{% endfor %}
```








