# Welcome {.unnumbered}

::: {.callout-note}
## About This Tutorial

This is a comprehensive, hands-on tutorial series for understanding and applying multivariate information theory to neuroscience and complex systems. We build from foundational concepts to complete analysis pipelines using state-of-the-art Python packages.
:::

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
git clone https://github.com/yourusername/multivariate-information-theory-tutorial.git
cd multivariate-information-theory-tutorial
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
@misc{petri2024multivariate,
  author = {Petri, Giovanni},
  title = {Multivariate Information Theory: A Practical Tutorial},
  year = {2024},
  publisher = {GitHub},
  url = {https://github.com/yourusername/multivariate-information-theory-tutorial}
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
