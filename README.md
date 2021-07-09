## Note! I no longer use Github. This repo may be out of date.

All my ex-Github repos are now stored and maintained at [my personal website](http://www.robertgrantstats.co.uk/code.html).

Why did I leave Github? Because I consider the compulsory imposition of 2-factor authentication to be inappropriate for people writing software, including cryptography, which can attract severe punishments in certain jurisdictions. We all know that the organisations that hold the 2nd factors (mobile telephony providers, tech companies) are compromised, willingly or otherwise, in their relationships with security agencies, benign or otherwise.

Why not just close it down? Because you might use it programmatically, via http or API, and I don't want to hurt you (by breaking your code) while trying to help you (by raising issues of privacy and confidentiality).


pictogram
=========

R function for pictograms

Surprisingly, there doesn't seem to be any major stats software out there providing pictograms. By pictogram, I mean one of those graphics where there are rows of little icons showing a count for each of several groups. This R function aims to get you started making your own.

You specify the following arguments:
*   icon - a list of raster images, or a single raster image to be shared among groups
*   n - a vector of integer counts, one for ecah group
*   grouplabels - a character vector of labels, one for each group
*   hicons - maximum number of icons to show in one row before starting the next one, default 20
*   vspace - the ratio of vertical blank space between groups to the vertical height of the icons, default 0.5
*   labprop - the ratio of width on the left of the axis (for labels), to the width on the right (for icons), default 0.2
*   labelcex - the cex parameter for text labels, default 1

Note that when I talk about the "vertical height of the icons", the function will use the icon with the greatest height:width aspect ratio for this. You should *avoid* using a mixture of icons that differ a lot in aspect ratio, because groups will appear at a glance to be more or less imposing than they really are.

It is up to you to use a package like jpeg or png to read in images as raster arrays and then supply these as the icons.

This function depends on one package: reshape

Things to do:
-------------

*   Allow for non-integer n, which will show part of an icon at the end of a row.
*   Allow more graphical parameters to be passed, like main()
*   Create internal vectors "spacing" and "x0" in more efficient ways (not important)
*   Consider resizing the raster once prior to plotting (for speed improvements)
