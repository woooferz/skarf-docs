Configuring Skarf
=================

You can configure skarf with YAML and JSON. To configure skarf (in
docker) you’ll need to mount ``/app/config`` to a local directory, and
then you can put a ``config.json`` or ``config.yml`` into that folder.
You can see examples of configs on this page, and further down there is
a section which tells you what everything means.

Examples
--------

Example YAML (``config.yml``)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: yaml

  version: 3 # pls no touch this
  debug: false
  settings:
    name: "Person" # Main name
    subtitle: "Some for info" # A little text below namwe
    font: Roboto, Arial # The font-family to use for the page
    color: "#6F6F6F" # The color of the name and subtitle
    link-color: "#F6F6F6" # The color of the text on the links
    glass-card: true # If the image, name, subtitle and links should be displayed on a glass-like card
    custom-css: false # OPTIONAL! url to custom css
    font-awesome:
      pro: false # if you have pro set to true
      pro-url: "/idk/here/maybe" # if you have pro enter url here, either a local one such as /static/fontawesome-pro.css or an external one such as https://fontawesome.example.com/pro.css (BOTH OF THESE WON'T WORK, GET YOUR OWN LINK)
    glass:
      color: "#FFFFFFAA" # color of the glass effect simply remove this if you enjoy the current color
    background: # The background info
      type: color # image or color or gradient Decides what to put as the background
      content: "#2F2F2F" # url to image or a color code (e.g. /static/bg.png) or the first color of a gradient
      content-2: "#FFFFFF" # only used when there is a gradient, the second color of gradient
    favicon: /static/favicon.png # If you want a favicon
    description: Some info in the meta description tag # If you want a meta description
    image:
      type: font-awesome # image or font-awesome decides how to display avatar
      style: solid # for font-awesome. Decides what style to display the icon
      content: user # font-awesome icon name, or url to image
    links:
      - name: Skarf Docs # Frienly Name of link
        link: https://skarf-docs.readthedocs.io/en/latest/index.html # The link to the link
        image: # same as the 'image' item above
          type: font-awesome
          style: solid
          content: book
        color: "#3F3F3F" # the background color of the link
      - name: Skarf Github # same as item above
        link: https://github.com/woooferz/skarf
        image:
          type: font-awesome
          style: brands
          content: github
        color: "#3F3F3F"
      - name: Support Discord
        link: https://discord.gg/VnskbWb4Ft
        image:
          type: font-awesome
          style: brands
          content: discord
        color: "#454FBF"
    mini-links: # different from 'links' as it is only an image/icon with a link. AKA no text.
      - link: https://github.com/woooferz/skarf # Link to the service
        image: # same as the 'image' item above
          type: font-awesome
          style: brands
          content: github
        color: "#3F3F3F" # color of it



Example JSON (``config.json``)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: json

  {
    "version": 3,
    "debug": false,
    "settings": {
      "name": "Person",
      "subtitle": "Some for info",
      "font": "Roboto, Arial",
      "color": "#6F6F6F",
      "link-color": "#F6F6F6",
      "glass-card": true,
      "custom-css": false,
      "font-awesome": {
        "pro": false,
        "pro-url": "/idk/here/maybe"
      },
      "glass": {
        "color": "#FFFFFFAA"
      },
      "background": {
        "type": "color",
        "content": "#2F2F2F",
        "content-2": "#FFFFFF"
      },
      "favicon": "/static/favicon.png",
      "description": "Some info in the meta description tag",
      "image": {
        "type": "font-awesome",
        "style": "solid",
        "content": "user"
      },
      "links": [
        {
          "name": "Skarf Docs",
          "link": "https://skarf-docs.readthedocs.io/en/latest/index.html",
          "image": {
            "type": "font-awesome",
            "style": "solid",
            "content": "book"
          },
          "color": "#3F3F3F"
        },
        {
          "name": "Skarf Github",
          "link": "https://github.com/woooferz/skarf",
          "image": {
            "type": "font-awesome",
            "style": "brands",
            "content": "github"
          },
          "color": "#3F3F3F"
        },
        {
          "name": "Support Discord",
          "link": "https://discord.gg/VnskbWb4Ft",
          "image": {
            "type": "font-awesome",
            "style": "brands",
            "content": "discord"
          },
          "color": "#454FBF"
        }
      ],
      "mini-links": [
        {
          "link": "https://github.com/woooferz/skarf",
          "image": {
            "type": "font-awesome",
            "style": "brands",
            "content": "github"
          },
          "color": "#3F3F3F"
        }
      ]
    }
  }

What everything means
---------------------

``version`` Version of renderer to load config with.

``debug`` If debug mode is on which reloads config on every load and shows some version info on page

``settings.name`` The title of the card, usually your name/nickname.

``settings.subtitle`` Text beneath ``settings.name`` with a smaller font
size.

``settings.font`` Font of the card, needs to be installed on the viewers
device.

``settings.color`` Text colour of ``settings.name`` and
``settings.subtitle``.

``settings.link-color`` Text colour of all the links.

``settings.glass-card`` If the card should have a glass effect. (From
`css.glass`_)

``settings.background.type`` Either color or image. Decides the type of
background your card will have.

``settings.background.content`` If ``settings.background.type`` is color
then use a hex color code, if it is image then use a image url.

``settings.favicon`` Path to a favicon.

``settings.description`` Meta description for your card.

``settings.image.type`` Either font-awesome or image. Decides the type
of avatar you will have.

``settings.image.style`` Only useful if you are using font-awesome for
``settings.image.type``, it will decide what style of icon you will
have. It can be solid or brand, assuming you have the free tier of font
awesome

``settings.image.content`` If ``settings.image.type`` is font-awesome it
is an icon name. If it is ``image`` then an image url.

``settings.links`` An array/list of links.

``settings.links.name`` The display text of a link.

``settings.links.link`` The link of a link.

``settings.links.image`` Same as ``settings.image``.

``settings.links.color`` The background colour of a link.

.. _css.glass: https://css.glass