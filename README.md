# Hi, I'm Wisdom Favour Chizoba

**Manufacturing Systems Engineering | Applied AI | Industrial Digitalization**  
*M.Eng. Applied Artificial Intelligence for Digital Production Management — Deggendorf Institute of Technology*
*B.Eng. Industrial Engineering - Deggendorf Institute of Technology*

I architect robust, scalable systems that bridge the gap between legacy industrial processes and advanced AI. My focus is on designing reliable, fail-safe automation pipelines—ensuring that algorithms don't just work in notebooks, but integrate seamlessly into production environments with measurable business impact.

---

## What I Solve (Systems Context)

- **Edge AI & Quality Control:** Designing fault-tolerant computer vision pipelines for real-time defect detection on high-speed production lines.
- **Digital Twins & Simulation:** Building validated simulation environments to test process changes without halting physical operations.
- **Root Cause Automation:** Replacing manual data entry with automated data-driven workflows that compress diagnostic lead times.
- **Predictive Maintenance:** Integrating sensor data streams with ML models, including explicit confidence thresholds and alarm logic to prevent false positives from disrupting operations.

---

## Featured Systems Engineering Projects
*Curated from my full portfolio—demonstrating numerical robustness, hardware-software integration, statistical process control, and simulation-driven optimisation. For the complete project catalogue (20+ applications), visit my [portfolio carousel](https://chizobawisdom.github.io/Portfolio/index_en.html).*

---

### Automation & Tooling
#### [Algorithmic Roots & Polynomial Solvers](https://github.com/Chizobawisdom/Portfolio/tree/8cc2df58c246912ae7be8b3a93641d44c072871d/Utility_and_Automation/polynomial-root-finder)
> **System Context:** Embedded within a suspension system digital twin to replace slow manual Excel calibration. The solver acts as a numerical watchdog to prevent cascading simulation crashes.
> 
> **My Action:** Architected a hybrid numerical kernel—Newton-Raphson with explicit Horner evaluation—paired with a **fail-safe Bisection fallback** when derivatives approach zero. Implemented a time-bounded convergence loop (`maxError = 1e-6`) to guarantee termination.
> 
> **Impact:** Reduced calibration setup time from **3 days to 15 minutes**. Validated against 10,000+ random polynomials with 100% stability (zero simulation freezes) and `<1e-6` precision versus MATLAB benchmarks.

---

### Computer Vision
#### [Vehicle Image Classifier — Two-Stage Fine-Tuning with ResNet50](https://github.com/Chizobawisdom/Portfolio/tree/8cc2df58c246912ae7be8b3a93641d44c072871d/Machine_Vision/vehicle-classification)
> **System Context:** Designed for industrial visual inspection tasks such as part-type recognition or defect class sorting on a production line, requiring high accuracy and controlled overfitting.
> 
> **My Action:** Built a swappable backbone factory (ResNet50/EfficientNet) with a **two-stage training regime**: Stage 1 froze the backbone and trained the head at `1e-3`; Stage 2 unfroze the last 30 layers and fine-tuned at `1e-4` with `ReduceLROnPlateau`. Implemented inline ImageNet normalisation via `tf.data.map()` and a rich augmentation pipeline (flip, rotation, zoom, brightness, contrast).
> 
> **Impact:** Achieved robust test accuracy with a modular architecture that can be retrained on any production defect dataset. Saved model in `.keras` format with a reusable `predict()` inference function for deployment.

---

### Industrial ML & Analytics
#### [Automated Statistical Process Control (SPC) & Quality Capability Engine](https://github.com/Chizobawisdom/Portfolio/tree/8cc2df58c246912ae7be8b3a93641d44c072871d/Industrial_AI_and_Quality_Engineering/continuous-factory-process-control)
> **System Context:** Real-time anomaly detection across multi-channel continuous factory sensor streams. Replaces manual plotting with systemic statistical control limits and process capability reporting.
> 
> **My Action:** Built a pure Python/NumPy engine that computes dynamic subgroup means ($\bar{X}$) and ranges ($R$) using standard control constants ($A_2, D_3, D_4$). Programmed **all 8 Nelson Run Rules**, implemented **CUSUM** and **Page-Hinkley** drift detectors for micro-shift identification, and computed short/long-term capability indices ($C_p, C_{pk}, P_p, P_{pk}$).
> 
> **Impact:** A diagnostic framework that runs across thousands of streaming sensor nodes, automatically generating a master quality dashboard and flagging rule violations *before* defects occur.

#### [Advanced Industrial Defect Reduction Pipeline — FFT + PCA + LightGBM](https://github.com/Chizobawisdom/Portfolio/tree/8cc2df58c246912ae7be8b3a93641d44c072871d/Industrial_AI_and_Quality_Engineering/industrial-defect-classification)
> **System Context:** Diagnosing structural machinery fault types from raw high-frequency spectral signals, plagued by severe class imbalance and the curse of dimensionality.
> 
> **My Action:** Stabilized features with `StandardScaler` and applied **SMOTE** to balance minority fault classes. Isolated FFT columns for targeted **Principal Component Analysis (PCA)**—reducing spectral noise into 10 dense orthogonal components—then horizontally stacked (`np.hstack`) with non-FFT features. Executed a 5-fold `RandomizedSearchCV` over `LGBMClassifier` hyperparameters to optimise non-linear multi-class boundaries.
> 
> **Impact:** Deployed a sub-millisecond anomaly mapping pipeline for predictive maintenance shop‑floors, yielding detailed confusion matrices and multi-class classification reports suitable for production integration.

---

### Digital Twins & Simulation
#### [AnyLogic DES — Industrial Quality Gate Capacity Optimisation](https://github.com/Chizobawisdom/Portfolio/tree/8cc2df58c246912ae7be8b3a93641d44c072871d/Digital_Manufacturing_and_Industry_4.0/inspection-bottlneck-station)
> **System Context:** A bottlenecked manual inspection gate—leadership needed data on whether to hire more inspectors or upgrade equipment speed.
> 
> **My Action:** Built a stochastic DES in AnyLogic (Source → Queue → Service → SelectOutput → Sink) with exponential interarrival ($\lambda = 0.2/\text{min}$) and Triangular service times. Executed **automated Parameter Variation experiments** across multiple scenarios, aggregating metrics across independent replications to compute **95% confidence intervals**.
> 
> **Impact:** Proved that adding a parallel inspector (Scenario A) reduces mean cycle time by **71% (16.02 min → 4.65 min)** and sharply mitigates system volatility near saturation—outperforming a 20% equipment speed upgrade. Validated baseline performance against theoretical $M/G/1$ queueing models.

#### [Discrete-Event Digital Twin — Production Line Balancing & OEE](https://github.com/Chizobawisdom/Portfolio/tree/8cc2df58c246912ae7be8b3a93641d44c072871d/Digital_Manufacturing_and_Industry_4.0/digital-twin-quality-control-line)
> **System Context:** A multi-stage manufacturing line (Cutting, Assembly, Inspection) with unpredictable machine downtime and inspection measurement noise—needed a risk-free virtual testbed for line-balancing decisions.
> 
> **My Action:** Programmed the line in **SimPy** with exponential MTBF/MTTR distributions for non-linear breakdowns. Engineered a closed-loop quality control subsystem evaluating parts against strict $USL$/$LSL$ limits, contaminated with **Gaussian gauge measurement noise** ($\sigma$), and constructed conditional rework routing.
> 
> **Impact:** Deployed a functional simulator generating vital KPIs—First Pass Yield (FPY), scrap rates, hourly throughput, and station-level OEE percentages—enabling rapid virtual testing of reconfiguration strategies without halting physical production.

---

### Full Project Catalogue
*I maintain 20+ projects across four domains. Explore the complete interactive carousel on my portfolio:*  
**[chizobawisdom.github.io/Portfolio](https://chizobawisdom.github.io/Portfolio/inedx_en.html)**

---

## Core Competencies (Systems & Technical)

| **Domain** | **Tools & Technologies** |
| :--- | :--- |
| **Languages & ML** | Python (pandas, scikit-learn, PyTorch), SQL, JavaScript, HTML, CSS |
| **Data & Visualization** | Power BI, matplotlib, KNIME |
| **Low-Code & Integration** | Microsoft Power Platform (Apps, Automate), SAP |
| **Simulation & Modelling** | SimPy, Anylogic, LTSpice |
| **Quality & SE Standards** | 8D, ISO 9001, IATF 16949, APQP, FMEA, Root Cause Analysis |
| **Cloud & Deployment** | Azure (basic), Docker (basic), Git |

---

## My Systems Approach
Every project follows a **V&V-first philosophy**:
- **Explicit Interface Definition:** Ensuring modular components (data ingestion, logic, output) can be swapped without breaking the whole.
- **Benchmark-Driven Validation:** Cross-validating results against industry standards (e.g., MATLAB benchmarks, physical test rigs) before deployment.

---

## Let's Connect

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](www.linkedin.com/in/wisdomfavourchizoba)

*"Turning industrial data into intelligent, reliable systems — bridging engineering and AI for smarter production."*
