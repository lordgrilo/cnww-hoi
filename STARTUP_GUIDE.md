# Quick Startup Guide - Avoiding Common Issues

## Fixed: CSL File Issue

✅ **RESOLVED** - The `nature-neuroscience.csl` reference has been removed from `_quarto.yml`. The book will now use Quarto's default citation style.

## Getting Started (Step by Step)

### 1. File Placement

Place these files in your repository root (same directory as your notebooks):

```
your-repo/
├── _quarto.yml           # Main configuration
├── index.md              # Landing page
├── references.md         # Bibliography page
├── references.bib        # BibTeX citations
├── installation_guide.md # Appendix
├── requirements.txt      # Python dependencies
├── styles.css           # Custom styling
├── 01_information_theory_foundations.ipynb
├── 02_xor_problem_synergy.ipynb
├── 03_hoi_higher_order_interactions.ipynb
├── 04_frites_neural_timeseries.ipynb
├── 05_xgi_hypergraph_networks.ipynb
└── 06_complete_integration.ipynb
```

### 2. First Render

```bash
# Navigate to your repo
cd your-repo

# Preview (opens browser, live reload)
quarto preview

# Or just render once
quarto render
```

## Common Issues and Solutions

### Issue: "File X not found"

**Check:**
- All files are in the same directory as `_quarto.yml`
- Notebook filenames match exactly (including `_` underscores)

**Quick fix:**
```bash
# List files to verify
ls -la *.ipynb *.md
```

### Issue: "Execution failed"

If notebooks fail to execute during rendering:

**Option 1: Freeze execution (recommended for first build)**
```yaml
# In _quarto.yml, change:
execute:
  freeze: true  # Don't execute notebooks, use existing outputs
```

**Option 2: Skip problematic notebook**
```yaml
# In _quarto.yml, comment out specific notebook:
chapters:
  # - 03_hoi_higher_order_interactions.ipynb  # Skip this one
```

**Option 3: Execute notebooks manually first**
```bash
# Run all notebooks in Jupyter first
jupyter notebook

# Then render with outputs
quarto render
```

### Issue: Missing Python packages

```bash
# Install all dependencies
pip install -r requirements.txt

# Or install just what you need for initial preview
pip install jupyter numpy scipy matplotlib seaborn
```

### Issue: PDF rendering fails

**Don't worry!** HTML rendering is more important initially.

```bash
# Just render HTML
quarto render --to html

# Skip PDF for now
# Later, install LaTeX when you need it
```

## Minimal Working Configuration

If you want to test with minimal setup:

1. **Only keep these files:**
   - `_quarto.yml`
   - `index.md` 
   - Your 6 notebooks

2. **Simplify `_quarto.yml`:**
```yaml
project:
  type: book
  output-dir: docs

book:
  title: "Multivariate Information Theory"
  author: "Your Name"
  chapters:
    - index.md
    - 01_information_theory_foundations.ipynb
    - 02_xor_problem_synergy.ipynb
    - 03_hoi_higher_order_interactions.ipynb
    - 04_frites_neural_timeseries.ipynb
    - 05_xgi_hypergraph_networks.ipynb
    - 06_complete_integration.ipynb

execute:
  freeze: true  # Use existing outputs

format:
  html:
    theme: cosmo
    toc: true
```

3. **Render:**
```bash
quarto preview
```

## Adding Features Incrementally

Once basic rendering works:

1. ✅ Add parts structure
2. ✅ Add references page
3. ✅ Add custom CSS
4. ✅ Enable PDF output
5. ✅ Add bibliography

## Testing Your Setup

### Test 1: Can Quarto find files?
```bash
quarto check
```

### Test 2: Preview without execution
```bash
# Edit _quarto.yml first: freeze: true
quarto preview
```

### Test 3: Render just index
```bash
quarto render index.md
```

## Custom Citation Style (Optional)

If you want Nature Neuroscience style later:

1. Download CSL file:
```bash
wget https://www.zotero.org/styles/nature-neuroscience -O nature-neuroscience.csl
```

2. Add back to `_quarto.yml`:
```yaml
bibliography: references.bib
csl: nature-neuroscience.csl
```

Or browse styles at: https://www.zotero.org/styles

## Next Steps After Successful Render

1. **Customize styling**: Edit `styles.css`
2. **Add content**: Edit `index.md` with your info
3. **Check output**: Look in `docs/` folder
4. **Deploy**: Push to GitHub, enable Pages

## Getting Help

If stuck:
1. Check `quarto check` output
2. Review error messages carefully
3. Try minimal configuration first
4. Check Quarto docs: https://quarto.org/docs/books/

---

**You should be good to go now!** The CSL issue is fixed. Just run `quarto preview` and it should work.
