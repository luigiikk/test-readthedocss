Disorder
=========
This test smell occurs when the order of elements in a test module does not follow a logical or standard structure, making the test file hard to browse and understand.

Example:

.. code-block:: javascript

  test("C", () => {});

  beforeAll(() => {});

  test("A", () => {});

  afterAll(() => {});
  
  test("B", () => {});

Refactor:

.. code-block:: javascript

  beforeAll(() => {});
  afterAll(() => {});

  test("A", () => {});
  test("B", () => {});
  test("C", () => {});

.. note::
  Maintain a clear and consistent ordering pattern such as setup → execution → teardown.