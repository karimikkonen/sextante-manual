Running an external algorithm
============================================================


.. note:: In this lesson we will see how to use algorithms that depend on a third-party application, particularly SAGA, which is one of the main algorithm providers using by SEXTANTE.

All the algorithms that we have run so far are part of SEXTANTE. That is, they are *native* algorithms implemented in the SEXTANTE plugin and run by QGIS just like SEXTANTE itself is run. However, one of the greatest features of SEXTANTE is that it can use algorithm from external application and extend the possibilites of those applications. Such algorithms are wrapped and included in SEXTANTE, so you can easily use them from QGIS, and use QGIS data to run them.

Some of the algorithms that you see in the simplified view require third party applications to be installed in your system. One algorithm provider of special interest is SAGA (System for Automated Geospatia Analysis). At the end of this lesson we will run an algorithm called *Convergence index*, which is provided by SAGA and computes a morphometrical measurement from a DEM. But first, we need to configure the 