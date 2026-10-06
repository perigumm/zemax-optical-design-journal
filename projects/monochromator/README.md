# Sequential Mode Monochromator Design Study

> **STATUS: IN PROGRESS**  
> *This project documents an active optical design study. Layouts, parameters, and configurations are subject to continuous revision as beam geometries and dispersion criteria are solved.*

**Role:** Optical Designer  
**Tool:** Ansys Zemax OpticStudio (Sequential Mode)

---

## 1. Project Objective

The goal of this project is to model and optimize a dispersion-based grating monochromator in Zemax OpticStudio Sequential Mode. The instrument is intended to isolate narrow spectral bandwidths around a central reference wavelength ($\approx 0.588\text{ μm}$) using an entrance slit, collimating optics, a planar reflection/transmission diffraction grating, and re-imaging optics onto an exit slit or detector plane.

---

## 2. Current Configuration & Parameters

| Parameter | Current Value / Baseline | Status |
| :--- | :--- | :--- |
| **Operating Central Wavelength** | $\approx 0.588\text{ μm}$ | Defined baseline |
| **Spectral Range** | Visible band around central line | Under definition |
| **Collimation Subsystem** | Under evaluation | Determining focal length & beam footprint |
| **Dispersive Element** | Diffraction Grating (Sequential surface) | Solving line density ($lines/mm$) and blaze angle |
| **Working Diffraction Order ($m$)** | $m = \pm 1$ | Evaluating order efficiency & dispersion |
| **Optical Configuration Type** | Collimator $\rightarrow$ Grating $\rightarrow$ Focusing Lens/Mirror | Assessing folded (e.g., Czerny-Turner/Ebert-Fastie) vs. in-line |

---

## 3. Current Progress

* Modeled collimated ray bundles at $\lambda = 0.588\text{ μm}$ entering the dispersive stage.
* Implemented diffraction grating surface definitions in Zemax Sequential Mode utilizing grating coordinate breaks to trace diffracted orders.
* Began calculating angular dispersion and grating equation constraints:

$$m \lambda = d (\sin \alpha + \sin \beta)$$

* Investigated beam footprint behavior on the grating clear aperture to prevent vignetting during rotational tuning.

---

## 4. Technical Problems Under Investigation

* **Beam Path & Angle Management:** In Sequential Mode, handling non-zero diffraction angles across multiple configurations requires precise Coordinate Breaks. Ensuring chief ray centering through subsequent focusing optics is currently being resolved.
* **Aberration Balancing across Spectral Band:** Anamorphic magnification caused by grating diffraction ($\frac{\cos\alpha}{\cos\beta}$) introduces asymmetry into the collimated bundle, complicating symmetric focusing.
* **Optical Architecture Selection:** Evaluating whether an off-axis parabolic (OAP) mirror system or an achromatized refractive doublet offers the best balance between chromatic correction, envelope size, and stray light.

---

## 5. Next Milestones

- [ ] Finalize grating groove frequency ($lines/mm$) to achieve target reciprocal linear dispersion ($nm/mm$).
- [ ] Implement and constrain focusing optics to image diffracted ray bundles onto the exit plane.
- [ ] Construct multi-configuration editor (MCE) setups to evaluate wavelength scanning via grating rotation.
- [ ] Evaluate resolution criteria: Rayleigh criterion, entrance/exit slit width convolution, and spectral line shapes.
