# Pre-commit Hooks Example

This repository demonstrates how to set up and use pre-commit hooks for Python development. It includes configuration for code formatting (Black), linting (Ruff), and various other code quality checks.

## Features

- Code formatting with [Black](https://github.com/psf/black)
- Linting and import sorting with [Ruff](https://github.com/astral-sh/ruff)
- Various git hooks for code quality checks
- Pre-commit configuration for automated checks

## Prerequisites

- Python 3.8 or higher
- Git

## Installation

1. Clone this repository:
   ```bash
   git clone <your-repo-url>
   cd <your-repo-name>
   ```

2. Create and activate a virtual environment (recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use: venv\Scripts\activate
   ```

3. Install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

4. Install the pre-commit hooks:
   ```bash
   pre-commit install
   ```

## Configuration

The repository includes the following pre-commit hooks:

### Basic Git Hooks
- `check-yaml`: Validates YAML files
- `end-of-file-fixer`: Ensures files end with a newline
- `trailing-whitespace`: Removes trailing whitespace
- `check-added-large-files`: Prevents committing large files
- `check-ast`: Validates Python files are syntactically correct
- `check-json`: Validates JSON files
- `check-merge-conflict`: Checks for merge conflict strings
- `detect-private-key`: Prevents committing private keys

### Python-specific Hooks
- `black`: Code formatting
- `ruff`: Linting and import sorting
- `ruff-format`: Code formatting (alternative to Black)

## Usage

The pre-commit hooks will run automatically when you try to commit changes. You can also run them manually:

```bash
# Run against all files
pre-commit run --all-files

# Run against staged files only
pre-commit run
```

## Customization

### Black Configuration
You can customize Black's behavior by creating a `pyproject.toml` file:

```toml
[tool.black]
line-length = 88
target-version = ['py39']
```

### Ruff Configuration
You can customize Ruff's behavior by creating a `pyproject.toml` or `.ruff.toml` file:

```toml
[tool.ruff]
line-length = 88
target-version = "py39"
```

## Troubleshooting

If you need to skip the pre-commit hooks for a particular commit:
```bash
git commit -m "your message" --no-verify
```

## Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a new Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
