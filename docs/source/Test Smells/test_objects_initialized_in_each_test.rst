Test Objects Initialized In Each Test
=======================================
This test smell occurs when initialization of the test object happens inside each test method, often redundantly or verbosely, rather than shared appropriately via setup or fixtures.
Example:

.. code-block:: javascript

  test("size works", () => {
    const widget = new Widget();
    widget.setSize(10);
    expect(widget.size).toBe(10);
  });

  test("color works", () => {
    const widget = new Widget();
    widget.setColor("red");
    expect(widget.color).toBe("red");
  });

Refactor:

.. code-block:: javascript

  let widget;

  beforeEach(() => {
    widget = new Widget();
  });

  test("size works", () => {
    widget.setSize(10);
    expect(widget.size).toBe(10);
  });

  test("color works", () => {
    widget.setColor("red");
    expect(widget.color).toBe("red");
  });

.. note::
  Initialization can be extracted to beforeEach/setup when common — reduces duplication while keeping isolation.