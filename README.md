# CanLearnML

## A Hands-on Journey into Machine Learning for Senior Developers

CanLearnML is an educational project designed specifically for experienced software developers who want to learn machine learning from first principles. Unlike many tutorials that assume either mathematical expertise or skip over foundational concepts, this project bridges the gap by providing a comprehensive, hands-on learning path from Python/NumPy basics to advanced PyTorch implementations.

### Who This Is For

- **Senior developers** who are proficient in programming but new to machine learning
- Engineers who prefer to understand the **why** behind concepts, not just the how
- Those who want to build neural networks and language models with a **solid foundation**
- Learners who appreciate clear explanations with **practical code examples**

## Learning Path

The project is structured as a progressive journey through four modules:

### Module 1: Python-NumPy Foundations
- Vectorization techniques and why they matter for ML performance
- Broadcasting rules and memory layout optimizations
- Data transformation techniques essential for ML workflows
- Practical performance comparisons between approaches

### Module 2: Mathematical Foundations
- Linear algebra concepts applied to machine learning problems
- Calculus fundamentals for gradient-based optimization
- Probability and statistics for model evaluation
- Mathematical intuition built through code examples

### Module 3: From Manual to Automatic
- Building neural networks from scratch with NumPy
- Understanding backpropagation and gradient descent
- Transitioning from manual implementations to automatic differentiation
- Visualizing and debugging learning processes

### Module 4: PyTorch Fundamentals
- Modern PyTorch patterns and best practices
- Building and training neural networks efficiently
- Language modeling techniques and implementations
- Scaling up from toy examples to practical applications

## Teaching Approach

CanLearnML emphasizes:

- **Hands-on learning** with executable notebooks
- **Performance comparisons** between different implementation approaches
- **Visual explanations** of complex concepts
- **Progressive complexity** that builds on previous modules
- **Practical examples** that connect theory to implementation

## Getting Started

This project uses Python 3.13 and UV for dependency management.

```bash
# Create a virtual environment
uv venv -p 3.13
source .venv/bin/activate  # On Unix/macOS
# or
.venv\Scripts\activate  # On Windows

# Install dependencies
uv pip install -e .

# For development tools (optional)
uv pip install -e ".[dev]"
```

## Running the Notebooks

Each module contains Jupyter notebooks that can be run sequentially:

```bash
# Make sure your environment is activated
jupyter notebook
```

Navigate to the module you want to explore and open the corresponding notebook.

## Project Origins

This project was inspired by Andrej Karpathy's "Neural Networks: Zero to Hero" series, with a focus on improved didactics and a more structured learning path for senior developers new to machine learning.
A help in learning was https://github.com/AayushSameerShah/Neural-Net-Zero-to-Hero-with-Andrej/blob/. 

## Contributing

Contributions are welcome! Please see our guidelines in the project documentation for more information on how to contribute.

## License

This project is licensed under the MIT License - see the LICENSE file for details.