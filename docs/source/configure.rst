.. toctree::
   :maxdepth: 2

   index
   installation
   configure

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

   version: 2 
   settings:
     name: 'Person' 
     subtitle: 'Some for info' 
     font: Roboto, Arial 
     color: '#6F6F6F' 
     link-color: '#F6F6F6' 
     glass-card: true 
     background:
       type: color
       content: '#2F2F2F' 
     favicon: /static/favicon.png 
     description: Some info in the meta description tag 
     image:
       type: font-awesome 
       style: solid 
       content: user
     links:
       - name: Google 
         link: https://google.com 
         image: 
           type: font-awesome
           style: brands
           content: google
         color: '#454FBF'
       - name: Skarf Github
         link: https://github.com/woooferz/skarf
         image:
           type: font-awesome
           style: brands
           content: github
         color: '#3F3F3F'

Example JSON (``config.json``)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: json

   {
     "version": 2,
     "settings": {
       "name": "Person",
       "subtitle": "Some for info",
       "font": "Roboto, Arial",
       "color": "#6F6F6F",
       "link-color": "#F6F6F6",
       "glass-card": true,
       "background": {
         "type": "color",
         "content": "#2F2F2F"
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
           "name": "Google",
           "link": "https://google.com",
           "image": {
             "type": "font-awesome",
             "style": "brands",
             "content": "google"
           },
           "color": "#454FBF"
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
         }
       ]
     }
   }

What everything means
---------------------

``version`` Version of skarf to load config with.

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