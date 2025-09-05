# 📊 Confidence Interval Calculator with Interactive Visualizations

A comprehensive Python toolkit for calculating and visualizing confidence intervals across multiple statistical scenarios. This interactive CLI application provides accurate statistical computations with intuitive plots for better data interpretation.

![Python](https://img.shields.io/badge/Python-3.7+-blue.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)
![Status](https://img.shields.io/badge/Status-Active-brightgreen.svg)

## 🎯 Overview

The Confidence Interval Calculator is designed for students, researchers, and data analysts who need quick, accurate statistical analysis with visual insights. It handles multiple types of confidence intervals and provides both numerical results and publication-ready visualizations.

### Key Features

- **Interactive CLI Interface** - User-friendly command-line experience
- **Multiple CI Types** - Comprehensive coverage of common statistical scenarios
- **Automatic Visualizations** - Clean, interpretable plots for each analysis
- **Flexible Input** - Accepts raw data or summary statistics
- **Export Capabilities** - Save results to CSV for reproducibility
- **Dashboard View** - Compare multiple confidence intervals side-by-side

## 🚀 Quick Start

### Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/confidence-interval-calculator.git
cd confidence-interval-calculator

# Install required packages
pip install numpy scipy pandas matplotlib
```

### Basic Usage

```bash
python ci_calculator.py
```

Follow the interactive prompts to:
1. Select your confidence interval type
2. Enter your data or statistics
3. Set confidence level (e.g., 0.95 for 95%)
4. View results and visualizations
5. Export or compare multiple analyses

## 📈 Supported Confidence Intervals

### 1. One-Sample Mean

**When to use:** Estimating the population mean from a single sample

**Z-Interval (σ known):**
```
CI = x̄ ± z_{α/2} × (σ/√n)
```

**T-Interval (σ unknown):**
```
CI = x̄ ± t_{α/2,n-1} × (s/√n)
```

**Required inputs:**
- Sample data OR (sample mean, sample size, standard deviation/population σ)
- Confidence level

**Example output:**
```
CI: (10.245, 12.755)
With 95.0% confidence, the true mean lies between 10.245 and 12.755.
```

### 2. Population Variance/Standard Deviation

**When to use:** Estimating population variability

**Chi-Square Interval:**
```
Variance: [(n-1)s²/χ²_{α/2,n-1}, (n-1)s²/χ²_{1-α/2,n-1}]
Std Dev: [√(lower_var), √(upper_var)]
```

**Required inputs:**
- Sample data OR (sample standard deviation, sample size)
- Confidence level

### 3. Population Proportion

**When to use:** Estimating success rate, percentage, or probability

**Wald Interval (Normal Approximation):**
```
CI = p̂ ± z_{α/2} × √(p̂(1-p̂)/n)
```

**Required inputs:**
- Number of successes
- Total sample size
- Confidence level

**Note:** Valid when np̂ ≥ 5 and n(1-p̂) ≥ 5

### 4. Two-Sample Mean Comparison

**When to use:** Comparing means between two independent groups

**Equal Variances (Pooled t-test):**
```
CI = (x̄₁ - x̄₂) ± t_{α/2,n₁+n₂-2} × sp√(1/n₁ + 1/n₂)
where sp² = [(n₁-1)s₁² + (n₂-1)s₂²]/(n₁+n₂-2)
```

**Unequal Variances (Welch's t-test):**
```
CI = (x̄₁ - x̄₂) ± t_{α/2,df} × √(s₁²/n₁ + s₂²/n₂)
where df = (s₁²/n₁ + s₂²/n₂)² / [(s₁²/n₁)²/(n₁-1) + (s₂²/n₂)²/(n₂-1)]
```

**Required inputs:**
- Two independent samples
- Assumption about equal variances
- Confidence level

### 5. Paired Sample Comparison

**When to use:** Comparing before/after measurements or matched pairs

**Paired t-Interval:**
```
CI = d̄ ± t_{α/2,n-1} × (sd/√n)
where d̄ = mean difference, sd = standard deviation of differences
```

**Required inputs:**
- Two paired samples (same length)
- Confidence level

## 🎨 Visualizations

### Individual Plots

1. **Histogram with CI Overlay** - For one-sample mean and variance intervals
2. **Bar Plot with Error Bars** - For proportions and two-sample comparisons  
3. **Difference Distribution** - For paired sample analysis

### Dashboard View

Compare multiple confidence intervals in a single plot with horizontal error bars, perfect for:
- Comparing different methods on the same data
- Showing results from multiple experiments
- Creating publication-ready comparison figures

## 📊 Example Workflow

```python
# Example: One-sample t-interval
data = [12.1, 11.8, 12.3, 11.9, 12.0, 12.2, 11.7, 12.4]
lower, upper, interpretation, mean = t_confidence_interval(data, confidence=0.95)

print(f"Mean: {mean:.3f}")
print(f"95% CI: ({lower:.3f}, {upper:.3f})")
print(interpretation)
# Output: With 95.0% confidence, the true mean lies between 11.814 and 12.286.
```

## 📁 Output Options

### Console Output
- Numerical confidence interval bounds
- Point estimates
- Statistical interpretation
- Method used (z, t, χ², etc.)

### Visual Output
- Automatic plots for each analysis
- Customizable titles and labels
- Professional styling for presentations

### Data Export
- CSV export of all calculated intervals
- Includes CI type, bounds, and interpretations
- Perfect for documentation and reporting

## 🔧 Technical Details

### Dependencies
- `numpy` - Numerical computations
- `scipy.stats` - Statistical distributions and tests
- `pandas` - Data manipulation and export
- `matplotlib` - Plotting and visualization

### Statistical Methods
- **Robust calculations** using scipy's statistical functions
- **Appropriate test selection** based on data characteristics
- **Assumption checking** prompts for user guidance
- **Edge case handling** for boundary conditions

### Error Handling
- Input validation for numerical data
- Sample size requirements checking  
- Confidence level bounds validation
- Graceful handling of invalid inputs

## 📚 Educational Value

This tool is excellent for:
- **Statistics courses** - Visual learning of CI concepts
- **Research training** - Hands-on practice with real data
- **Data analysis workshops** - Quick, reliable calculations
- **Self-study** - Interactive exploration of statistical methods

## 🤝 Contributing

We welcome contributions! Areas for improvement:
- Additional CI types (bootstrap, Bayesian intervals)
- Enhanced visualizations
- Web interface development
- Performance optimizations
- Additional statistical tests


## 🔗 References

- Casella, G., & Berger, R. L. (2002). Statistical Inference (2nd ed.)
- Montgomery, D. C., & Runger, G. C. (2018). Applied Statistics and Probability for Engineers
- Rice, J. A. (2006). Mathematical Statistics and Data Analysis

## 📧 Contact

For questions, suggestions, or collaborations, please open an issue or reach out via [your-pranavdabholkar11124.com](mailto:your-pranavdabholkar11124@gmail.com).

---

**Happy Statistical Analysis! 📊✨**
