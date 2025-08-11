# Breakthrough Listen 2025: Searching for Lasers Within 100pc Using High-Resolution Spectroscopy

### Introduction
Our objectives were to compile a list of targets in the Gaia Catalog of Nearby Stars (GCNS) that have high resolution spectra associated with them and then download and search their spectra for narrowband lasers. We crossmatched the following surveys to GCNS to obtain spectra: Gaia-ESO, NEID, HIRES, KPF, HARPS, APOGEE, GALAH, and CARMENES.

### Overview
The notebooks are organized by the steps we took to obtain and analyze the data. First, we acquired target lists from the various surveys and crossmatched them with GCNS. The scripts for this are in [compile_catalogs](compile_catalogs/). We decided to proceed by downloading spectra from the GALAH survey since it had the most matches to GCNS and also covered a wide range of stars within the H-R diagram. Next, we experimented with using a modified version of SciPy's find_peaks() function to detect potential narrowband laser emissions from the spectra in [find_peak.ipynb](find_peak/find_peak.ipynb). To test this out we injected artificial lasers of varying amplitudes and widths and ran our modified peak detection algorithim on them in [inject_laser.ipynb](get_spectra/inject_laser.ipynb). We then ran this process on a sample of 40 spectra in two ways: (1) injecting 1 laser per spectrum and trying to recover it, and (2) injecting 1000 lasers per spectrum and tryiing to recover each one individually.


# Repository Organization

## Root Files

| File Name | Description |
|-----------|-------------|
| `README.md` | This documentation file |
| `calc_laser.ipynb` | Some calculations for the minimum intensity laser that we can detect |
| `invalid_fits_files.csv` | Checks the ~17000 FITS files downloaded from GALAH for invalid ones |

---

## Folder: `compile_catalogs`

| File Name | Description |
|-----------|-------------|
| `CARMENES_names.txt` | Needed for querying the CARMENES catalog |
| `catalog_summary.csv` | Output of compile_catalogs.ipynb |
| `compile_catalogs.ipynb` | Crossmatches catalogs to GCNS into one CSV  |
| `get_gcns_names.ipynb` | Produces GCNS coords and names lists as `.txt` files |

---

## Folder: `example_spectra`

Example FITS files of spectra

---

## Folder: `find_peak`

| File Name | Description |
|-----------|-------------|
| `find_peak.ipynb` | Intial draft of developing a modified find_peaks() function |
| `find_peak_demo.ipynb` | Draft of incorporating find_peaks() in practice to multiple spectra |
| `find_peak_statistics.ipynb` | Runs find_peak.ipynb on multiple spectra |
| `single_laser_injection_results.npz` | Results of find_peak_statistics, 1 injection + recovery per spectrum |
| `thousand_laser_injection_results.npz` | Results of find_peak_statistics, 1000 injections + recoveries per spectrum |

---

## Folder: `gcns_searchlists`

This contains the coordinates of all objects in the GCNS, broken into 10 `.txt` files in the format (RA [tab] DEC). Useful for crossmatching.

---

## Folder: `get_spectra`

| File Name | Description |
|-----------|-------------|
| `download_galah.ipynb` | Downloads FITS files of spectra from full GALAH dataset |
| `inject_laser.ipynb` | Initial draft of injecting artificial laser into spectra |
| `interactive_spectra_demo.ipynb` | Demo taken from [GALAH website](https://www.galah-survey.org/dr4/the_spectra/) |
| `simple_spectrum_demo.ipynb` | Figuring out how to download and plot all cameras of spectra from GALAH |
| `spectra_demo.ipynb` | Demo taken from [GALAH website](https://www.galah-survey.org/dr4/the_spectra/) |

---

