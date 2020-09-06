# Template file structure for surface-wave testing projects

> Joseph Vantassel, The University of Texas at Austin

[![LICENSE](https://img.shields.io/badge/license-CC--By--SA--4.0-brightgreen.svg)](https://github.com/jpvantassel/sw-template/blob/master/LISCENSE.md)

## General Guidelines

- Prefer easily readable formats (i.e., `.txt` and `.csv`) over proprietary
  formats (i.e., `.xlsx` and `.docx`).
- Prefer multiple simple files (i.e., multiple `.csv`) over one large complex
  file (i.e., `.xlsx` workbook with multiple sheets).
- If something is unusual about the work add a `meta.md` with narrative
  information regarding what you did and why it was necessary.
- Avoid saving many output figures to disk, instead organize them in a notebook
  or better yet create a proper summary document describing your work.
- Avoid directory and file name capitalization.
- Do not use spaces or special characters in your file and directory names.
- Prefer the use of `_` (i.e., `snake_case`) to delineate words instead of
  capitalization (i.e., `camelCase`).
- Keep file names short, descriptive, and easy-to-read.

## Outline

- [coordinates](https://github.com/jpvantassel/sw-template/blob/master/coordinates)
  - Includes relative and absolute coordinates for the project. It contains
    three subdirectories as follows:
    - [construction](https://github.com/jpvantassel/sw-template/blob/master/coordinates/construction)
      - Should contain the coordinates in the most raw form.
      - Should provide a clear and logical progression from raw to final coordinates.
    - [final](https://github.com/jpvantassel/sw-template/blob/master/coordinates/final)
      - Include final coordinates, specifically:
        - `master.csv` with the final coordinates of all passive-stations.
        - `c60.txt` Should contain a separate geopsy-style coordinate file for each passive array.
    - [kml](https://github.com/jpvantassel/sw-template/blob/master/kml)
      - Includes kml files for viewing site information in Google Earth, specifically:
        - `planning.kml` which shows the site characterization as planned.
        - `as-built.kml` which shows the acquisition as it was performed.
      - Arrays should be divided into groups.
      - Each sensor should be named using its number and its associated array.
- [fk](https://github.com/jpvantassel/sw-template/blob/master/fk)
  - Includes results for frequency-wavenumber processing, specifically:
    - `.max` and `.log` files for each 2D array,
    - `mam.ipynb` for post-processing, and
    - `.json` with post-processed dispersion peaks.
- [geopsy_db](https://github.com/jpvantassel/sw-template/blob/master/geopsy_db)
  - Includes geopsy database(s). A database should:
    - Exist for each array.
    - Include the relative coordinate for each station.
    - Include at a minimum all three components (XYZ) together, though you may
      produce subdivided groups (i.e., Z alone) if desired.
- [hvsr](https://github.com/jpvantassel/sw-template/blob/master/hvsr)
  - Includes results of horizontal-to-vertical spectral ratio processing, specifically:
    - `hvsr.ipynb` for processing.
    - `f0.csv` or `t0.csv` with the mean and standard deviation of frequency or period respectively.
    - `hvsr.kml` which shows the distribution of frequency/period.
- [inversion](https://github.com/jpvantassel/sw-template/blob/master/inversion)
  - Includes information necessary for inversion. It includes, subdirectories
  as follows:
    - [0_targets](https://github.com/jpvantassel/sw-template/blob/master/inversion/0_target)
      - Includes dinver-style `.target` files.
    - [1_parameters](https://github.com/jpvantassel/sw-template/blob/master/inversion/1_parameters)
      - Includes dinver-style `.param` files.
    - [2_reports](https://github.com/jpvantassel/sw-template/blob/master/inversion/2_reports)
      - Includes dinver-style `.report` files.
    - [3_text](https://github.com/jpvantassel/sw-template/blob/master/inversion/2_reports)
      - Includes dinver-style `_GM.txt` and `_DC.txt` files.
    - Additional files for pre- and post-processing will be kept in the inversion
    directory. Do not place processing files in any of the directories listed above.
- [masw](https://github.com/jpvantassel/sw-template/blob/master/masw)
  - Includes multi-channel analysis of surface waves data, specifically:
    - `masw.ipynb` for processing and post-processing,
    - `.json` file from processing,
    - `.json` file from post-processing.
- [raw_data](https://github.com/jpvantassel/sw-template/blob/master/raw_data)
  - Includes the data in its most raw form. It includes, two subdirectories
    `active` and `passive` for each type of testing performed.
  - Each directory should include a `meta` directory will any relevant
    meta information.
- [reports](https://github.com/jpvantassel/sw-template/blob/master/reports)
  - Includes incoming and out-going summary reports. Should contain a
    subdirectory indicating where it is going or who it is from (e.g., `from_jd`
    to indicate a report from `Jane Doe`). The directory should include
    the report and any supporting information and figures. Avoid performing
    analyses in these directories.
- [site_information](https://github.com/jpvantassel/sw-template/blob/master/site_information)
  - Includes site information such as general geologic information, site
    specific references, invasive testing data/results, and other useful
    references for performing surface wave inversion.
- [spac](https://github.com/jpvantassel/sw-template/blob/master/mspac)
  - Includes results of the spatial auto-correlation processing, specifically:
    - `.max` and `.log` files for each 2D array.
- [unprocessed_data](https://github.com/jpvantassel/sw-template/blob/master/unprocessed_data)
  - Includes data in the most ready-to-be-use form, specifically:
    - MASW and MAM array data should be separated into their own directories
      where each array is named by its testing type and its name/id (e.g.
      `masw_array1` or `mam_c150`).
    - MASW data should consist of unstacked, `seg2` data files with correct
      header information. __Do not rely on the data sheets to note incorrect
      header information, instead fix the error before transferring it.__
    - MAM data should consist of trimmed `.mseed` files with the header
      information entered correctly, this at a minimum should include the
      `group id`, `station number`, and the associated `array`.
    - Typed summaries of the meta-data in picture-ready `.pdf` format.
