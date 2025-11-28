# Statistical Power Analysis & Sample Size Determination

![R](https://img.shields.io/badge/Language-R-blue)
![Stats](https://img.shields.io/badge/Domain-Statistical%20Inference-lightgrey)
![Status](https://img.shields.io/badge/Status-Completed-success)

> **Implementation of Whitehead's (1983) unified theory for optimizing sample sizes in clinical trials.**

## 📄 Project Overview
In clinical trial design, determining the correct sample size is critical to minimize cost while ensuring statistical significance. This project implements a **Power Analysis** framework to determine the necessary sample size ($\ n \ $) to detect a deviation from a baseline probability ($p_0 = 0.003$) with a specific statistical power ($1 - \beta = 0.80$).

The project involves manual mathematical derivation (LaTeX) of Log-Likelihood functions and the implementation of simulation algorithms in **R** to validate theoretical approximations against empirical results.

## Methodology & Key Features

The analysis follows a rigorous statistical workflow:

* **Mathematical Derivation:** Derived the Fisher Information ($\mathcal{I}$) and Score Statistics ($Z$) for Binomial distributions from first principles.
* **Whitehead’s Method:** Applied Whitehead's formula to calculate sample sizes based on Type I error ($\alpha = 0.025$) and Power ($0.80$).
* **Hypothesis Testing:**
    * **Parametric:** Chi-Square Test (`chisq.test`) and Exact Binomial Test (`binom.test`).
    * **Non-Parametric:** Wilcoxon Rank-Sum Test (implemented to handle cases where parametric assumptions fail).
* **Simulation:** Generated Monte Carlo simulations (using `rbinom`) to verify the theoretical error rates against observed data.

## Tech Stack
* **Language:** R (Base R, Stats)
* **Reporting:** R Markdown (Knitr, LaTeX)
* **Statistical Techniques:** Maximum Likelihood Estimation (MLE), Wald Test, Score Test.

## Statistical "Decisions"
* **Exact vs. Asymptotic:** While the Score Test (Asymptotic) is computationally efficient, we implemented the **Exact Binomial Test** for validation. This confirmed that for small probabilities ($p=0.003$), the asymptotic approximations hold only when $n$ is sufficiently large.
* **Handling Non-Normality:** To ensure robustness, I explored the **Wilcoxon Rank-Sum Test** as an alternative when the assumption of normality in the residuals (or the binomial approximation to normal) was questionable.

## Installation & Usage

1.  **Clone the repo:**
    ```bash
    git clone [https://github.com/yourusername/statistical-power-analysis.git](https://github.com/yourusername/statistical-power-analysis.git)
    ```
2.  **Open the Project:**
    Open `power_sample_size_analysis.Rmd` in **RStudio**.
3.  **Run the Analysis:**
    Click the **Knit** button in RStudio to generate the full PDF report with LaTeX equations rendered.

## Authors
* **Gonzalo Cruz Gómez**
* **Daniel Fernández Magariños**

---
*Based on the statistical framework proposed by Whitehead, J., & Stratton, I. (1983).*
