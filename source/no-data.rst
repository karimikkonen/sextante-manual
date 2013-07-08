The raster calcualtor. No-data values
============================================================


.. note:: In this lesson we will see how to use the raster calculator to perform some operations on raster layers. We will also explain what are no--data values and how the calculator and other algorithms deal with them


The raster calculator is one of the most powerful algorithms that you will find in SEXTANTE. It's a very flexible and versatile algorithm that can be used for many different calculations, and one that will soon become an important part of your toolbox. 

In this lesson we will be performing some calculation with the raster calculator, most of them rather simple. This will let us see how it is used and how it deals with some particular situations that it might find. Understanding that is important to later get the expected results when using the calculator, and also to understand certain techniques that are commonly applied with it.

Open the QGIS project corresponding to this lesson and you will see that it contains several raster layers.


.. figure::

Now open the toolbox and open the dialog corresponding to the raster calculator.

.. figure::

The dialog contains 3 parameters.

- The layers to use for the analysis. This is a multiple input, that meaning that you can select as many layers as you want. Click on the button on the right--hand side and then select the layers that you want to use in the dialog that will appear.
- The formula to apply. The formula uses the layers selected in the above parameter, which are named using alphabet letters (``a, b, c...``) or ``g1, g2, g3...`` as variable names. That is, the formula ``a + 2 * b`` is the same as ``g1 + 2 * g2`` and will compute the sum of the value in the first layer plus two times the value in the second layer. The ordering of the layers is the some ordering that you see in the selection dialog.
- Whether to use or not no--data values. A no--data value indicates that, for a given cell in the raster layer, no value has been recorded. The value for that cell is not an actual valid value, but some kind of placeholder instead. If this field is set to true, those values will be used as normal values, ignoring that they actually mean that there is no valid value for that cell. If it is false, the value will be ignored, and the result for that cell will be the no-data value (since there is one variable in the formula that has no value, there is no way of computing the result for that cell, and that is indicated by setting the no--data value for the resulting layer)


To start with, we will change the units of the DEM from meters to feet. The formula we need is the folowwing one:

::

	h' = h ********

Select the DEM in the layers field and type ``a ****** `` in the formula field.

Click *OK* to run the algorithm. You will get a layer that has the same appearance of the input layer, but with different values. This layer has valid values in all its cells, so the last parameter has no effect at all.

Let's now perform another calculation, this time on the *accflow* layer. This layer contains values of accumulated flow, a hydrological parameter. It contains those values only within the area of a given watershed, with no--data values outside of it. As you can see, the rendering is not very informative, due to the way values are distributed. Using the logarithm of that flow accumulation will yield a much more informative representation. We can calculate that using the raster calculator.

Open the algorithm dialog again, select the *accflow* layer as the only input layer, and enter the following formula: ``log(a)``. Make sure the *Use no-data values* parameter is set to false.

Here is the layer that you will get