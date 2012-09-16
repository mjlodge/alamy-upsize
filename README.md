Alamy-upsize
============

rhotoshop script to upsize photographs to meet Alamy.com's minimum size requirement

Why you need this
=================

Bulk upsizing of photos to meet Alamy's minimum uncompressed file size
requirement is harder than it sounds. Common approaches all have important
failure conditions that can cause your image submission to fail -- and the more
failures you have, the longer it takes Alamy to process your upload.

Using Photoshop "Fit image" works if all the photos have the same aspect ratio. If they don't,
you can end up with a thinner image that still isn't 48MB even though the
longest edge is the right length. It also will downsize photos that are already >48MB.

Because I often process a mix of images from different cameras, some of them
cropped to unusual aspect ratios, I needed a script that would:

a) Not downsize images that were already >48MB
b) Correctly upsize any image, regardless of aspect ratio
c) Do this automatically as part of a Photoshop batch process

How it works
============

The script calculates the uncompressed file size of the image, and if it's
>48MB, does nothing. If smaller, it uses a binary search algorithm to find
the image dimensions that upsize the image to within 10% of 48MB while
retaining the image's aspect ratio. The image
size is always guaranteed to be >48MB, but you do not want to upsize an image more than is absolutely necessary in
order to retain image quality. This "fudge factor" can be adjusted in the code.

Having found the optimal dimensions, the script does the resize using the
Bicubic Smoother algoritm.

How to use
==========

Download the script to your computer. From Photoshop, select File->Scripts->Browse...

Navigate to where you downloaded the script, select it, and click Open. I recommend putting this into an Action that you can run in Batch mode.

Licensing
=========

This script is free open source software, released under the GNU GPLv3. It is Copyright 2012 by Mathew Lodge, but is free to use under the terms of GPLv4. For
more on GPLv3, see http://gplv3.fsf.org/
