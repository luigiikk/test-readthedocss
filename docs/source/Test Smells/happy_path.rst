Happy Path
==============
This type of test smell occurs when a test uses known input, executes without exception, and produces the expected output—thus only verifying the “sunny day” scenario and ignoring error conditions or edge cases. 

Example:

.. code-block:: javascript

  test("should add two numbers", () => {
    expect(add(2, 3)).toBe(5);
  });

Refactor:

.. code-block:: javascript

  test("should add two numbers correctly", () => {
    expect(add(2, 3)).toBe(5);
  });

  test("should throw if argument is non-number", () => {
    expect(() => add(2, "x")).toThrow(Error);
  });

.. note::
  While verifying the happy path is important, tests should also cover failure paths and edge cases to detect hidden defects.