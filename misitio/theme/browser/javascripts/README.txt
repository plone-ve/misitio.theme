README for the 'browser/javascripts/' directory
===============================================

This folder is a Zope 3 Resource Directory acting as a repository for
javascripts.

Its declaration is located in 'browser/configure.zcml':

    <!-- Resource directory for javascripts -->
    <browser:resourceDirectory
        name="misitio.theme.javascripts"
        directory="javascripts"
        layer=".interfaces.IThemeSpecific"
        />

A javascript placed in this directory (e.g. 'main.js') can be accessed from
this relative URL:

    "++resource++misitio.theme.javascripts/main.js"

Note that it might be better to register each of these resources separately if
you want them to be overridable from zcml directives.

The only way to override a resource in a resource directory is to override the
entire directory (all elements have to be copied over).

A Zope 3 browser resource declared like this in 'browser/configure.zcml':

    <browser:resource
        name="main.js"
        file="javascripts/main.js"
        layer=".interfaces.IThemeSpecific"
        />

can be accessed from this relative URL:

    "++resource++main.js"

