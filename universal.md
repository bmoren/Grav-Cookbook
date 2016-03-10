# There are several core variables which can be used in most pages. This is the best place to start.

## Relative or Absolute URL structure

The URL structure can be defined in the admin panel under the configuration tab > system tab > Hide home route in URLs ![abs rel urls](imgs/absrelurl.png)

If you choose YES to hide the home route in urls use the base_url_absolute variable<br> If you chose NO use the base  else use the base_url_relative variable

### base_url_relative variable

The `{{ base_url_relative }}` returns the base URL to the Grav site, without the host information.

### base_url_absolute variable

`{{ base_url_absolute }}` returns the universal root URL, this is very useful for making a link which always returns to the home page or for building dynamic links.

## theme_url variable

- The `{{ theme_url }}` returns the relative URL to your theme directory.
- Common uses: linking style sheets, or external image files which will never be changed by the content editor, this gives you access to the directory which contains all of your template files, the 'root' directory of your template.

  1. Example: `<link rel="stylesheet" href="{{ theme_url }}/css/default.css" media="screen" title="no title" charset="utf-8">`
  2. Example: `<img src="{{ theme_url }}/images/sitelogo.png">`

## page

`{{ page.content }}` returns the entire HTML content of your page. In the admin panel, this is anything contained in the primary markdown compatible text box for each page.

`{{ page.summary(50) }}` Get a short summary of the {{page.content}}, use the number in the parenthesis to specify how many characters you wish to provide.

`{{ page.title }}` returns the title of your page. This is associated with the 'title' text box in the admin panel

`{{ page.author }}` returns the author of your page. This is associated with the 'author' text box in the admin panel accessible in the configuration tab under the 'site' sub tab.

`{{ page.date }}` returns the date this page was last modified
