# SWIR Varifocal Catadioptric Telescope System

**Status:** Completed  
**Role:** Student completing capstone project while having fun learning   
**Tool:** Ansys Zemax OpticStudio (Sequential)

---

## 1. Project Overview & Optical Architecture

This project covers the optical design, performance optimization, and tolerance evaluation of a compact, short-wave infrared (SWIR) catadioptric telescope. The system employs a varifocal architecture with fixed primary/secondary mirrors and internal axial lens groups that translate to achieve three distinct focal lengths.

The compact optical layout is folded to maintain an overall track length under 400 mm while supporting a 200 mm entrance pupil diameter ($F/5$ at $f = 1000\text{ mm}$ to $F/7.5$ at $f = 1500\text{ mm}$).

---

## 2. Optical Specifications

| Parameter | Design Value | Notes / Verification |
| :--- | :--- | :--- |
| **Optical Configuration** | Catadioptric (Folded Mirror + Moving Refractive Groups) | Fixed mirrors, internal zoom motion |
| **Spectral Band** | SWIR (1.0 μm, 1.3 μm, 1.6 μm) | Dispersion control across primary bands |
| **Effective Focal Length (EFL)** | 1000 mm / 1250 mm / 1500 mm | Multi-configuration zoom positions |
| **Entrance Pupil Diameter (EPD)** | 200 mm | Clear aperture |
| **Working F-Number** | $F/5.0$ / $F/6.25$ / $F/7.5$ | Across the three zoom configurations |
| **Total Track Length (OAL)** | < 400 mm | Compact envelope constraint |
| **Secondary Mirror Profile** | Conic Surface | Corrects spherical aberration at primary fold |
| **Detector Format** | 1024 × 1024 pixels | 15 μm pixel pitch |
| **Active Image Height** | ~10.8 – 11.0 mm | Matched to detector sensor format |
| **Evaluation Criterion** | Diffraction-limited across field | Evaluated via MTF and RMS wavefront error |

---

## 3. Optical Layout & Ray Traces

*Optical layout cross-sections and 3D shaded models exported from Zemax OpticStudio.*

<!-- Placeholder for Zemax Layouts -->
> *Figures will be uploaded to `projects/swir-catadioptric-telescope/images/`*
> - 2D Cross-section at EFL = 1000 mm
> - 2D Cross-section at EFL = 1250 mm
> - 2D Cross-section at EFL = 1500 mm

---

## 4. Optical Performance Analysis

### Modulation Transfer Function (MTF)
Polychromatic FFT MTF was evaluated against the diffraction limit out to the Nyquist frequency determined by the 15 μm pixel pitch:

$$\nu_{\text{Nyquist}} = \frac{1}{2 \times 0.015\text{ mm}} \approx 33.3\text{ lp/mm}$$

* Performance maintained diffraction-limited contrast across on-axis and edge-of-field angles across all three configurations.

### Spot Diagrams & Encircled Energy
* RMS spot radius remains bounded within the Airy disk across the field points for 1.0 μm, 1.3 μm, and 1.6 μm wavelengths.

---

## 5. Tolerance Analysis (Monte Carlo)

To assess manufacturability and alignment sensitivity:
* **Analysis Type:** Monte Carlo Simulation
* **Sample Count:** ~1000 runs
* **Perturbations Applied:**
  * Radius of curvature and conic constant tolerances
  * Element center thickness and axial air spaces
  * Surface tilt and decenter tolerances
  * Element tilt and decenter tolerances
  * Refractive index and Abbe number variations
* **Criterion:** RMS wavefront error degradation at operating zoom states.

---

## 6. Engineering Decisions & Lessons Learned

* **Achromatization in SWIR:** Glass selection prioritized materials with high transmission between 1.0 μm and 1.6 μm while mitigating secondary chromatic spectrum without excessive element count.
* **Axial Motion Constraints:** Constraining the moving elements to linear axial translations eliminated complex mechanical cams, maintaining boresight stability between focal lengths.
* **Non-Sequential Verification:** Performed ghost-reflection and stray-light checks to ensure off-axis solar and out-of-field sources do not cause critical sensor irradiance on the 1024 × 1024 array.
