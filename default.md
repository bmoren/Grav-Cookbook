Get all sibling pages, get all of the pages that are next to this page, this is useful to create a menu of all pages, for example if this is a single project page under a 'projects' parent, this would give you a list of all of the projects: project 1, project 2, project 3, project 4...

```twig
<ul>
{% for p in page.parent.children %}
  <li>  {{ p.url }} </li>
{% endfor %}
</ul>
```

Display all tags associated with a page with a link to those tags.
```twig
{% for tag in page.taxonomy.tag %}
    <a href="search/tag:{{ tag }}">{{ tag }}</a>
{% endfor %}
```

Output the HTML tag to display all images associated with a page, useful to get all images onto the page which are uploaded to the media box at the bottom of the page editor in the admin panel.:  

```twig
 {% for image in page.media.images %}  
   {{ image.html }}  
{% endfor %}
```

get links to the sibling pages next to the current pages, useful for page to page navigation
```html
<a href="{{ page.parent().children().nextSibling(page.path).url }}"> next sibling </a>
<a href="{{ page.parent().children().prevSibling(page.path).url }}"> prev sibling </a>
  ```

get the very first sibling page in a set of sibling pages
```html
<a href="{{page.parent.children.nth(0).url}}"> First Sibling </a>
```

get the very last sibling page in a set of sibling pages
```html
<a href="{{page.parent.children.nth( page.parent.children.count()- 1 ).url}}">Last Sibling</a>
```

make a next button which moves to the next page loops around to the first page if it hits the end
```html
      {% if page.id() == page.parent().children.nth( page.parent().children.count() - 1 ).id() %} 

      {{page.parent().children.nth( 0 ).url}}

      {% else %}

      {{ page.parent().children().prevSibling(page.path).url }}

      {% endif %}
```



