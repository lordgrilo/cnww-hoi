# Book Format Recommendations: Quarto vs JupyterBook

## TL;DR Recommendation

**Use Quarto** for this project. Here's why:

1. **Better PDF output** with superior LaTeX integration for your mathematical content
2. **More flexible cross-format publishing** (web, PDF, DOCX simultaneously)
3. **Modern tooling** with active development and growing ecosystem
4. **Easier integration** with non-notebook content (regular markdown)
5. **Better handling of complex mathematics** and scientific notation

## Detailed Analysis

### Your Project Characteristics

Your tutorial series has specific needs:
- ✅ Heavy mathematical content (entropy, mutual information, PID equations)
- ✅ Progressive structure (6 notebooks building on each other)
- ✅ Code + explanation integration
- ✅ Rich visualizations throughout
- ✅ Potential for academic publication/citation
- ✅ Cross-references between notebooks essential
- ✅ Multiple output formats likely needed (web, PDF for offline)

### Quarto Advantages for Your Use Case

#### 1. **Superior Mathematics Rendering**
```yaml
# Quarto handles LaTeX beautifully in all formats
format:
  html:
    html-math-method: mathjax
  pdf:
    pdf-engine: pdflatex
```

Your notebooks have complex equations like:
- $H(X) = -\sum_{i=1}^{n} P(x_i) \log_2 P(x_i)$
- $I(X;Y) = H(X) + H(Y) - H(X,Y)$
- Partial Information Decomposition formulas

Quarto renders these consistently across web and PDF, while JupyterBook sometimes struggles with PDF math.

#### 2. **Multi-Format Publishing**
```bash
# Single command generates all formats
quarto render --to html
quarto render --to pdf
quarto render --to docx
```

For academic work, you might want:
- **HTML** for interactive web access
- **PDF** for printing and distribution
- **DOCX** for sharing with collaborators

Quarto handles all three cleanly from the same source.

#### 3. **Better Book Organization**
```yaml
# _quarto.yml structure
project:
  type: book

book:
  title: "Multivariate Information Theory"
  author: "Giovanni Petri"
  chapters:
    - index.qmd
    - part: "Foundations"
      chapters:
        - 01_information_theory_foundations.ipynb
        - 02_xor_problem_synergy.ipynb
    - part: "Tools"
      chapters:
        - 03_hoi_higher_order_interactions.ipynb
        - 04_frites_neural_timeseries.ipynb
        - 05_xgi_hypergraph_networks.ipynb
    - part: "Integration"
      chapters:
        - 06_complete_integration.ipynb
    - references.qmd
```

Natural book structure with parts and cross-references.

#### 4. **Code Execution Control**
```yaml
execute:
  freeze: auto  # Only re-run changed notebooks
  cache: true   # Cache expensive computations
```

Your notebooks have computationally intensive cells (HOI calculations, permutation testing). Quarto's `freeze` feature means you render once, then only re-execute when you edit.

#### 5. **Citations and Bibliography**
```yaml
bibliography: references.bib
csl: nature-neuroscience.csl
```

Built-in Pandoc citation processing for academic work.

#### 6. **Modern Web Features**
```yaml
format:
  html:
    code-fold: true        # Collapsible code blocks
    code-tools: true       # Download full code
    number-sections: true  # Auto-numbering
    theme: cosmo
    toc: true
```

Better control over interactive features for web version.

### JupyterBook Advantages

JupyterBook isn't without merits for your case:

#### 1. **Tight Jupyter Integration**
JupyterBook is built specifically for Jupyter notebooks and has some nice features:
- Familiar to Jupyter users
- Good integration with Binder for live execution
- MyST markdown for enhanced notebooks

#### 2. **Interactive Computing**
```yaml
# JupyterBook with Thebe
launch_buttons:
  thebe: true
```
Allows users to run code directly in the browser (though this requires a backend).

#### 3. **Sphinx Ecosystem**
Built on Sphinx, so you get access to many Sphinx extensions.

### Comparison Table

