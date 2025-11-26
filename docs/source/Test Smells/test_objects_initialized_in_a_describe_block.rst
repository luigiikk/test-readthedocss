Test Objects Initialized In A Describe Block
===============================================
This test smell occurs when tests share the same reference to an object initialized in a describe/context block (or suite/header), meaning any single test can mutate the object for following tests.
Example:

.. code-block:: javascript

  describe("Widget tests", () => {
  const widget = new Widget(); // shared across all tests

  test("should set size", () => {
    widget.setSize(10);
    expect(widget.size).toBe(10);
  });

  test("should default color", () => {
    expect(widget.color).toBe("blue");  // may fail if size test mutated widget
  });


  });

Refactor:

.. code-block:: javascript

  describe("Widget tests", () => {
  let widget;

  beforeEach(() => {
    widget = new Widget();
  });

  test("should set size", () => {
    widget.setSize(10);
    expect(widget.size).toBe(10);
  });

  test("should default color", () => {
    expect(widget.color).toBe("blue");
  });
  });

.. note::
  Avoid sharing mutable object state across tests; initialize fresh instances per test.