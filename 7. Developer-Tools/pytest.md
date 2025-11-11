## Definition

Pytest is a testing framework for Python that makes it easy to write simple and scalable test cases. It supports unit tests, functional tests, and complex testing scenarios with minimal boilerplate code. Definitely better than unittest and can be combined in an elegant way.

### Unit Testing

Unit testing is a software testing method where individual units (functions, methods, classes) are tested in isolation to verify they work correctly. Benefits include:
- Early bug detection
- Easier refactoring
- Documentation of expected behavior
- Faster debugging

## Installation

```bash
pip install pytest
```

---

## Basic Usage

### 1. **Writing a Simple Test**

Create a test file starting with `test_` or ending with `_test.py`.

```python
# test_example.py
def add(a, b):
    return a + b

def test_add():
    assert add(2, 3) == 5
    assert add(-1, 1) == 0
```

---

### 2. **Running Tests**

```bash
pytest                          # Runs all tests in current directory
pytest test_example.py          # Runs tests in specific file
pytest tests/                   # Runs all tests in directory
pytest -v                       # Verbose output
pytest -k "test_add"            # Runs tests matching pattern
```

---

### 3. **Test Classes**

Group related tests together using classes.

```python
class TestCalculator:
    def test_add(self):
        assert add(2, 3) == 5
    
    def test_subtract(self):
        assert subtract(5, 3) == 2
```

---

### 4. **Fixtures**

Reusable setup code for tests.

```python
import pytest

@pytest.fixture
def sample_data():
    return [1, 2, 3, 4, 5]

def test_sum(sample_data):
    assert sum(sample_data) == 15
```

---

### 5. **Parametrized Tests**

Run the same test with different inputs.

```python
@pytest.mark.parametrize("a, b, expected", [
    (2, 3, 5),
    (0, 0, 0),
    (-1, 1, 0),
])
def test_add(a, b, expected):
    assert add(a, b) == expected
```

---

### 6. **Testing Exceptions**

Verify that code raises expected exceptions.

```python
def test_division_by_zero():
    with pytest.raises(ZeroDivisionError):
        result = 1 / 0
```

---

### 7. **Markers**

Skip or mark tests for specific conditions.

```python
@pytest.mark.skip(reason="Not implemented yet")
def test_feature():
    pass

@pytest.mark.skipif(sys.version_info < (3, 8), reason="Requires Python 3.8+")
def test_new_feature():
    pass
```

---

### 8. **Setup and Teardown**

Run code before and after tests.

```python
@pytest.fixture
def setup_database():
    db = create_database()
    yield db  # Test runs here
    db.close()  # Cleanup after test

def test_query(setup_database):
    result = setup_database.query("SELECT * FROM users")
    assert len(result) > 0
```

---

### 9. **Coverage Report**

Measure test coverage.

```bash
pip install pytest-cov
pytest --cov=myproject tests/       # Shows coverage report
pytest --cov=myproject --cov-report=html tests/  # Generates HTML report
```

---

### 10. **Useful Options**

```bash
pytest -x                       # Stop after first failure
pytest --maxfail=2              # Stop after 2 failures
pytest --tb=short               # Shorter traceback format
pytest -s                       # Show print statements
pytest --lf                     # Run last failed tests
pytest --ff                     # Run failures first, then others
```

---

## Project Structure

```
project/
├── src/
│   └── mymodule.py
├── tests/
│   ├── __init__.py
│   ├── conftest.py          # Shared fixtures
│   └── test_mymodule.py
└── pytest.ini               # Configuration file
```

---

## Configuration (pytest.ini)

```ini
[pytest]
testpaths = tests
python_files = test_*.py
python_classes = Test*
python_functions = test_*
addopts = -v --tb=short
```

---

## Mocking with unittest.mock

### 11. **Mock Objects**

Mock objects simulate real objects to isolate code during testing.

```python
from unittest.mock import Mock

def test_mock_basic():
    mock_obj = Mock()
    mock_obj.method.return_value = 42
    
    assert mock_obj.method() == 42
    mock_obj.method.assert_called_once()
```

---

### 12. **MagicMock**

MagicMock is a Mock subclass with default implementations of magic methods (e.g., `__str__`, `__len__`).

```python
from unittest.mock import MagicMock

def test_magic_mock():
    mock_list = MagicMock()
    mock_list.__len__.return_value = 5
    
    assert len(mock_list) == 5
```

---

### 13. **Patching**

Replace objects during tests to control dependencies.

```python
from unittest.mock import patch

# Patch as decorator
@patch('module.function')
def test_with_patch(mock_func):
    mock_func.return_value = 'mocked'
    assert module.function() == 'mocked'

# Patch as context manager
def test_with_context():
    with patch('requests.get') as mock_get:
        mock_get.return_value.status_code = 200
        response = requests.get('http://example.com')
        assert response.status_code == 200
```

---

### 14. **Mock Assertions**

Verify how mocks were called.

```python
mock = Mock()
mock.method(1, 2, key='value')

mock.method.assert_called_once()
mock.method.assert_called_with(1, 2, key='value')
mock.method.assert_called_once_with(1, 2, key='value')
assert mock.method.call_count == 1
```

---

### 15. **Side Effects**

Simulate exceptions or dynamic return values.

```python
mock = Mock()
mock.method.side_effect = [1, 2, 3]  # Returns different values
assert mock.method() == 1
assert mock.method() == 2

# Raise exception
mock.method.side_effect = ValueError('Error')
with pytest.raises(ValueError):
    mock.method()
```
