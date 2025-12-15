# Getting Started with Quarto Book

This is a quick guide to building and deploying your Quarto book.

## Prerequisites

1. **Install Quarto**: https://quarto.org/docs/get-started/
   ```bash
   # macOS
   brew install quarto
   
   # Windows
   # Download installer from https://quarto.org/docs/get-started/
   
   # Linux
   # Download and install from https://quarto.org/docs/get-started/
   ```

2. **Verify installation**:
   ```bash
   quarto --version
   ```

## Building Your Book

### 1. Preview Locally (Recommended During Development)

```bash
# Navigate to your repository
cd multivariate-information-theory-tutorial

# Start live preview server
quarto preview

# Opens browser at http://localhost:4200
# Auto-reloads when you save changes
```

### 2. Render Complete Book

```bash
# Render HTML version (default)
quarto render

# Output goes to docs/ folder
```

### 3. Render Specific Formats

```bash
# HTML only
quarto render --to html

# PDF only
quarto render --to pdf

# Both HTML and PDF
quarto render --to html --to pdf
```

### 4. Render Single Chapter

```bash
# Just one notebook
quarto render 01_information_theory_foundations.ipynb
```

## Customizing Your Book

### Basic Configuration

Edit `_quarto.yml`:

```yaml
book:
  title: "Your Title"
  author: "Your Name"
  
format:
  html:
    theme: cosmo  # Try: cosmo, flatly, darkly, etc.
```

### Adding Content

1. **Create new chapter**: Add `.ipynb` or `.md` file
2. **Register in `_quarto.yml`**:
   ```yaml
   chapters:
     - new_chapter.ipynb
   ```
3. **Render**: `quarto render`

### Styling

Modify `styles.css` for custom styling:
```css
/* Example: Change heading color */
h1, h2 {
  color: #0969da;
}
```

## Publishing Options

### Option 1: GitHub Pages (Recommended)

```bash
# 1. Render the book
quarto render

# 2. Commit changes
git add .
git commit -m "Update book"
git push

# 3. Enable GitHub Pages
# Go to: Settings > Pages > Source: main branch, /docs folder
```

Your book will be available at: `https://yourusername.github.io/repo-name`

### Option 2: Quarto Pub

```bash
# One-time setup
quarto publish quarto-pub

# Future updates
quarto publish quarto-pub
```

### Option 3: Netlify

1. Connect GitHub repo to Netlify
2. Build command: `quarto render`
3. Publish directory: `docs`

## Workflow Tips

### During Development

```bash
# Use preview for live updates
quarto preview

# Edit notebooks in Jupyter as usual
jupyter notebook

# Quarto preview will auto-refresh
```

### Before Publishing

```bash
# Check for errors
quarto render

# Review locally
open docs/index.html  # macOS
start docs/index.html # Windows
xdg-open docs/index.html # Linux
```

### Execution Control

Control notebook execution in `_quarto.yml`:

```yaml
execute:
  freeze: auto    # Only re-run when notebook changes
  cache: true     # Cache results
  eval: true      # Execute code cells
  echo: true      # Show code in output
```

Options:
- `freeze: true` - Never re-execute (fastest)
- `freeze: auto` - Re-execute only changed notebooks
- `freeze: false` - Always re-execute (slowest)

## Common Tasks

### Add Bibliography

1. Create `references.bib`:
   ```bibtex
   @article{shannon1948,
     title={A Mathematical Theory of Communication},
     author={Shannon, Claude E},
     journal={Bell System Technical Journal},
     year={1948}
   }
   ```

2. Cite in notebooks:
   ```markdown
   As Shannon showed [@shannon1948], entropy measures...
   ```

### Add Cross-References

```markdown
See @fig-example for visualization.

See @eq-entropy for the formal definition.
```

### Include Math

```markdown
The entropy is defined as:

$$H(X) = -\sum_{i} p_i \log_2 p_i$$ {#eq-entropy}
```

### Add Callouts

```markdown
::: {.callout-note}
## Important Note
This is a highlighted note.
:::

::: {.callout-warning}
## Warning
Be careful here!
:::
```

## Troubleshooting

### Issue: Notebooks won't execute

**Check:**
1. Is Python kernel available? `jupyter kernelspec list`
2. Are packages installed? See `installation_guide.md`
3. Set `freeze: true` to skip execution

### Issue: PDF rendering fails

**Solutions:**
1. Install LaTeX:
   ```bash
   # macOS
   brew install --cask mactex
   
   # Windows - Install MiKTeX
   # Linux
   sudo apt-get install texlive-full
   ```

2. Or use Quarto's built-in TinyTeX:
   ```bash
   quarto install tinytex
   ```

### Issue: Changes don't appear

**Solutions:**
1. Stop preview (`Ctrl+C`)
2. Clear cache: `rm -rf .quarto`
3. Re-render: `quarto render`
4. Restart preview: `quarto preview`

### Issue: Links broken after publishing

**Check:**
- Relative paths in notebooks
- Update `repo-url` in `_quarto.yml`

## Advanced Features

### Multiple Formats Simultaneously

```yaml
format:
  html:
    theme: cosmo
  pdf:
    documentclass: book
  docx:
    reference-doc: template.docx
```

### Custom Templates

```yaml
format:
  html:
    template: custom-template.html
```

### Conditional Content

```markdown
::: {.content-visible when-format="html"}
This only appears in HTML
:::

::: {.content-visible when-format="pdf"}  
This only appears in PDF
:::
```

## Resources

- **Quarto Guide**: https://quarto.org/docs/books/
- **Gallery**: https://quarto.org/docs/gallery/#books
- **Discussions**: https://github.com/quarto-dev/quarto-cli/discussions

## Quick Reference

```bash
# Preview with live reload
quarto preview

# Render entire book
quarto render

# Render to specific format
quarto render --to pdf

# Check for issues
quarto check

# Get help
quarto render --help
```

---

::: {.callout-tip}
## Pro Tip

Use `quarto preview` during development - it's much faster than re-rendering after each change!
:::
