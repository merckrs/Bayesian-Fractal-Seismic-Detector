# Non-parametric Detection of Critical Precursors in Non-Equilibrium Systems

> **Official implementation of the paper:** *"Non-parametric Detection of Critical Precursors in Non-Equilibrium Systems via Bayesian-Fractal Energy Ranking"*

## 🔬 Overview

This repository contains the source code, datasets, and simulation scripts for a novel signal processing framework designed to detect **critical phase transitions** in stochastic time series.

While traditional early warning systems rely on amplitude thresholding (which fails in high-noise environments), this project introduces a **Bayesian-Fractal Filter** that identifies a specific low-entropy state termed **"Coiling"** (Locking Phase). This method has been validated on historical seismographic data (1999 Izmit & 2011 Tohoku earthquakes) and synthetic financial crash scenarios.

## 🚀 Key Features

  * **Bayesian-Fractal Fusion:** Combines *Instantaneous Energy Ranking* with *Local Fractal Dimension* (Choppiness Index).
  * **Regime Detection:** Distinguishes between "Stochastic Noise" (Safe) and "Deterministic Locking" (Critical).
  * **Non-Parametric:** Works on any time series (Seismic, Financial, Biological) without assuming a Gaussian distribution.
  * **Pi-Sigma Shock Detector:** Includes a specialized module for detecting "Flash Crashes" that bypass the locking phase.

## 📊 Methodology

The algorithm operates on three sequential layers:

1.  **Energy Ranking ($\hat{R}_t$):** Calculates the kinetic energy of the signal and ranks it against a historical lookback window.
2.  **Structural Filtering ($D_f$):** Measures the *Fractal Dimension* to determine if the system is in a chaotic (safe) or ordered (dangerous) state.
3.  **Recursive Bayesian Update:** A Kalman-like filter that modulates its learning rate based on the structural entropy of the signal.

$$K_t \propto \frac{1}{D_f(t)^2}$$

*(The filter learns aggressively during ordered states and ignores observations during chaotic states.)*

## 📈 Results

### 1\. Seismic Validation (Izmit 1999)

The model successfully identified the **"Seismic Gap"** (Silence of the Coil) weeks before the main rupture.

### 2\. Statistical Significance (N=50 Events)

Tested against 50 randomized seismic events based on USGS catalog characteristics. The model achieved **90% accuracy** in distinguishing locking phases from background noise.

## 🛠️ Installation & Usage

1.  **Clone the repository:**

    ```bash
    git clone https://github.com/your-username/Bayesian-Fractal-Seismic-Detector.git
    cd Bayesian-Fractal-Seismic-Detector
    ```

2.  **Install dependencies:**

    ```bash
    pip install numpy pandas matplotlib seaborn scikit-learn
    ```

3.  **Run the simulation:**

    ```bash
    python main.py
    ```

    *This will generate the plots and the confusion matrix seen in the paper.*

## 📄 Citation

If you use this code or methodology in your research, please cite the following working paper:

```bibtex
@article{KaanBozanlı2025,
  title={Non-parametric Detection of Critical Precursors in Non-Equilibrium Systems via Bayesian-Fractal Energy Ranking},
  author={Kaan, Bozanlı},
  journal={Preprint / GitHub Repository},
  year={2025},
  url={https://github.com/your-username/repo-name}
}
```

## ⚖️ License

This project is licensed under the MIT License - see the [LICENSE](https://www.google.com/search?q=LICENSE) file for details.

-----

*Developed by [Kaan Bozanlı] - 2025*
