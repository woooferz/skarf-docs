Make Skarf Static
============

Skarf is created with flask an it will take up your server resources as it is being rendered on the server side. To fix this you can make it static with a workaround kinda thing. Do this after you have finished configuring skarf and you just want the static files left.

First you will need ``wget``, it can be installed on unix based systems.

Run this command:
``wget --recursive --no-clobber --page-requisites --html-extension --convert-links -restrict-file-names=windows [link to your skarf instance]``

This will download your skarf instance and you will be able to view it in static form.