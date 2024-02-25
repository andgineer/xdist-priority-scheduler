[![Build Status](https://github.com/andgineer/xdist-scheduling-exclusive/workflows/CI/badge.svg)](https://github.com/andgineer/xdist-scheduling-exclusive/actions)
[![Coverage](https://raw.githubusercontent.com/andgineer/xdist-scheduling-exclusive/python-coverage-comment-action-data/badge.svg)](https://htmlpreview.github.io/?https://github.com/andgineer/xdist-scheduling-exclusive/blob/python-coverage-comment-action-data/htmlcov/index.html)
# xdist-scheduling-exclusive

pytest-xdist scheduler that runs some tests on dedicated workers. 

Can significantly improve runtime by running long tests on separate 
workers.

# Installation

```bash
pip install xdist-scheduling-exclusive
```

# Usage

Add to `conftest.py`:

```python
from xdist_scheduling_exclusive import ExclusiveScheduling

def pytest_xdist_make_scheduler(config, log):
    """xdist-pytest hook to set scheduler."""
    return ExclusiveScheduling(config, log)
```

Also there is alternative scheduler `ExclusiveLoadFileScheduling` which works like xdist `loadfile` scheduler, 
but put exclusive tests into separate groups so they can run in parallel even if defined in one file.

# Developers

Do not forget to run `. ./activate.sh`.

# Scripts
    make help

## Coverage report
* [Codecov](https://app.codecov.io/gh/andgineer/xdist-scheduling-exclusive/tree/main/src%2Fxdist_scheduling_exclusive)
* [Coveralls](https://coveralls.io/github/andgineer/xdist-scheduling-exclusive)
