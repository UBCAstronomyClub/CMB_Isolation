# 🌌 CMB Foreground Separation Workshop

**Learn how cosmologists extract the Cosmic Microwave Background from contaminated telescope observations using Bayesian methods.**

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/UBCAstronomyClub/CMB_Isolation/blob/main/cmb_mcmc_workshop.ipynb)

---

## Overview

The **Cosmic Microwave Background (CMB)** is the oldest light in the universe — released just 380,000 years after the Big Bang. It contains invaluable information about the early universe, but when we observe it, we also see contaminating emission from our own Milky Way galaxy.

In this workshop, you'll learn how astronomers separate the CMB from galactic "foregrounds" using **Monte Carlo methods** and **Bayesian inference** — the same techniques used by real experiments like the Planck satellite.

### The Challenge

When a telescope observes the microwave sky, it sees a mixture of:

| Component | Origin | Frequency Behavior |
|-----------|--------|-------------------|
| **CMB** | The early universe (13.8 billion years ago) | Constant at all frequencies |
| **Synchrotron** | Electrons in galactic magnetic fields | Brighter at low frequencies |
| **Thermal Dust** | Warm dust grains in our galaxy | Brighter at high frequencies |

The key insight: **each component has a unique spectral signature**. By observing at multiple frequencies, we can mathematically separate them!

### Our Approach

We use a two-stage hybrid method:

1. **MCMC on a single pixel** → Learn the synchrotron spectral index and get uncertainties
2. **Linear algebra on all pixels** → Fast reconstruction using the learned parameters

This gives us the best of both worlds: Bayesian uncertainty quantification AND computational efficiency.

---

## What You'll Learn

### Physics Concepts
-  What the CMB is and why it matters for cosmology
-  How synchrotron radiation and thermal dust emission work
-  Why do different components have different spectral signatures
-  The mathematics of component separation

### Computational Methods
-  Building a parametric forward model
-  Likelihood functions and chi-squared fitting
-  Bayesian inference with priors and posteriors
-  Markov Chain Monte Carlo (MCMC) sampling
-  Linear least squares for fast map reconstruction

### Python Skills
- Working with NumPy arrays
- Creating visualizations with Matplotlib
- Implementing scientific algorithms from scratch
- Analyzing and interpreting MCMC results

---

## Getting Started

### Prerequisites

- Basic Python knowledge (variables, functions, loops)
- Some familiarity with physics or astronomy (helpful but not required)
- A Google account (for Google Colab)

### Setup Instructions

#### Option 1: Google Colab (Recommended)

The easiest way to run this workshop — no installation required!

1. **Download the notebook** from this repository:
   - Click on `cmb_mcmc_workshop.ipynb`
   - Click the "Download" button (or Raw → Save As)

2. **Open Google Colab**:
   - Go to [colab.research.google.com](https://colab.research.google.com)

3. **Upload the notebook**:
   - Click `File → Upload notebook`
   - Select the downloaded `.ipynb` file

4. **Save a copy to your Drive**:
   - Click `File → Save a copy in Drive`
   - This ensures your work is saved!

5. **Run the cells**:
   - Press `Shift + Enter` to run each cell
   - Or use `Runtime → Run all` to run everything

#### Option 2: Local Installation

If you prefer to run locally:

```bash
# Clone the repository
git clone https://github.com/UBCAstronomyClub/CMB_Isolation.git
cd CMB_Isolation

# Create a virtual environment (optional but recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install numpy matplotlib tqdm jupyter

# Launch Jupyter
jupyter notebook cmb_mcmc_workshop.ipynb
```

---

## Repository Contents

```
├── README.md                        # This file
├── cmb_workshop_montecarlo.ipynb    # Main workshop notebook 
└── cmb_workshop_solutions.ipynb     # Solutions notebook (added after the workshop)
```

---

## Example Results

After completing the workshop, you'll produce results like these:

### Posterior Distributions
The MCMC sampler recovers the true parameter values with well-defined uncertainties:

- CMB amplitude: accurately recovered
- Synchrotron spectral index: β_s ≈ -3.0 ± 0.1
- Component amplitudes: within 1-2σ of true values

### CMB Map Recovery
- Correlation with true CMB: > 99%
- Variance explained: > 95%
- Residuals consistent with noise level

---

## Further Reading

### CMB and Cosmology
- [Planck Mission Overview](https://www.esa.int/Science_Exploration/Space_Science/Planck)
- [CMB Introduction (Wayne Hu)](http://background.uchicago.edu/~whu/beginners/introduction.html)

### Component Separation Methods
- [Planck 2018 Component Separation Paper](https://arxiv.org/abs/1807.06208)
- [BeyondPlanck: End-to-end Bayesian analysis](https://arxiv.org/abs/2011.05609)

### MCMC and Bayesian Methods
- [Practical MCMC (Hogg & Foreman-Mackey)](https://arxiv.org/abs/1710.06068)
- [emcee: The MCMC Hammer](https://emcee.readthedocs.io/)

### Alternate Component Separation Methods for Isolating CMB
- [LAMBDA](https://lambda.gsfc.nasa.gov/toolbox/comp_separation.html)

---

## License

This workshop is released under the MIT License. Feel free to use, modify, and distribute for educational purposes.

---

## Acknowledgments

This workshop was developed for astronomy education. The methods presented are simplified versions of techniques used by real CMB experiments, including Planck, WMAP, and upcoming projects like CMB-S4 and LiteBIRD.

---

## Questions or Issues?

If you encounter any problems or have suggestions for improvement:
- Open an issue on this repository
- Contact: [your email or contact info]

**Happy exploring the early universe! **
