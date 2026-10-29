# Test levels and test-driven development

**Covers:** unit test, integration test, system test, TDD

## Testing at different distances {#overview}
Testing a whole product by hand is slow, and when it fails it does not tell you where the fault is. So teams test at several distances: close up on one function, in the middle on parts working together, and from far away on the whole product. Each level catches different problems at a different cost. Test-driven development adds a twist: you write the test first.

## unit test {#unit-test}
A unit test checks one small piece of code, such as a single function, in isolation from the rest of the system. It is fast, usually a fraction of a second, and it points to the exact place when it fails. A team can run thousands of them in a minute, many times a day.

To keep a unit test isolated, anything outside the unit, such as a database or a web service, is replaced by a plain stand-in.

## integration test {#integration-test}
Parts that pass their own tests can still fail together. The login page might pass its unit tests, and the database layer might pass its own, yet the two can disagree about the name of a field. An integration test checks that several parts work together correctly. It saves a new user through the page and checks that the database has the record.

These tests are slower and more complex, so there are fewer of them. They catch the problems that live between the parts.

## system test {#system-test}
A system test checks the whole finished product from end to end, the way a real user would use it: sign up, add items to a basket, pay and receive the confirmation. It runs against a complete environment that looks like production.

System tests give the most realistic result and the least precise diagnosis, because a failure could come from anywhere. They are also the slowest, so teams run them less often.

## TDD {#tdd}
TDD stands for test-driven development. You work in short cycles of three steps, often called red, green, refactor:

1. **Red:** write a small test for a behavior that does not exist yet, and watch it fail.
2. **Green:** write only enough code to make it pass.
3. **Refactor:** clean up the code while keeping the tests passing.

The first step proves that the test can fail, so it is a real check. The method also forces you to think about how the code will be used before you write it, and it leaves a set of tests as a by-product.

## A worked example {#example}
Here is one TDD cycle for a function that adds tax to a price.

```python
def add_tax(price, rate):
    return round(price * (1 + rate), 2)


def test_add_tax():
    assert add_tax(100, 0.2) == 120.0
    assert add_tax(19.99, 0.1) == 21.99


test_add_tax()
print("tests passed")
# tests passed
```

Let's walk through how the cycle ran:

1. Red: the test was written first and failed, because `add_tax` did not exist.
2. Green: the one-line function was added, and both checks passed.
3. Refactor: the team renamed a variable and ran the test again to be sure nothing broke.

The test is a unit test, because it checks one function alone. If the shop had also checked that the basket page shows the taxed total, that would be an integration test. Placing a real order from the browser and checking the receipt would be a system test.

## A common mistake {#mistake}
A common slip is having only system tests, because they feel closest to reality. They are slow and fragile, and when they fail nobody knows why. A healthier mix is many unit tests, fewer integration tests and a small number of system tests.

A second slip is writing the tests after the code and never seeing them fail, so you cannot be sure they test anything.

## Key points {#key-points}
- A unit test checks one small piece in isolation and is fast and precise.
- An integration test checks that several parts work together.
- A system test checks the whole product the way a user would, and is the slowest.
- TDD means write a failing test, make it pass, then clean up.
