# Results

Since early 2022, there has been an explosion in the number and skill of AI/ML-based weather and climate models, with many such models now able to predict the atmosphere with competitive skill to the world’s leading dynamical models (Rasp et al., 2024). This project involves evaluation of the ECMWF **AIFS** and **AIFS-ENS** models with a focus on physical realism, specifically through studying how well they represent turbulence cascades - a feature that manifests as predictable behavior in the atmospheric energy spectra.

---

## Introduction

A well-known limitation of ML models in meteorology is the so-called *double penalty issue*, which tends to blur spatial fields. An open question is whether this blurring reflects a genuine loss of energy at small scales, or whether turbulence can in fact be learned by AI models.  

At the same time, AI-based systems are known to perform particularly well at large scales (~1000 km), where they are already competitive with leading numerical weather prediction (NWP) systems.

The objective of this study is therefore to assess the physical realism of **AIFS** and its ensemble counterpart **AIFS-ENS** (released on 1 July 2025). To do so, we focus on the energy cascade by analyzing the atmospheric kinetic energy spectrum. This spectrum, obtained through spectral decomposition, describes the distribution of kinetic energy across spatial scales:  

- High wavenumbers correspond to **3D turbulent processes**  
- Low wavenumbers are associated with **quasi-balanced large-scale dynamics**

---

## Plot Description

The Fourier transform is applied along circles of constant latitude, which allows efficient averaging within the project time constraints.  

- **x-axis:** wavenumber  
- **y-axis:** spectral amplitude  

Reference scales indicated on the plots include:  

- The **resolution cutoff**, beyond which models are not representative (λ < 4Δx)  
- The **theoretical slope** of the turbulent regime  

---

## Results

We compare the following models:  

- **AIFS** and **AIFS-ENS** (ECMWF AI models)  
- **ERA5**, the ECMWF reanalysis on which AIFS was trained (reference replay dataset)  
- **IFS analysis**, the operational ECMWF dynamical analysis used as initial conditions for AIFS  
- **IFS forecast**  

### Spectral behavior

As expected, all models perform well at large scales. Differences arise at smaller scales:  

- **ERA5** decays more rapidly and departs from the theoretical slope.  
- **IFS analysis** follows the slope over a broader range but loses energy at the smallest scales.  
- **AIFS** underestimates mesoscale energy (wavenumbers 50-200) but recovers the theoretical slope at higher wavenumbers.  
- **AIFS-ENS** provides the closest match to the theoretical slope: it still loses some mesoscale energy, but far less than AIFS-single or even ERA5.  

This last result is particularly striking.

---

## Comparison with Other AI Models

Additional context can be obtained from Google’s **WeatherBench2** platform, which presents comparable diagnostics for models such as **GraphCast** and **Pangu-Weather**. Notably, AIFS-ENS retains more energy across wavenumbers than ERA5, contrasting with the behavior of these other AI systems.

---

## Lead-Time Dependence

We also examine the evolution of spectra with lead time (from +6 h to +360 h):  

- **AIFS-single** continues to lose energy up to +100 h before stabilizing, with performance already substantially degraded by +48 h.  
- **AIFS-ENS**, in contrast, shows virtually no degradation with lead time, maintaining a realistic energy spectrum throughout the forecast range.  
