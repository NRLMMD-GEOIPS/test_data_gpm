    # # # Distribution Statement A. Approved for public release. Distribution unlimited.
    # # # 
    # # # Author:
    # # # Naval Research Laboratory, Marine Meteorology Division
    # # # 
    # # # This program is free software:
    # # # you can redistribute it and/or modify it under the terms
    # # # of the NRLMMD License included with this program.
    # # # 
    # # # If you did not receive the license, see
    # # # https://github.com/U-S-NRL-Marine-Meteorology-Division/
    # # # for more information.
    # # # 
    # # # This program is distributed WITHOUT ANY WARRANTY;
    # # # without even the implied warranty of MERCHANTABILITY
    # # # or FITNESS FOR A PARTICULAR PURPOSE.
    # # # See the included license for more details.


# v1.5.1: 2022-07-14, geoips2->geoips, consolidate test outputs, update compress scripts

### Refactor
* **File modifications**
    * Update all instances of 'geoips2' with 'geoips'
    * Update all instances of 'GEOIPS2' with 'GEOIPS'
* **Test outputs**
    * Remove all test outputs from test data repo (move to source repos)
    * Add bdeck file for reference

### Documentation Updates
* Update \*.md Distro statement headers to use 4 spaces prefix rather than ### (formatting improvement)
* **README.md**
    * Update test scripts to use $GEOIPS simplified direct test calls


# v1.4.7: 2022-05-06, goes16 background data files

### Improvements
* Adding goes16 background data files for tc2020al20teddy gmi test case


# v1.3.0: 2021-11-25, atcf->tc, remove satops

### Breaking Test Repo Updates
    * Update TC YAML metadata outputs
        * update output path to geoips_outdirs/preprocessed/tcwww
        * add sector_type: tc


# v1.2.4: 2021-11-12, original_source_filenames, simplify README

### Breaking Test Repo Updates
    * Updated all metadata YAML files with list of original_source_filenames rather than single original_source_filename

###  Improvements
    * Simplify README installation and test instructions


# v1.2.1: Updated matplotlib/cartopy versions, removed automatic TC recentering for all products

### Breaking Test Repo Updates
    * Updated cartopy to 0.20.0 and matplotlib to v3.4.3
        * test repo outputs incompatible with matplotlib < 3.4.0 and cartopy < 0.19.0
        * Older versions have figures that are very slightly shifted from later versions
        * Exclusively a qualitative difference, but it *does* cause the test comparisons to fail
    * No longer recentering all TC outputs by default
        * standard outputs are *not* recentered as of 1.2.1 - test recentering separately from other functionality


# v1.2.0: Major backwards incompatible update

###  Major New Functionality:
    * Exhaustive test scripts with final return value of 0 for successful completion of all functionality
    * Initial geotiff output support
    * Initial full disk output support
    * Night Visible products
    * Recentering / sectoring updates
 
###  Improvements
    * YAML based product specifications (references colormaps, algorithms,
      interpolation routines, coverage checks, etc)
 
###  Bug fixes
    * Resolved sectoring issue, allowing complete center coverage
        * Previously when sectoring based on min/max lat/lon, any values outside the explicit
          requested values would be masked, causing masked data on non-square datasets when 
          good data was actually available for the entire requested region. Only drop rows outside
          requested range, do not mask data.

GEOIPS2-71 GEOIPS2-6
