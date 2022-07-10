# Configuring Skarf

You can configure skarf with YAML and JSON. To configure skarf (in
docker) you'll need to mount `/app/config` to a local directory, and
then you can put a `config.json` or `config.yml` into that folder. You
can see examples of configs on this page, and further down there is a
section which tells you what everything means.

## Examples

### Example YAML (`config.yml`)

``` yaml
version: 6 # pls no touch this
debug: false
settings:
  name: "Person" # Main name
  subtitle: "Some for info" # A little text below namwe
  font: Roboto, Arial # The font-family to use for the page
  verified: false # adds a cool checkmark
  check-color: '#55FF11' # decides the color of checkmark
  color: "#6F6F6F" # The color of the name and subtitle
  button-border-radius: '15'
  link-color: "#F6F6F6" # The color of the text on the links
  card:
    border-radius: '15'
    glass: 
      status: true
      color: "#FFFFFFAA"
    solid:
      status: false
      color: "#FFFFFF"
  custom-css: false # OPTIONAL! url to custom css
  kofi:
    status: false # kofi on / off status
    slug: supportkofi # if your kofi was https://ko-fi.com/supportkofi then you would put 'wooferz'
    text: Support Ko-Fi # the text on the button (Keep under 13 characters as it will add a scroll bar otherwise)
    background-color: '#00b9fe' # background color of button
    text-color: '#ffffff' # text color of button
  font-awesome:
    pro: false # if you have pro set to true
    pro-url: "/idk/here/maybe" # if you have pro enter url here, either a local one such as /static/fontawesome-pro.css or an external one such as https://fontawesome.example.com/pro.css (BOTH OF THESE WON'T WORK, GET YOUR OWN LINK)
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
  share: true
  share-color: '#3F3F3F'
  links:
    - name: Skarf Docs # Frienly Name of link
      link: https://skarf-docs.readthedocs.io/en/latest/index.html # The link to the link
      image: # same as the 'image' item above
        type: font-awesome
        style: solid
        content: book
      color: '#3F3F3F' # the background color of the link
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
```

### Example JSON (`config.json`)

``` json
{
  "version": 6,
  "debug": false,
  "settings": {
    "name": "Person",
    "subtitle": "Some for info",
    "font": "Roboto, Arial",
    "verified": false,
    "check-color": "#55FF11",
    "color": "#6F6F6F",
    "button-border-radius": "15",
    "link-color": "#F6F6F6",
    "card": {
      "border-radius": "15",
      "glass": {
        "status": true,
        "color": "#FFFFFFAA"
      },
      "solid": {
        "status": false,
        "color": "#FFFFFF"
      }
    },
    "custom-css": false,
    "kofi": {
      "status": false,
      "slug": "supportkofi",
      "text": "Support Ko-Fi",
      "background-color": "#00b9fe",
      "text-color": "#ffffff"
    },
    "font-awesome": {
      "pro": false,
      "pro-url": "/idk/here/maybe"
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
    "share": true,
    "share-color": "#3F3F3F",
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
```

## What everything means

`version` Version of renderer to load config with.

`debug` If debug mode is on which reloads config on every load and shows
some version info on page

`settings.name` The title of the card, usually your name/nickname.

`settings.subtitle` Text beneath `settings.name` with a smaller font
size.

`settings.font` Font of the card, needs to be installed on the viewers
device.

`settings.verified` Verification status, if set to true it adds a cool little checkmark

`settings.check-color` Decides the color of the checkmark if `settings.verified` is set to true, if not set it will be the color of `settings.color`

`settings.color` Text color of `settings.name` and `settings.subtitle`.

`settings.button-border-radius` The border radius of all the buttons

`settings.link-color` Text color of all the links.

`settings.card` All the configuration for the card design

`settings.card.border-radius` The border radius of the card

`settings.card.glass.status` If the card should have a glass effect. (From [css.glass](https://css.glass))

`settings.card.glass.color` Color of glass effect if it is enabled

`settings.card.solid.status` If the card should have a solid color background. Only can be enabled if `settings.card.glass.status` is set to false

`settings.card.solid.color` Color of solid background

`settings.share` Status of share button

`settings.share-color` Color of share button if enabled

`settings.custom-css` A link to custom css

`settings.kofi.status` true/false if you want to enable Ko-Fi Integration.

`settings.kofi.slug` Your kofi link, but only the last bit (e.g. supportkofi)

`settings.kofi.text` Button text on Ko-Fi Integration.

`settings.kofi.background-color` Background color of Ko-Fi Integration button.

`settings.kofi.text-color` Text color on Ko-Fi Integration button.

`settings.font-awesome.pro` If you want pro url enabled (true/false)

`settings.font-awesome.pro-url` The link to fontawesome pro you want to
use only used if `settings.font-awesome.pro` is enabled.

`settings.glass.color` Optional! If you want a custom color on the glass
effect

`settings.background.type` Either color or image or gradient. Decides
the type of background your card will have.

`settings.background.content` If `settings.background.type` is color
then use a hex color code, if it is image then use a image url. If it is
gradient then use the first gradient value

`settings.background.content-2` Only used if `settings.background.type`
is gradient, sets the second gradient value

`settings.favicon` Path to a favicon.

`settings.description` Meta description for your card.

`settings.image.type` Either font-awesome or image. Decides the type of
avatar you will have.

`settings.image.style` Only useful if you are using font-awesome, it
will decide what style of icon you will have. It can be solid or brand,
assuming you have the free tier of font awesome

`settings.image.content` If `settings.image.type` is font-awesome it is
an icon name. If it is `image` then an image url.

`settings.links` An array/list of links.

`settings.links.name` The display text of a link.

`settings.links.link` The link of a link.

`settings.links.image` Same as `settings.image`.

`settings.links.color` The background color of a link.

`settings.links.text-color` Overides `settings.link-color`, it sets the
color of the link

`settings.mini-links` Like `settings.links` but it only has a icon and
appears in one line, it is an array/list

`settings.mini-links.link` The link of the item

`settings.mini-links.image` Same as `settings.image`

`settings.mini-links.color` The color of the link
