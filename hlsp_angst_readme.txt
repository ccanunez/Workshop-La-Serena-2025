
This website contains the ANGST Photometry Repository.  The current
version is Data Release 1 (v1: September 30, 2008).

The files herein contain binary fits tables of photometry for the
ANGST sample, as defined in Dalcanton et al. 2008
(http://www.nearbygalaxies.org/papers/survey_ms.pdf). Also included
are associated reference images and raw photometry tables.

PHOTOMETRY: ACS measurements were made using the DOLPHOT (Dolphin
2000) package, and WFPC2 measurements were made using the HSTphot
pipeline described in Holtzman et al 2006, updated with the new August
2008 CTE corrections derived by Dolphin.  ACS photometry uses CTE
corrections as determined before the switch to side 2 electronics, but
the zero points in the binary fits tables have been corrected to the
most recent values published on the STScI website as of 10-Sep-2008.
New ACS CTE corrections will be incorporated into upcoming data
releases.

NOTES ON INDIVIDUAL TARGETS: The M82 fields are very crowded and
shallow, leading to low-precision photometry whose errors are
significantly underestimated by the quoted errors from DOLPHOT.
Photometry near bright diffraction spikes is unreliable; data in these
regions are provided on a shared risk basis.  Archival F814W data for
M81 tilings from GO-10250 is not included in the current release,
since the significant misalignments with the F435W and F606W data
prevents automated pipeline reductions; these data will be incorporated
in subsequent releases.  Not every ACS/WFPC2 image of target galaxies
is included in this release; pointings were excluded when images were
not of sufficient depth or wavelength coverage to be useful for
stellar photometry.  Please contact the ANGST team if you find images
in the archive that you think should be included in subsequent
releases.

NAMING CONVENTION: The field names were taken from the image headers
and are of the format PROPOSID-TARGNAME.  The naming conventions and
column names for the photometry and image files are summarized below,
as well as in the headers of the fits files themselves.  File names
also include the filters of the photometry.  For fields with three
filters, the *.st.fits and *.gst.fits files are generated for each
pair of filters; complete 3 filter photometry can be found in the much
larger *.phot files.  The headers for the binary fits tables include
extensive information on the data used for photometry (name of
reference image, filters, camera, etc).

*ref.fits: Reference image used for the alignment of the data and
determination of the X, Y, RA, and DEC (J2000) coordinates of each
star.  WFPC2 data has a separate reference image for each chip: 
*ref[1-4].fits.

*ref.jpg: JPEG image of reference image used for the alignment of the
ACS data and determination of the X, Y, RA, and DEC (J2000)
coordinates of each star.

*refmos.jpg: JPEG image of "batwing" mosaic of the 4 chips of the
reference image used for the alignment of the WFPC2 data.

*.st.fits: Star files: these files contain the photometry of all
objects classified as stars (object type <= 2) with S/N > 4 and data
flag < 8.  These files will contain more objects than the *.gst.fits
files, but will have less clean CMD features.  Columns are X, Y, RA,
DEC, MAG1_ACS, MAG1_STD, MAG1_ERR, MAG2_ACS, MAG2_STD, MAG2_ERR.
Filters are in the file name as well as the header.

*.gst.fits: Good Star files: These files contain the stars that pass
the ANGST quality cuts for sharpness and crowding (sharp_filter1 +
sharp_filter2)^2 < 0.075 && crowd_filter1 + crowd_filter2 < 0.1), in
addition to the S/N and flag criteria.  Columns are X, Y, RA, DEC,
MAG1_ACS, MAG1_STD, MAG1_ERR, MAG2_ACS, MAG2_STD, MAG2_ERR.  Filters
are in the file name as well as the header.  For WFPC2 data, the
crowding cut was 0.7.  All of this information is also in the headers
of the binary fits tables.  Caution should be used when using these
files in regions of high crowding, such as stellar clusters.

*.phot: Raw output from DOLPHOT (or in case of WFPC2 data, raw
output from HSTphot).  For DOLPHOT output, the columns are defined as
follows, as can be seen in the DOLPHOT manual 
(http://purcell.as.arizona.edu/dolphot/):

#### DOLPHOT/ACS OUTPUT ##############################
######################################################
1	extension
2	chip
3	x position
4	y position
#### GLOBAL SOLUTION #################################
5	chi
6	signal-to-noise
7	sharpness
8	roundness
9	major axis
10	crowding
11	object type (1,2 == stars)
#### PHOTOMETRY ######################################
12	counts
13	background
14	magnitude (instrumental)
15	magnitude (standard)
16	magnitude uncertainty
17	chi
18	signal-to-noise
19	sharpness
20	roundness
21	crowding
22	FWHM
23	ellipticity
24	PSF a
25	PSF b
26	PSF c
27	error flag (<8 usable)
######################################################
#### COMBINED PHOTOMETRY IS REPEATED N TIMES FOR  ####
#### N FILTERS (IN ORDER OF WAVELENGTH), FOLLOWED ####
#### BY PHOTOMETRY FOR EACH INDIVIDUAL IMAGE      ####
######################################################


For raw HSTphot output, the columns are defined as follows, as can be
seen in HSTphot manual:

#### HSTPHOT OUTPUT ##############################
######################################################
1       chip
2       x position
3       y position
#### GLOBAL SOLUTION #################################
4       chi
5       signal-to-noise
6       sharpness
7       roundness
8       major axis
9       object type (1,2 == stars)
#### PHOTOMETRY ######################################
10      counts
11      background
12      magnitude (VEGAMAG)
13      magnitude (standard)
14      magnitude uncertainty
15      chi
16      signal-to-noise
17      sharpness
18      roundness
19      crowding
######################################################
#### COMBINED PHOTOMETRY IS REPEATED N TIMES FOR  ####
#### N FILTERS (IN ORDER OF WAVELENGTH FOR FILTERS ###
#### FOR WHICH MORE THAN ONE IMAGE WAS ENTERED INTO ##
#### HSTPHOT), FOLLOWED BY PHOTOMETRY FOR EACH  ######
#### INDIVIDUAL IMAGE      ###########################
######################################################



OTHER FILES: Additional files are available at
http:www.nearbygalaxies.org.  These include ascii parameter files used
for processing, JPGs of CMDs, JPGs of field placement, etc.



