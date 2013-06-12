CRSs. Reprojecting
============================================================


.. note:: In this lesson we will discuss how SEXTANTE uses CRSs. We will also see a very useful algorithm: reprojecting.


CRS's are a great source of confusion for SEXTANTE users, so here are some general rules about how they are handled by SEXTANTE when creating a new layer

- If there are input layers, it will use the CRS of the first layer. This is assumed to be the CRS of all input layers, since they should have the same one. If you use layers with unmatching CRS's, SEXTANTE will warn you about it. Notice that the CRS of input layers is shown along with its name.

.. figure::

- If there are no input layer, it will use the project CRS, unless the algorithm contains a specific CRS field (as it happenend in the last lesson with the graticule algorithm)

Open the project corresponding to this lesson and you will see two layers named 23030 and 4326. They both contain the same points, but in different CRSs (EPSG:23030 and EPSG:4326). They appear in the same place because QGIs is reprojecting on the fly to the project CRS (EPSG:4326), but they are not actually the same layer.

Open the *Add coordinates to points* algorithm.

.. figure::

In the list of available layers that you will find in the input layer field, you will see each one with its corresponding CRS. That means that, although they appear in the same place in your canvas, SEXTANTE will treat them differently. Select the 4326 layer and run the algorithm.

You should get a new layer with exactly the same points as the other two layers. If you right click on the name of the layer and open its properties, you will see that it shares the same CRS of the input layer, that is, EPSG:4326. When the layer is loaded into QGIS, you will not be asked to enter the CRS of the layer, since SEXTANTE will take care of telling QGIS about it.

If you open the attributes table of the new layer you will see that it contains two new fields with the X and Y coordinates of each point.

.. figure::

Now do the same with the other layer. You should find it rendered exactly in the same place as the other ones, and it will have the EPSG:23030 CRS, since that was the one of the input layer.

If you go to its attribute table, you will see values that are different to the ones in the first layer that we created.

.. figure::

This is because the original data is different, and those corrdinates are taken from these different values.

What should you learn from this? The main idea behind these examples is that SEXTANTE uses the layer as it is in its original data source, and completely ignores the reprojections that QGIS might be doing before rendering. In other words, do not trust what you see in the canvas, but always have in mind that SEXTANTE will use the original data. That is no so important in this case, since we are just using one single layer at a time, but in an algorithm that needs several of them (such as a clip algorithm), layers that appear to match or overlay might be very far one from each other, since they might have different CRSs. 

SEXTANTE performs no reprojection (except in the reprojection algorithm that we will soon see), so it is up to you to make sure that layers have matching CRS's.


An interesting module that deals with CRS's is the reprojection one. It represents a particular case, since it has an input layer (the one to reproject), but it will not use its CRS for the the output one.

Open the *Reprojection* algorithm.

.. figure::

Select any of the layers as input, and select EPSG:23029 as the destination CRS. run the algorithm and you will get a new layer, identical to the input one, but with a different CRS. It will appear on the same region of the canvas, like the other ones, since QGIS will reproject it on the fly, but its original coordinates are different. You can see that by running the *Add coordinates to points* algorithm using this new layer as input, and veryfing that the added coordinates are different to the ones in the attribute tables of both of the two layers that we had computed before.