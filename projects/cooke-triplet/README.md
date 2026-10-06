# Cooke Triplet Aberration & Optimization Study

**Status:** Completed  
**Role:** Optical Designer  
**Tool:** Ansys Zemax OpticStudio (Sequential Mode)

---

## 1. Design Objective

The objective of this design study was to implement, optimize, and evaluate a classical Cooke triplet objective. The Cooke triplet is the foundational optical form providing sufficient degrees of freedom (six radii, two air spaces, glass selection) to simultaneously correct the primary third-order Seidel aberrations:
* Spherical aberration
* Coma
* Astigmatism
* Field curvature (Petzval sum)
* Distortion
* Axial and lateral chromatic aberrations

---

## 2. System Specifications & Configuration

*Optical parameters evaluated in Zemax OpticStudio:*

| Parameter | Value | Notes |
| :--- | :--- | :--- |
| **Optical Form** | Refractive Triplet (Positive – Negative – Positive) | Crown - Flint - Crown configuration |
| **Spectral Band** | Visible spectrum ($F, d, C$ lines / 0.486, 0.587, 0.656 μm) | Standard visible achromatization |
| **Effective Focal Length (EFL)** | *[Insert EFL, e.g., 50 mm / 100 mm]* | Paraxial focal length |
| **Entrance Pupil Diameter (EPD)** | *[Insert EPD or F-number]* | Working aperture |
| **Stop Location** | Located near central negative element | Symmetry used to control off-axis aberrations |
| **Field of View (FOV)** | *[Insert Semi-FOV, e.g., ±10° to ±20°]* | Evaluated across multiple field heights |

---

## 3. Optical Layout

*Ray trace cross-section showing marginal and chief rays across defined field angles:*

<!-- Placeholder for Zemax Layout Image -->
> *Figures will be uploaded to `projects/cooke-triplet/images/`*
> - 2D Cross-section layout with ray bundles

---

## 4. Optimization Approach

1. **Degrees of Freedom:**
   * Surface curvatures set as variables.
   * Central and rear air spaces set as variables.
   * Glass substitutions explored using common optical crowns and flints (e.g., N-BK7 / N-SF11 or equivalent).

2. **Merit Function Construction:**
   * Default merit function based on RMS wavefront error / RMS spot radius.
   * Target constraints added for focal length, total track length, and edge/center glass thickness boundaries to prevent self-intersection.
   * Targeted boundary conditions to control Petzval curvature without forcing steep, unmanufacturable radii.

---

## 5. Performance Evaluation

* **Spot Diagrams:** Evaluated on-axis, 0.7 field, and full field against the diffraction Airy disk.
* **Transverse Ray Fan Plots:** Examined to identify residual higher-order spherical and oblique spherical aberrations.
* **Field Curvature & Distortion:** Analyzed grid distortion and astigmatic field curves ($S$ and $T$).

---

## 6. Engineering Takeaways & Lessons Learned

* **Achromatization vs. Field Curvature:** Controlling chromatic aberration requires power balance between the crown and flint elements, which directly interacts with the Petzval sum contribution.
* **Stop Placement Sensitivity:** Moving the aperture stop relative to the negative element significantly shifts the balance between coma and astigmatism.
* **Limitations of the Form:** While effective for moderate apertures and fields, scaling to faster speeds or wider fields requires splitting elements into forms such as the Double Gauss or Tessar.
