Parsed Data
==============
This test smell occurs when a test creates structured data by parsing unstructured input (e.g., JSON parsing inside the test) and then uses only the structured data for assertions, adding unnecessary complexity. 
test-smell-catalog.readthedocs.io

Example:

.. code-block:: javascript

  test("should parse response", () => {
    const raw = '{"id":1,"name":"John"}';
    const data = JSON.parse(raw);
    expect(data.name).toBe("John");
  });

Refactor:

.. code-block:: javascript

  test("should handle parsed response", () => {
    const data = { id:1, name:"John" };
    expect(handler(data).name).toBe("John");
  });

.. note::
  Simplify tests by using already-structured data where parsing overhead is not the core behaviour being tested.