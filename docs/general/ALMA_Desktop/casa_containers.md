# General notes on CASA containers 

This page contains a compilation of useful notes, etc, on various CASA containers.

## Astroquery / astropy

The [astroquery tool](https://astroquery.readthedocs.io/en/latest/) is presently only installed on newer CASA containers (6.4.4-6.6.3).  To use astroquery from an appropriate CASA container, type the following to initiate an astroquery-compatible version of python:
`/opt/casa/bin/python3`
As per the [astroquery documentation](https://astroquery.readthedocs.io/en/latest/), the tool can then be used on the command line within the python environment.  For example, the following sequence of commands

`from astroquery.simbad import Simbad`

`result_table = Simbad.query_object("m1")`


`result_table.pprint()`

yield a one-line table listing some basic information about M1.

## Analysis Utilities
The [analysisUtils package](https://casaguides.nrao.edu/index.php/Analysis_Utilities) package is pre-installed on every CASA container, and is ready to use.  You may need to type
`import analysisUtils as au`
to load it.

## Firefox
The Firefox web-browser, needed for CASA commands where you are interacting with the weblogs, should available for CASA versions 6.1.0 to 6.4.3.  Error messages will pop up in your terminal window, but minimal testing suggests that it is sufficiently functional.

## UVMultiFit
The [UVMultiFit](https://github.com/onsala-space-observatory/UVMultiFit/blob/master/INSTALL.md) package is presently installed and working for all CASA 5.X versions.  To load the UVMultiFit package, initiate casa and then type

`from NordicARC import uvmultifit as uvm`
To use the pre-installed UVMultiFit test suite, first copy the test file directory to somewhere where you have write permissions.  E.g.,

`cp -r /opt/casa/NordicARC/UVMultiFit/test [mydirectory]/`

## Known Container Bugs

Most CASA5.X display a proc kill error message when exiting, but this does not appear to have any other impact on using the software.

CASA versions 6.5.0 to 6.5.2 initially launch with some display errors in the logger window.  Exiting casa (but not the container) and re-starting casa fixes the issue, i.e.,

`casa`

`exit`

`casa`

## Related Containers
A basic installation of [galario](https://mtazzari.github.io/galario/index.html) is available under the radio-submm tab of AstroSoftware.

[Starlink](https://starlink.eao.hawaii.edu/starlink), software commonly used at the JCMT, including the gaia graphical image tool, is presently available under the skaha tab of AstroSoftware.
