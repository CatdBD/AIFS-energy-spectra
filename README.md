## AIFS Energy Spectra

This repository contains Python code and Jupyter notebooks developed during my internship at the **Australian Bureau of Meteorology (BOM)**.  
The main objective is to analyze and compare energy spectra from different weather models.

---

## Repository Structure

This repository includes two main notebooks:

- **`zonal_energy_spectrum.ipynb`**  
  Transforms regular weather fields into energy spectrum files.

- **`workspace.ipynb`**  
  A working notebook containing sections for plotting spectra and downloading IFS fields.

And results analysis :
- **`results.md`**  
  A recap of the seminar speech
  
- **`Evaluation of the ECMWF ML model AIFS.pptx`**  
  A presentation to show the plots and results obtained

---

## Environment and Requirements

A local clone of **[WeatherBench2](https://github.com/google-research/weatherbench2)** is required.  
The link to the repo is also indicated in the `"imports"` cell of the `zonal_energy_spectrum.ipynb` notebook.  

All notebooks were developed and tested on **Gadi**, the NCI supercomputer, within the conda environment **analysis3**. They may run in other environments provided that similar Python packages (xarray, dask, numpy, matplotlib, scipy, ecmwf, ecmwfapi etc.) are available.

---

## Notes

This work was carried out as part of my internship at the **Bureau of Meteorology**.  
The repository is still evolving, and scripts or notebooks may be updated over time.

---

## License

This project is distributed under the MIT License.  
See [`LICENSE`](./LICENSE) for details.

