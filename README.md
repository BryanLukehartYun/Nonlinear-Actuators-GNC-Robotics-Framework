## Pneumatic Artificial Muscle Nonlinear Dynamics Analysis
**Nonlinear GNC framework for Pneumatic Artificial Muscles (PAMs). Features NLARX system identification (Sigmoid, Wavelet, idTreePartition) and robust state estimation (Kalman Filters) designed to reject complex hysteresis-induced bias and non-differentiable gradient spikes. Also contains Monte Carlo regarding Unscented Kalman Filter and Model Predictive Control.** 

**Preface**: Traditional industry estimators (EKF/CKF) and controls fail to estimate/ predict soft-actuator dynamics due to inherent nonlinear hysteresis and non-differentiable gradient spikes. This repository contains a high-performance skeleton of the Guidance, Navigation, and Control (GNC) framework for stable open-loop modeling and closed-loop control of McKibben Artifical Muscles. Three reports demonstrates a full-stack engineering pipeline: from identifying non-differentiable plant dynamics to implementing derivative-free state estimation and nonlinear model predictive control over nonlinear hysteretic actuators.


## Technical Highlights & Results 
* Model Fidelity - Achieved a 98.2% fitness match using Sigmoid-NLARX models, significantly outperforming standard linear approximations in capturing hysteresis drift inherent to soft actuators, and stable for driving NMPC optimization. 
* Derivative-Free Estimation: Implements an **Unscented Kalman Filter** to bypass massive Jacobian spikes (+400 to -1100) that casues standard EKF linearization to fail. Validated robustness by using Monte Carlo simulations. 
* NMPC Performance: Achieves a 75.6% reduction in trackign error compared to baseline PID controllers in high-nonlinearity environments. 

## Project Architecture & Reports
| Module | Technical Focus | Key Metric |
| :--- | :--- | :--- |
| **[01-NLARX-SysID](./01-NLARX-SysID-Estimation/)** | **Nonlinear System ID** | **98.2% Sigmoid Fitness** |
| **[02-Monte-Carlo-KalmanFilter](./02-Monte-Carlo-KalmanFilter/)** | **State Estimation** | **Validate Robustness of Sigmoid-NLARX and UKF** |
| **[03-Nonlinear-MPC](./03-Nonlinear-MPC/)** | **Optimal Control** | **1.36 mm Tracking RMSE** |

## Institutional Context & Academic Foundation | Technical Expansion
This framework represents the **technical expansion and demonstration** of research established within the **BioSEL Lab** at the **Rochester Institute of Technology (RIT)**.

* **Academic Anchor**: Builds upon principles validated in my thesis and bridge the gap between Academia and the industry.  
* **Thesis Title**: *Stable Open-Loop Modelling of McKibben Muscle with Tunable
Slider*.
* **Certification**: Master of Science in Mechanical Engineering (Date: August 2022 - December 2025). 
* **Abstract & Metadata** Formal Abstract and institutional metadata available via [RIT Digital Commons - Thesis](https://repository.rit.edu/theses/12372/)
* **Status & Notice**: The M.S. Thesis with full-scale research (data, derivations, and analysis) are currently under embargo pending publications in *IEEE T-RO*, *IJRR*, and *Data in Brief*

For further information pertaining the research related to thesis under RIT, please reach out to the following authors: 
* Primary Author: Bryan Lukehart-Yun @ wwy6929@rit.edu pertaining to research collaboration or thesis. For clarification, refer to the table below if related to professional interest.  
* **Principal Investigator**: Dr. Kathleen Lamkin-Kennard, Supervisor of the M.S. Thesis, @ kaleme@rit.edu pertaining to BioSEL Lab activities and further collaboration. 

| Inquiry Type | Point of Contact | Action |
| :--- | :--- | :--- |
| **Recruitment & Professional** | Bryan Lukehart-Yun | [Email bryan.lukehartyun@gmail.com](mailto:bryan.lukehartyun@gmail.com) |
| **Technical & Repository Help** | Bryan Lukehart-Yun | Open a GitHub Issue |
| **BioSEL Lab & Research Collaboration** | Dr. Kathleen Lamkin-Kennard | [View RIT Faculty Profile](https://www.rit.edu/directory/kaleme-kathleen-lamkin-kennard) |


## **Roadmap**
This repository is organized into three distinct technical reports that follows **Input $\rightarrow$ Evidence $\rightarrow$ Decision framework**. This functionally amounts to a **Guidance, Navigation, and Control (GNC)** stack-equivalent. 

1. **01-NLARX-SysID-Estimation**: Comparison of different models (NLARX models vs different Kalman Filters) and rejection of Extended Kalman Filter (EKF) and Cubature Kalman Filter (CKF) in favor of Unscented Kalman Filter

2. **02-Monte-Carlo-KalmanFilter**: (Done - Further Finetuning) Statistical verification of estimator robustness across randomized initial conditions. Note source code for driving this part is still WIP for git commits. 

3. **03-Nonlinear-MPC**: (Done - Further Finetuning) Real-Time Tracking of Fourier-series references using the NLARX PLant Models for Model Predictive Controls. Note source code for driving this part is still WIP for git commits. 

4. **04-GNC-Integration**: (Planned). Integrate and expand all three scripts into a single real-time NMPC + UHKF estimator solution backed by Monte Carlo Simualtions. 

5. **Notice**: Future works may expand or extend the reports here for publications (not limited to the aforementioned journals). This repository is intended to validate and serve as a sample of the work that can be extended to the Industry. 

## **Licensing & Intellectual Property**

This project utilizes a **dual-licensing framework** to distinguish between functional software and technical research analysis:

* **Software & Scripts**: All MATLAB source code (.m) and supporting functions are provided under the **MIT License**.

* **Technical Analysis**: The reports, unique figure interpretations, and design-decision narratives contained in the README files are copyright © 2026 Bryan Lukehart-Yun and licensed under **CC BY-NC-ND 4.0**. 

* **Data Attribution**: The provided 10,000-sample dataset containing multiple permutations (.mat) is a series of randomized, non-representative slices **intended for architectural demonstration**.
Full high-fidelity datasets (15M+ samples) and theoretical derivations are reserved for upcoming publications in T-RO, IJRR, and Data In Brief. Those were collected during graduate research at RIT. 

* **Future Release** The complete 15-million-sample global dataset will be published via Data in Brief; this repository will be updated with the public access links upon release. 

**Citation**: If you utilize this GNC framework or the UKF bias-rejection analysis in your work, please attribute it to this repository or the forthcoming Zenodo DOI. **In the Future, a list of publications will be listed here for future citations to use instead.**

**TL;DR: The MATLAB Code is open-source (MIT License), while the Technical Reports, Analysis, and Figures are protected intellectual property (CC BY-NC-ND 4.0).**