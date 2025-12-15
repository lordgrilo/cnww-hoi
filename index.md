# Welcome {.unnumbered}

::: {.callout-note}
## About This Tutorial

This is a comprehensive, hands-on tutorial series for understanding and applying multivariate information theory to neuroscience and complex systems. We build from foundational concepts to complete analysis pipelines using three state-of-the-art Python packages: **HOI**, **Frites**, and **XGI**.
:::

## Featured Packages

This tutorial teaches you to use three powerful open-source Python packages for information-theoretic analysis:

::: {.grid}

::: {.g-col-12 .g-col-md-4}
### HOI
**Higher-Order Interactions**

[![HOI](https://img.shields.io/badge/Docs-brainets.github.io/hoi-blue?style=for-the-badge)](https://brainets.github.io/hoi/)
[![GitHub](https://img.shields.io/badge/GitHub-brainets/hoi-181717?style=for-the-badge&logo=github)](https://github.com/brainets/hoi)
[![PyPI](https://img.shields.io/pypi/v/hoi?style=for-the-badge&logo=pypi&logoColor=white)](https://pypi.org/project/hoi/)

Fast computation of O-information, S-information, and Partial Information Decomposition. Built on JAX for CPU/GPU acceleration.

**Key Features:**
- Synergy & redundancy detection
- Multiple entropy estimators
- GPU acceleration
- Scikit-learn-style API

:::

::: {.g-col-12 .g-col-md-4}
### Frites
**Framework for Information Theoretical analysis**

[![Frites](https://img.shields.io/badge/Docs-brainets.github.io/frites-green?style=for-the-badge)](https://brainets.github.io/frites/)
[![GitHub](https://img.shields.io/badge/GitHub-brainets/frites-181717?style=for-the-badge&logo=github)](https://github.com/brainets/frites)
[![PyPI](https://img.shields.io/pypi/v/frites?style=for-the-badge&logo=pypi&logoColor=white)](https://pypi.org/project/frites/)

Time-resolved mutual information analysis for M/EEG and intracranial neural data with rigorous statistical testing.

**Key Features:**
- Dynamic functional connectivity
- Permutation-based statistics
- Cluster correction
- MNE-Python integration

:::

::: {.g-col-12 .g-col-md-4}
### XGI
**CompleX Group Interactions**

[![XGI](https://img.shields.io/badge/Docs-xgi.readthedocs.io-orange?style=for-the-badge)](https://xgi.readthedocs.io/)
[![GitHub](https://img.shields.io/badge/GitHub-xgi--org/xgi-181717?style=for-the-badge&logo=github)](https://github.com/xgi-org/xgi)
[![PyPI](https://img.shields.io/pypi/v/xgi?style=for-the-badge&logo=pypi&logoColor=white)](https://pypi.org/project/xgi/)

Hypergraph and simplicial complex analysis for representing higher-order network structures.

**Key Features:**
- Hypergraph data structures
- Network algorithms
- Beautiful visualizations
- 40+ real-world datasets

:::

:::

::: {.callout-tip}
## Published Research

All three packages are peer-reviewed and published in the **Journal of Open Source Software (JOSS)**:

- **HOI**: [Neri et al. (2024)](https://doi.org/10.21105/joss.07360)
- **Frites**: [Combrisson et al. (2022)](https://doi.org/10.21105/joss.03842)
- **XGI**: [Landry et al. (2023)](https://doi.org/10.21105/joss.05162)

:::

## Why These Packages?

We've carefully selected **HOI**, **Frites**, and **XGI** as the foundation for this tutorial:

**🔬 Cutting-Edge Methods**: All three implement the latest published research in information theory and network science, maintained by active research groups.

**🤝 Complementary Strengths**:
- **HOI** excels at detecting synergy and redundancy in static data
- **Frites** specializes in time-resolved analysis with rigorous statistics  
- **XGI** provides the perfect representation for higher-order structures

**📚 Well-Documented**: Each has extensive documentation, examples, and active community support.

**🚀 Production-Ready**: Used in published neuroscience research and actively maintained with regular updates.

**🆓 Open Source**: All three are BSD-licensed and freely available.

## What You'll Learn

Over six progressive notebooks, you'll master:

- **Information theory fundamentals** - From entropy to mutual information
- **Higher-order interactions** - Synergy, redundancy, and the famous XOR problem
- **Professional tools** - HOI, Frites, and XGI packages for real-world analysis
- **Time-resolved analysis** - Dynamic information flow in neural systems
- **Network representations** - Hypergraphs for higher-order structures
- **Complete pipelines** - End-to-end analysis workflows

## Who Is This For?

This tutorial is designed for:

- **Neuroscience researchers** analyzing neural population data
- **Network scientists** studying higher-order interactions
- **Complex systems researchers** exploring emergent phenomena
- **Graduate students** learning information-theoretic methods
- **Computational biologists** working with multivariate dependencies
- **Machine learning practitioners** interested in feature interactions

### Prerequisites

- **Programming**: Intermediate Python (NumPy, Matplotlib)
- **Mathematics**: Basic probability theory, linear algebra
- **Statistics**: Understanding of hypothesis testing helpful but not required
- **Domain knowledge**: Neuroscience background helpful but not essential

## Tutorial Structure

### Part I: Foundations (Notebooks 1-2)

Build solid understanding of information theory and discover why pairwise analysis fails for higher-order phenomena.

**Time commitment**: 4-6 hours

### Part II: Advanced Tools (Notebooks 3-5)

Learn three powerful Python packages for analyzing multivariate information in different contexts.

**Time commitment**: 6-8 hours

### Part III: Integration (Notebook 6)

Synthesize everything into a complete analysis pipeline tackling a realistic neuroscience question.

**Time commitment**: 3-4 hours

## Key Features

::: {.grid}

::: {.g-col-6}
### 🎓 Progressive Learning
Each notebook builds on previous ones, with clear learning objectives and prerequisites.
:::

::: {.g-col-6}
### 💻 Hands-On Code
All concepts implemented from scratch before using professional tools.
:::

::: {.g-col-6}
### 🔬 Real Applications
Examples and exercises based on actual neuroscience research scenarios.
:::

::: {.g-col-6}
### 📊 Rich Visualizations
Extensive plotting to build intuition for abstract information-theoretic concepts.
:::

:::

## Getting Started

### Quick Start

1. Clone the repository:
```bash
git clone https://github.com/lordgrilo/cnww-hoi.git
cd cnww-hoi
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Launch Jupyter:
```bash
jupyter notebook
```

4. Start with [Notebook 1](01_information_theory_foundations.ipynb)

### Reading This Book

You can use this tutorial in several ways:

- **Complete course**: Work through all six notebooks sequentially (recommended for learners)
- **Tool reference**: Jump to specific notebooks for package documentation (Notebooks 3-5)
- **Research template**: Adapt the complete pipeline (Notebook 6) to your data
- **Teaching resource**: Use notebooks for workshops or courses

## Online Resources

- **GitHub Repository**: [Link to code and issues](https://github.com/yourusername/repo)
- **Package Documentation**: 
  - [HOI](https://hoi.readthedocs.io/)
  - [Frites](https://brainets.github.io/frites/)
  - [XGI](https://xgi.readthedocs.io/)

## Citation

If you use these tutorials in your research or teaching, please cite:

```bibtex
@misc{petri2025multivariate,
  author = {Petri, Giovanni},
  title = {Multivariate Information Theory: A Practical Tutorial},
  year = {2025},
  publisher = {GitHub},
  url = {https://github.com/lordgrilo/cnww-hoi}
}
```

## License

This work is licensed under the MIT License. See [LICENSE](LICENSE) for details.

## Acknowledgments

This tutorial integrates three excellent open-source packages:

- **HOI** by Etienne Combrisson and team
- **Frites** by Etienne Combrisson and team  
- **XGI** by the Comple(X) Group Interactions team

Special thanks to the network science and computational neuroscience communities for developing the theoretical foundations these tools implement.

---

::: {.callout-tip}
## Ready to Start?

Begin your journey with [Notebook 1: Information Theory Foundations](01_information_theory_foundations.ipynb) where we build the mathematical groundwork from scratch.
:::

## Quick Links

### Package Documentation

::: {.grid}

::: {.g-col-12 .g-col-md-4}
#### HOI Resources
- [📖 Documentation](https://brainets.github.io/hoi/)
- [💻 GitHub Repository](https://github.com/brainets/hoi)
- [📦 PyPI Package](https://pypi.org/project/hoi/)
- [📄 JOSS Paper](https://doi.org/10.21105/joss.07360)
:::

::: {.g-col-12 .g-col-md-4}
#### Frites Resources
- [📖 Documentation](https://brainets.github.io/frites/)
- [💻 GitHub Repository](https://github.com/brainets/frites)
- [📦 PyPI Package](https://pypi.org/project/frites/)
- [📄 JOSS Paper](https://doi.org/10.21105/joss.03842)
:::

::: {.g-col-12 .g-col-md-4}
#### XGI Resources
- [📖 Documentation](https://xgi.readthedocs.io/)
- [💻 GitHub Repository](https://github.com/xgi-org/xgi)
- [📦 PyPI Package](https://pypi.org/project/xgi/)
- [📄 JOSS Paper](https://doi.org/10.21105/joss.05162)
:::

:::

### Tutorial Notebooks

| Notebook | Topic | Package |
|----------|-------|---------|
| [Notebook 1](01_information_theory_foundations.ipynb) | Information Theory Foundations | None (from scratch) |
| [Notebook 2](02_xor_problem_synergy.ipynb) | The XOR Problem & Synergy | None (from scratch) |
| [Notebook 3](03_hoi_higher_order_interactions.ipynb) | Higher-Order Interactions | **HOI** |
| [Notebook 4](04_frites_neural_timeseries.ipynb) | Neural Time Series Analysis | **Frites** |
| [Notebook 5](05_xgi_hypergraph_networks.ipynb) | Hypergraph Networks | **XGI** |
| [Notebook 6](06_complete_integration.ipynb) | Complete Integration | **HOI + Frites + XGI** |

### Support & Community

- **🐛 Report Issues**: Use each package's GitHub Issues page
- **💬 Discussions**: GitHub Discussions for questions
- **🐦 Social Media**: Follow [@kNearNeighbors](https://twitter.com/kNearNeighbors) (Frites/HOI) and [@xginets](https://twitter.com/xginets) (XGI)
- **📧 Mailing Lists**: Sign up on respective package websites
