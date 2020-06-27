# Testing

## Test Driven Development (TDD)
A process where tests are written for tasks before the code to implement those tasks is written.

Reference links:
* [Data Science and Test Driven Development](https://www.linkedin.com/pulse/data-science-test-driven-development-sam-savage/)

* [Test-Driven Development for Data Science](http://engineering.pivotal.io/post/test-driven-development-for-data-science/)

* [Test Driven Development is essential for good data science. Here’s why.](https://medium.com/uk-hydrographic-office/test-driven-development-is-essential-for-good-data-science-heres-why-db7975a03a44)

* [Testing Your Code](https://docs.python-guide.org/writing/tests/)


## Unit Test
A test that covers a "unit" of code, usually a single function independent of the rest of the code.


## Integration Test
Used to show that all parts of the program are working correctly with each other. [Integration testing](https://www.fullstackpython.com/integration-testing.html_)


[Four Ways Data Science Goes Wrong and How Test-Driven Data Analysis Can Help](https://www.predictiveanalyticsworld.com/machinelearningtimes/four-ways-data-science-goes-wrong-and-how-test-driven-data-analysis-can-help/6947/)

[Getting Started Testing](https://speakerdeck.com/pycon2014/getting-started-testing-by-ned-batchelder)
[Presentation](https://www.youtube.com/watch?v=FxSsnHeWQBY)


## pytest
Install with `pip install -U pytest`. See pytest docs [here](https://docs.pytest.org/en/latest/getting-started.html).

Use for testing by writing a test file with functions to test and then run `pytest` in the directory where the test file exists. Generally only 1 assert statement is included per test otherwise you would not know how many tests failed or which tests failed.

In the test output, periods represent successful unit tests and F's represent failed unit tests.

NOTE: Test file needs to be named starting with "test_" and the functions also need to start with "test_".


Example test file:

```
from file import function_to_test

def test_function():
    assert(function_to_test(args) == the_true_value)
```


More examples:
File: `compute_launch.py`
```
def days_until_launch(current_day, launch_day):
    """"Returns the days left before launch.

    current_day (int) - current day in integer
    launch_day (int) - launch day in integer
    """
    if (launch_day < current_day):
        return 0
    else:
        return launch_day - current_day
```

Test file: `test_compute_launch.py`
```
from compute_launch import days_until_launch

def test_days_until_launch_4():
    assert(days_until_launch(22, 26) == 4)

def test_days_until_launch_0():
    assert(days_until_launch(253, 253) == 0)

def test_days_until_launch_0_negative():
    assert(days_until_launch(83, 64) == 0)

def test_days_until_launch_1():
    assert(days_until_launch(9, 10) == 1)
```