| Feature | Quarto | JupyterBook |
|---------|--------|-------------|
| **PDF Quality** | ⭐⭐⭐⭐⭐ Excellent | ⭐⭐⭐ Good but limited |
| **Math Rendering** | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ |
| **Web Output** | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ |
| **Multi-format** | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ |
| **Setup Complexity** | ⭐⭐⭐⭐ Easy | ⭐⭐⭐ Moderate |
| **Active Development** | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ |
| **Live Execution** | ⭐⭐⭐ | ⭐⭐⭐⭐ |
| **Customization** | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ |

## Implementation Recommendation

### Minimal Quarto Setup

1. **Install Quarto**: https://quarto.org/docs/get-started/

2. **Create `_quarto.yml`:**
```yaml
project:
  type: book
  output-dir: docs

book:
  title: "Multivariate Information Theory: A Practical Tutorial"
  author: "Giovanni Petri"
  date: today
  chapters:
    - index.md
    - part: "Part I: Foundations"
      chapters:
        - 01_information_theory_foundations.ipynb
        - 02_xor_problem_synergy.ipynb
    - part: "Part II: Advanced Tools"
      chapters:
        - 03_hoi_higher_order_interactions.ipynb
        - 04_frites_neural_timeseries.ipynb
        - 05_xgi_hypergraph_networks.ipynb
    - part: "Part III: Integration"
      chapters:
        - 06_complete_integration.ipynb
    - references.md

bibliography: references.bib

format:
  html:
    theme: cosmo
    code-fold: show
    code-tools: true
    toc: true
    number-sections: true
  pdf:
    documentclass: book
    toc: true
    number-sections: true
    colorlinks: true

execute:
  freeze: auto
  cache: true
  warning: false
```

3. **Create `index.md`** (landing page)
4. **Add `references.bib`** for citations
5. **Render**: `quarto render`

### Why Not Both?

You *could* technically maintain both, but:
- **Maintenance burden**: Two build systems to update
- **Divergence risk**: Outputs may differ
- **Diminishing returns**: Quarto's HTML is excellent

### Future Considerations

**If you later want**:
- **Interactive execution in browser** → Add JupyterHub/Binder link to Quarto book
- **Multiple deployment targets** → Quarto handles this natively
- **Academic paper** → Quarto generates journal-ready PDFs
- **Grant proposals** → Quarto's DOCX output useful

## Migration Strategy

Your notebooks are already in good shape. To convert to Quarto book:

1. **No changes to notebooks** - they work as-is
2. **Add `_quarto.yml`** configuration
3. **Create simple `index.md`** landing page
4. **Optional**: Add frontmatter to notebooks for per-chapter customization
5. **Render and iterate**

## Example Workflow

```bash
# Development
quarto preview  # Live preview as you edit

# Publishing to GitHub Pages
quarto render
# Commit docs/ folder to repo
# Enable GitHub Pages from /docs

# PDF for offline distribution
quarto render --to pdf
```

## Conclusion

**Choose Quarto because**:
1. Your content is mathematical and publication-quality
2. You need excellent PDF output
3. You want flexibility for future formats
4. Active development and modern tooling
5. Better suited for serious academic/research content

**Choose JupyterBook if**:
- You specifically need Sphinx extensions
- You're already heavily invested in Sphinx ecosystem
- You prioritize browser-based code execution
- Your organization has standardized on it

For your project, **Quarto is the clear winner**. It will give you a professional, flexible, and maintainable book that serves both web readers and PDF users beautifully.

## Resources

**Quarto**:
- Documentation: https://quarto.org/docs/books/
- Gallery: https://quarto.org/docs/gallery/#books
- Tutorial: https://quarto.org/docs/get-started/hello/rstudio.html

**JupyterBook** (for reference):
- Documentation: https://jupyterbook.org/
- Gallery: https://executablebooks.org/en/latest/gallery.html

## Next Steps

1. Install Quarto
2. Create minimal `_quarto.yml` (I can help with this)
3. Run `quarto preview` to see it work
4. Iterate on styling and organization
5. Deploy to GitHub Pages

Would you like me to generate a complete `_quarto.yml` and `index.md` for your specific notebooks?
