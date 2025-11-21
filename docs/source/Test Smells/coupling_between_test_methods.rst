Coupling Between Test Methods
================================
This type of test smell occurs when modifying one test affects the results of others because they share state implicitly.

Example:

.. code-block:: javascript

  let list = [];

  test("add item", () => {
    list.push("A");
    expect(list.length).toBe(1);
  });

  test("list should have one element", () => {
    expect(list.length).toBe(1); // Fails if run independently
  });

Refactor:

.. code-block:: javascript

  let list;

  beforeEach(() => {
    list = [];
  });

  test("add item", () => {
    list.push("A");
    expect(list.length).toBe(1);
  });

.. note::
  Setup/reset logic must ensure isolation.