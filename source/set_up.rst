Setting-up SEXTANTE
====================

The first thing to do before using SEXTANTE is to configure it. There is not much to set-up in SEXTANTE, so this is an easy task. 

Later on we will show how to configure the external applications that SEXTANTE uses for extending the list of available algorithms, but for now we are just going to work with SEXTANTE itself.

SEXTANTE is a core QGIS plugin, which means that, if you are running QGIS 2.0, it should already be installed in your system, since it is included with QGIS. If you use a previous version of QGIS, you should install SEXTANTE manually. Since this text is targeted at QGIS 2.0 users, that will not be covered here. However, we strongly recommend to use SEXTANTE in QGIS 2.0 or higher, since earlier versions do not support the latest version of SEXTANTE.

In case SEXTANTE is active, you should see a menu called *Analysis* in your menu bar. There you will find an access to all SEXTANTE components.

.. figure::

If you cannot find that menu, you have to enable SEXTANTE by going to the plugin manager and activating it.

.. figure::

The main SEXTANTE element that we are going to work with is the toolbox. Click on the corresponding menu entry and you will see the toolbox docked at the right side of the QGIS window.

The toolbox contains a list of all the available algorithms, divided in groups. There are two ways of displaying and organizing those algorithms: the *advanced mode* and the *simplified* mode. 

By default, you will see the simplified mode, which groups algorithms according to the kind of operation they perform. Although some of the algorithms that you will see in the toolbox depend on other external applications (most of them do, in fact), you will not see any mention to those applications. The origin of algorithms is hidden in this mode, which is a facade that simplifies using algorithms through SEXTANTE.

Examples in this guide only use the simplified mode. The advanced mode has some additional features and algorithms, but it requires understanding the applications that are called by SEXTANTE, so they are a more advanced topic. Some of these more advanced ideas are introduced in the final lessons of this book, but for the rest of them we will just use the simplified interface.

You can change between the simplified and the advanced mode by using the selector on the bottom part of the toolbox.

The toolbox box, when using the advanced mode, looks like this.

.. figure::


If you have reached this point, now you are ready to use SEXTANTE. There is no need to configure anything else by now. We can already run our first algorithm, which we will do in the next lesson.