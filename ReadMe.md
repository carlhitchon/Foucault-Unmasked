# Foucault-Unmasked
Software for analyzing Foucault images of a mirror without the use of a mask.

  This software will analyze foucault images of a mirror and produce information about the mirror's surface, including a error plots, 
  Strehl ratio, RMS error etc.
  To use the software you need to photogragh foucault images of your mirror (withouut the use of a mask). An image is required for each 
  zone you want to include in the analysis. Generally it's easyist if you start with the central zone and then move the knife edge by a 
  fixed amount for each subsequent zone until you reach the edge zone.  The more zones you photogragh, the more detailed the results will be.
  Please read the Help Overview before using as it provides detailed instructions. The UI controls have tool-tips that popup if you hover 
  the mouse pointer over a contol.

Updates:

Version 3.0 (beta version)
-----------

New Features

    Main Window
        Help
            The Overview has been updated to reflect many changes - please reread it.

        Results File
            The .CVS results file type is currently not working. It may be changed to an XML file in the future.

        Mirror Parameters
             A central hole or obstruction diameter has been added. The program does not look for null zones in this area and 
             it is not shown in error plots.

        Images
            The KE offset auto-assignment has been made more flexible. Offsets can now be applied to either all images or
            to only selected images. When applied, the starting KE offset is obtained from the first image and
            remaining image offsets are set by incrementing the offset by an interval for each subsequent image.

            The Analyze Images button now checks for failed images (no null zone found) and optionally deletes them. They 
            must be deleted before the Show Results... button is used. This change resolves some zone numbering issues.

            The Show Results... button has been moved into this group (under the Analyze Images button).

            Images List
                The # column (formerly Row #) is now consitent with the zone numbers displayed in plots and saved in .fig or
                .set files.
                The Image File Name column now shows only the simple file name. The full pathname can be 
                displayed by placing the mouse pointer near the file name.

    Results Window
        The results window is now independent of the main window. The main window can be accessed while the Results window is open. 
        However, changes in Main Window that effect results will cause the Results window to be closed.

        Summary - summary of surface errors. The volume of substrate remaining has been added. PV is available for surface.

        Plots - additional error plots have been added.

            Millies-Lacroxi plot   - displays the longitudinal error at the center of curvature (with error bounds).
            Weighted Surface Error - the surface error weighted by radius. Outer radii contribute more to RMS error.
            Transverse Error       - the distances from the optical axis at the focal plane of rays reflected from infinity 
                                     (with airy disk bounds).

        Target Conic Surface - this group sets parameters for a conic surface to be fitted to the mirror surface.
            The target conic surface can now be fitted by either minimizing the RMS error or the volume of substrate that 
            must be removed.
            The conic constant can now be varied, reset to the originally specified value or set to the best fit value.

        Edge Mask - this group applies a mask to the outer portion of the mirror, e.g. to view errors after a TDE is masked off.

Issues     
    The CSV results file type is not working currently. It will be updated to an XML file with more data, including image file names.

    This release is a beta version.
