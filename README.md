# Simple Python Application

A simple Python application demonstrating Jenkins pipeline integration with automated testing, code quality checks, and packaging.

## Features

- **Calculator**: Basic mathematical operations
- **Greeting Service**: Generate personalized greetings with timestamps
- **List Utilities**: Common list operations and statistics
- **CLI Interface**: Command-line interface for easy interaction
- **Comprehensive Testing**: Unit tests with pytest
- **Code Quality**: Linting with flake8 and formatting with black

## Installation

### From Source
```bash
git clone https://github.com/neerajk555/simple-python-app.git
cd simple-python-app
pip install -e .
```

### Development Setup
```bash
# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\\Scripts\\activate

# Install dependencies
pip install -r requirements-dev.txt
pip install -e .
```

## Usage

### As a Library
```python
from myapp.app import Calculator, GreetingService, ListUtils

# Calculator
calc = Calculator()
result = calc.add(5, 3)

# Greeting Service
service = GreetingService("World")
greeting = service.get_greeting()

# List Utilities
numbers = [1, 2, 3, 4, 5]
even_numbers = ListUtils.filter_even_numbers(numbers)
```

### Command Line Interface
```bash
# Calculator operations
simple-python-app calc add 5 3
simple-python-app calc multiply 4 7

# Greetings
simple-python-app greet --name "Jenkins" --time
```

### Direct Execution
```bash
python -m myapp.app
python -m myapp.cli greet --name "Test"
```

## Development

### Running Tests
```bash
# Run all tests
pytest

# Run with coverage
pytest --cov=myapp --cov-report=html

# Run specific test file
pytest tests/test_app.py

# Run with verbose output
pytest -v
```

### Code Quality
```bash
# Check code style
flake8 src tests

# Format code
black src tests

# Type checking
mypy src
```

### Building Distribution
```bash
python setup.py sdist bdist_wheel
```

## Jenkins Pipeline

This project includes a `Jenkinsfile` with the following stages:

1. **Checkout**: Clone the source code
2. **Setup**: Create virtual environment and install dependencies
3. **Lint**: Code quality checks with flake8
4. **Test**: Run unit tests with pytest
5. **Coverage**: Generate coverage reports
6. **Package**: Build distribution packages
7. **Archive**: Store build artifacts

## Requirements

- Python 3.8 or higher
- pip package manager
- Virtual environment (recommended)

## License

MIT License - see LICENSE file for details.