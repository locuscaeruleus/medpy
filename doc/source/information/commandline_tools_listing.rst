.. _top:

=========================
List of commandline tools
=========================
MedPy is shipped with a number of python scripts (little programs) that are installed on your system together with MedPy. On this page you can find a short overview over these scripts.
All are prefixed with **medpy_**.

Categories
==========
* :ref:`basic`
* :ref:`volume`
* :ref:`binary`
* :ref:`filter`
* :ref:`mr`
* :ref:`gc`
* :ref:`itk`
* :ref:`others`

.. _basic:

Basic image manipulation
========================
:ref:`↑top <top>`

.. topic:: medpy_info.py

	Prints basic information about an image to the stdout.

.. topic:: medpy_convert.py

	Converts between two image formats. Alternatively can be used to create an empty image by example.

.. topic:: medpy_create_empty_volume_by_example.py

	Can be used to create an empty image by example.

.. topic:: medpy_resample.py

	Re-samples an image using b-spline interpolation.

.. topic:: medpy_set_pixel_spacing.py

	Manually set the pixel/voxel spacing of an image.

.. todo:: Change script, such that it can work on an image directly

.. topic:: medpy_diff.py

	Compares the meta-data and intensity values of two images.

.. topic:: medpy_grid.py

	Creates a binary volume containing a regular grid.

.. topic:: medpy_extract_min_max.py

	Extracts the min and max intensity values of one or more images.

.. topic:: medpy_swap_dimensions.py

	Swap two image dimensions.


.. _volume:

Image volume manipulation
=========================
:ref:`↑top <top>`

.. topic:: medpy_extract_sub_volume.py

	Extracts a sub volume from an image.

.. topic:: medpy_extract_sub_volume_auto.py

	Splits a volume into a number of sub volumes along a given dimension. 

.. topic:: medpy_extract_sub_volume_by_example.py

	Takes an image and a second image containing a binary mask, then extracts the sub volume of the first image defined by the bounding box of the foreground object in the binary image.

.. topic:: medpy_join_xd_to_xplus1d.py

	Joins a number of xD images by adding a new dimension, resulting in a (x+1)D image.

.. topic:: medpy_split_xd_to_xminus1d.py

	Splits a xD image into a number of (x-1)D images.

.. topic:: medpy_stack_sub_volumes.py

	Stacks a number of sub volumes together along a defined dimension.

.. topic:: medpy_zoom_image.py

	Enlarges an image by adding (interpolated) slices.

.. topic:: medpy_shrink_image.py

	Reduces an image by simply discarding slices.

.. topic:: medpy_reslice_3d_to_4d.py

	Reslices a 3D image formed by stacked up 3D volumes into a real 4D images (as e.g. often necessary for DICOM).

.. topic:: medpy_dicom_slices_to_volume.py

	Takes a number of 2D DICOM slice (a DICOM series) and creates a 3D volume from them.

.. topic:: medpy_dicom_to_4D.py

    Takes a number of 2D DICOM slice (a DICOM series) and creates a 4D volume from them (split-points are passed as arguments).


.. _binary:

Binary image manipulation
=========================
:ref:`↑top <top>`

.. topic:: medpy_merge.py

	Performs a logical OR on two binary images.


.. _filter:

Image filters
=============
:ref:`↑top <top>`

.. topic:: medpy_gradient.py

	Gradient magnitude image filter. Output is float.

.. topic:: medpy_morphology.py

	Apply binary morphology (dilation, erosion, opening or closing) to a binary image.

.. topic:: medpy_anisotropic_diffusion.py

	Apply the edge preserving anisotropic diffusion filter to an image.

.. topic:: medpy_watershed.py

    Applies a watershed filter, results in a label map / region image.


.. _mr:

Magnetic resonance (MR) related
===============================
:ref:`↑top <top>`

.. topic:: medpy_apparent_diffusion_coefficient.py

	Computes the apparent diffusion coefficient (ADC) map from two diffusion weight (DW) volumes acquired with different b-values.

.. topic:: medpy_intensity_range_standardization.py

	Standardizes the intensity ranges of a number of MR images and produces a corresponding model that can be applied to new images.


.. _gc:

Graph-cut
=========
:ref:`↑top <top>`

GC based on (and shipped with, ask!) Max-flow/min-cut by Boykov-Kolmogorov algorithm, version 3.01 [1]_.

.. topic:: medpy_graphcut_voxel.py

	Executes a voxel based graph cut. Only supports the boundary term.

.. topic:: medpy_graphcut_label.py

	Executes a label based graph cut. Only supports the boundary term.

.. topic:: medpy_graphcut_label_bgreduced.py

	Executes a label based graph cut. Only supports the boundary term. Reduces the input image by considering only the region defined by the bounding box around the background markers.

.. topic:: medpy_graphcut_label_wsplit.py

	Executes a label based graph cut. Only supports the boundary term. Reduces the memory requirements by splitting the image into a number of sub-volumes. Note that this will result in a non-optimal cut.

.. topic:: medpy_graphcut_label_w_regional.py

	Executes a label based graph cut. With boundary and regional term.

.. topic:: medpy_label_count.py

	Counts the number of unique intensity values in an image i.e. the amount of labelled regions.

.. topic:: medpy_label_fit_to_mask.py

	Fits the labelled regions of a label map image to a binary segmentation map.

.. topic:: medpy_label_superimposition.py

	Takes to label maps and superimpose them to create a new label image with more regions.


.. _itk:

Scripts requiring ITK
=====================
:ref:`↑top <top>`

All of the scripts in this section require the ITK Python bindings to be installed.

.. topic:: medpy_itk_smoothing.py

	Applies the edge preserving anisotropic diffusion filter to an image.

.. topic:: medpy_itk_gradient.py

	Applies a gradient magnitude filter.

.. topic:: medpy_itk_watershed.py

	Applies a watershed filter, results in a label map / region image.


.. _others:

Others
======
:ref:`↑top <top>`

.. topic:: medpy_check_marker_intersection.py

	Special marker intersection check for the MICCAI'12 cardiac segmentation challenge.

.. topic:: medpy_evaluate_miccai2007.py

	Performs binary segmentation evaluation according to the MICCAI'07 SLiver challenge.

References
==========
.. [1] http://vision.csd.uwo.ca/code/
