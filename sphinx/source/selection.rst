Selection
============================================================


.. note:: In this lesson we will see how SEXTANTE handles selections in vector layers that are used as inputs for a SEXTANTE algorithm, and how to create a selection using a particular type of algorithm.


Unlike other analysis plugins in QGIS, you will not find in SEXTANTE any "Use only selected features" checkbox or similar. The behaviour regarding selection is set for the whole plugin and all its algorithms, and not for each algrithm execution. SEXTANTE follows the following simple rules when using a vector layer.

- If the layer has a selection, only selected features are used.
- If there is no selection, all features are used.


You can test that yourself by selecting a few points in any of the layers that we used in the last chapter, and running the reprojection algorithm on them. The reprojected layer that you will obtain will contain only those points that were selected, unless there was no selection, which will cause the resulting layer to contain all points from the origin layer.

To make a selection, you can use any of the available methods and tools in QGIS. However, you can also use SEXTANTE algorithms to do so. Algorithms for creating a selection are found in the toolbox under *Vector/Selection*

.. image:: img/selection/selection_algs.png

Open the *Random selection* algorithm.

.. image:: img/selection/random_selection.png

Leaving the default values, it will select 10 points from the current layer.

.. image:: img/selection/selected.png

You will notice that this algorithm does not produce any output, but modifies the input layer (not the layer itself, but its selection). This is an uncommon behaviour, since all the rest of SEXTANTE algorithms will produce new layers and not alter the input layers.

Since the selction is not part of the data itself, but something that only exist within GIS, these selection algorithms only must be used selecting a layer that is open in QGIS, and not with the file selection option that you can find in the corresponding parameter value box.

The selection we have just made, like most of the ones created by the rest of the SEXTANTE selection algorithms, can also be done manually from QGIS, so you might be wondering what is the point on using SEXTANTE for that. Although now this might not make much sense to you, we will later see how to create models and scripts in SEXTANTE. If you want to make a selection in the middle of a model (which defines a processing workflow), only SEXTANTE algorithms can be added to a model, and other QGIS elements and operations cannot be added. That is the reason why some SEXTANTE algorithms duplicate functionality that is also available in other QGIS elements.

By now, just remember that selections can be made using SEXTANTE algorithms, and that SEXTANTE algorithms will only use the selected features if a selection exists, or all features otherwise.