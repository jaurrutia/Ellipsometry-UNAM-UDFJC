# Ellipsometry Data Analysis Using Open-Source Tools
### Jonathan A. Urrutia-Anguiano

---
**RefEllips · pyElli · (pending: regress-pro)**
---
`<img src="https://upload.wikimedia.org/wikipedia/commons/2/2e/Escudo_UD.svg" alt="Universidad Distrital Francisco José de Caldas" width="200"/>`{=html}

```{=html}
<p align="center">
```
`<img src="assets/logo_facultad_ciencias_unam.png" alt="Facultad de Ciencias UNAM" width="200"/>`{=html}
    
`<img src="assets/logo_udistrital.png" alt="Universidad Distrital Francisco José de Caldas" width="200"/>`{=html}
```{=html}
</p>
```
This repository compiles the technical notes, scripts, workflows, and
results obtained during a short research stay at the **Optical
Characterization Laboratory** of the **Scientific and Didactic
Instrumentation Group (GICD)** at the **Universidad Distrital Francisco
José de Caldas**, Bogotá, Colombia.\
The work focuses on analyzing ellipsometric data acquired with a
**HORIBA commercial ellipsometer**, using open-source software tools for
data processing, model fitting, and optical response extraction.

## Research Stay Information

-   **Student:** *Jonathan Urrutia*\
-   **Program:** PhD in Science (Physics), Facultad de Ciencias, UNAM\
-   **Advisor:** Dr. **Alejandro Reyes-Coronado** (UNAM)\
-   **Host institution:** **Universidad Distrital Francisco José de
    Caldas**\
-   **Host research group:** Scientific and Didactic Instrumentation
    Group (GICD)\
-   **Laboratory:** Optical Characterization Laboratory\
-   **Host researcher:** Dr. **César Herreño**\
-   **Location:** Bogotá, Colombia\
-   **Dates:** *November 12--28, 2025*\
-   **Financial support:** Mobility funding granted by the **Facultad de
    Ciencias, UNAM**.

## Purpose of This Repository

This repository documents the use of open-source tools to:

1.  **Import, process, and analyze ellipsometric measurements** obtained
    with a HORIBA ellipsometer.\
2.  **Fit optical models** and extract parameters such as dielectric
    functions, film thicknesses, effective refractive indices, and
    structural parameters of disordered metasurfaces.\
3.  **Compare fitting algorithms, modeling approaches, and analysis
    pipelines** across different open-source packages.

## Tools Explored

### RefEllips

-   Importing HORIBA datasets\
-   Initial parameter fitting\
-   Parameter sweeps\
-   Goodness-of-fit evaluation (MSE)

### pyElli

-   Dielectric function estimation\
-   Effective medium modeling\
-   Custom spectral-analysis routines

### regress-pro (pending)

## Repository Structure

    ├── assets/
    │   ├── logo_facultad_ciencias_unam.png
    │   └── logo_udistrital.png
    ├── data/
    │   ├── raw/
    │   └── processed/
    ├── notebooks/
    │   ├── refellips_examples.ipynb
    │   ├── pyelli_workflow.ipynb
    │   └── dielectric_function_estimation.ipynb
    ├── models/
    │   └── metasurface_effective_model.json
    ├── scripts/
    │   ├── import_horiba.py
    │   ├── fit_refellips.py
    │   └── fit_pyelli.py
    └── README.md

## Scientific Context

This work forms part of my PhD project on the **theoretical, numerical,
and experimental study of disordered plasmonic metasurfaces for
biosensing applications**. It includes comparison of measurements from
the INAOE and the GICD, evaluation of phase‑retrieval algorithms, and
determination of effective dielectric functions.

## Contact

**Jonathan Urrutia**\
Facultad de Ciencias, UNAM\
Email: \[your email here\]
