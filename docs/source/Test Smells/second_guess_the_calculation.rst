Second Guess The Calculation
==============================

This test smell occurs when, rather than using concrete test data and fixed expected values, the test calculates the expected answer ahead of the assertion (in the test), thus reducing the test’s value as a specification. 


Example:

.. code-block:: javascript

  const input = [2,4,6];
  const expected = input.reduce((a,b) => a + b);
  test("sum calculation", () => {
    expect(subject.sum(input)).toBe(expected);
  });

Refactor:

.. code-block:: javascript

  test("sum of [2,4,6] is 12", () => {
    expect(subject.sum([2,4,6])).toBe(12);
  });

.. note::
  Hard-coded expected values serve as documentation — calculating them in the test reduces readability and makes test intent less clear.