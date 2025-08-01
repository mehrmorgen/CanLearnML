# CanLearnML Project Guidelines

## Project Overview

CanLearnML is an educational project focused on teaching machine learning concepts to senior developers. The project is structured as a series of modules that progressively build knowledge from Python/NumPy foundations to advanced PyTorch implementations.

### Project Structure

- **Module 1 - Python-NumPy Foundations**: Covers vectorization, broadcasting, memory layout, and data transformations essential for ML
- **Module 2 - Mathematical Foundations**: Focuses on linear algebra, calculus, probability, and statistics concepts used in ML
- **Module 3 - From Manual to Automatic**: Demonstrates the transition from manual implementations to automatic differentiation
- **Module 4 - PyTorch Fundamentals**: Introduces PyTorch framework for building neural networks and language models

Each module contains Jupyter notebooks with a combination of explanatory text and code examples. The teaching approach is hands-on with performance comparisons and practical examples.

## Development Tools

**IMPORTANT:** CanLearnML strives to be as strict as possible with modern syntax and latest libraries, with exceptions only for compatibility issues common in the Python data science ecosystem. We use UV with the project TOML for everything.

### **UV** — Package & Environment Management
- **What:** Fast dependency resolver, installer, and Python virtual environment manager
- **Why:** 10–100x faster than pip; reliable, cross-platform, and supports modern workflows
- **When to use:** For all dependency and environment management (install, sync, run commands)
- **Policy:** UV is the only supported tool for dependency management and environment setup

### **Ruff** — Unified Linter, Formatter & Import Organizer
- **What:** Handles linting, code formatting, and import sorting in one fast tool
- **Why:** Replaces multiple tools with a single, ultra-fast, highly configurable tool
- **When to use:** For all routine code quality, formatting, and import hygiene tasks
- **Configuration:** Strict settings with line length of 88, targeting Python 3.13, and comprehensive linting rules

### **mypy** — Static Type Checking
- **What:** Enforces type annotations and detects type errors statically
- **Why:** Ensures type-hint coverage and prevents type-related bugs
- **When to use:** After code changes, before PR or merge
- **Configuration:** Strict mode enabled with comprehensive error checking

## Development Workflow

### Initial Project Setup

1. **Create virtual environment:**
   ```bash
   uv venv -p 3.13
   source .venv/bin/activate  # On Unix/macOS
   # or
   .venv\Scripts\activate  # On Windows
   ```

2. **Install dependencies:**
   ```bash
   uv pip install -e .
   
   # For development dependencies
   uv pip install -e ".[dev]"
   ```

### Standard Development Workflow

```bash
# 1. Make code changes (manual or automated)

# 2. Apply linting, formatting, and import sorting
uv pip run ruff check --fix .
uv pip run ruff format .

# 3. Type checking
uv pip run mypy .

# 4. Run tests (when available)
uv pip run pytest
```

The strict type checking configuration in mypy includes exceptions for data science libraries to ensure compatibility while maintaining strict typing for our own code.

## Guidelines for Contributors

### Code Style

1. Follow the existing code style in the notebooks, which includes:
   - Detailed markdown explanations before code cells
   - Type hints for function parameters and return values
   - Comprehensive comments explaining complex operations
   - Clear variable naming that reflects the mathematical concepts

2. Maintain the educational focus:
   - Code should prioritize clarity over excessive optimization
   - Include explanations of why certain approaches are used
   - Compare different implementation approaches when relevant

### Testing

1. For code changes to notebooks:
   - Ensure all cells can execute without errors
   - Verify that outputs match expectations
   - Test with small examples before applying to larger datasets

2. For package structure changes:
   - Verify that `uv pip install -e .` works correctly
   - Ensure notebooks can import from the package structure

### Project Organization

1. Keep the modular structure intact:
   - Each module should build on concepts from previous modules
   - Maintain clear separation between different learning topics

2. When adding new content:
   - Place it in the appropriate module
   - Update README.md if adding new modules
   - Ensure dependencies are properly documented in pyproject.toml

## Troubleshooting

- **Virtual environment not activated?**
  - Run `source .venv/bin/activate` (Unix/macOS) or `.venv\Scripts\activate` (Windows)
  
- **Dependencies not installed?**
  - Run `uv pip install -e .` or `uv pip install -e ".[dev]"` for development dependencies
  
- **Verify your environment:**
  - `uv --version`
  - `python --version`
  - `uv pip list`

## Building and Packaging

The project uses setuptools for packaging. When making changes that affect the package structure:

1. Update version numbers in pyproject.toml
2. Test installation in a clean environment before submitting changes