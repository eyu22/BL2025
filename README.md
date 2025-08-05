# Breakthrough Listen 2025: Searching for Lasers Within 100pc Using High-Resolution Spectroscopy

### Introduction
Our objectives were to compile a list of targets in the Gaia Catalog of Nearby Stars (GCNS) that have high resolution spectra associated with them and then download and search their spectra for narrowband lasers. We crossmatched the following surveys to GCNS to obtain spectra: Gaia-ESO, NEID, HIRES, KPF, HARPS, APOGEE, GALAH, and CARMENES.

### Analysis
The notebooks are organized by the steps we took to obtain and analyze the data. First, we acquired target lists from the various surveys and crossmatched them with GCNS. The scripts for this are in [compile_catalogs](compile_catalogs/). We decided to proceed by downloading spectra from the GALAH survey since it had the most matches to GCNS and also covered a wide range of stars within the H-R diagram. 
