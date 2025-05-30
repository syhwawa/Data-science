# Contribution Guidelines

## Table of Contents

- [Style Guidelines](#style-guidelines)
- [Write Article Draft](#write-article-draft)
- [Write Code](#write-code)

## Style Guidelines

### Tone and Structure

- Use direct, conversational language
- Keep paragraphs short (2-4 sentences maximum)
- Prioritize comprehensive but concise explanations without repetition
- Maintain a balanced ratio of explanation to code (approximately 50/50)

### Data Science Focus

- Begin with a real, practical data science problem before introducing the tool
- Focus on how each tool or feature helps solve that problem
- Always explain the **practical value** of a feature (e.g., saves time, reduces costs, enables offline workflows)
- Avoid tool-first framing. Tools should support a use case, not be the center of the article

### Reader Experience Assumptions

- Assume readers are data scientists who have basic programming knowledge but may be new to specific tools
- Write for readers who scan, not follow step-by-step; they want to *understand*, not necessarily *run* the code
- When mentioning install commands or configuration flags, keep them minimal and link out to official docs for details

## Write Article Draft

1. Create your blog post in [HackMD](https://hackmd.io)
2. Follow [these instructions](https://hackmd.io/c/tutorials/%2F%40docs%2Finvite-others-to-a-private-note-en) to share your draft with khuyentran@codecut.ai for review

## Write Code

### Environment Setup

#### Install uv

[uv](https://github.com/astral.sh/uv) is a fast Python package installer and resolver.

```bash
# Install uv
curl -LsSf https://astral.sh/uv/install.sh | sh

# Verify installation
uv --version
```

#### Install Dependencies

```bash
# Install dependencies from pyproject.toml
uv sync
```

#### Install Pre-commit Hooks

We use pre-commit to ensure code quality and consistency.

```bash
# Install pre-commit hooks
uv run pre-commit install
```

### Working with Marimo Notebooks

#### Creating a New Notebook

Create a new notebook using marimo:

```bash
uv run marimo edit notebook.py --sandbox
```

#### Publishing Notebooks

To export your marimo notebooks to HTML locally:

1. Make sure the `export_notebook.sh` script is executable:

   ```bash
   chmod +x export_notebook.sh
   ```

2. Run the script with your notebook name:

   ```bash
   # For notebooks in the root directory
   ./export_notebook.sh notebook_name

   # For notebooks in subdirectories
   ./export_notebook.sh path/to/notebook_name
   ```

   For example:

   ```bash
   ./export_notebook.sh data_science_tools/polars_vs_pandas
   ./export_notebook.sh llm/pydantic_ai_examples
   ```

The exported HTML files will be automatically deployed to GitHub Pages through the GitHub Actions workflow.

### Pull Request Process

1. Fork the repository
2. Create a new branch for your feature
3. Make your changes
4. Submit a pull request with a clear description of changes

