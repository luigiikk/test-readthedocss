Lonely Test
==============
A test that cannot run alone because it depends on shared fixtures initialized outside its scope.

Example:

.. code-block:: javascript

  // Loaded only at suite level
  beforeAll(() => {
    global.token = generateToken();
  });

  test("validate token", () => {
    expect(global.token).toBeDefined();
  });

Refactor:

.. code-block:: javascript

  test("validate token", () => {
    const token = generateToken();
    expect(token).toBeDefined();
  });

.. note::
  A test must be executable independently from the suite.