Asynchronous Test
==================
This smell occurs when tests include explicit delays that slow down execution unnecessarily, reducing test suite performance.

Example:

.. code-block:: javascript

  test("Fetch data", (done) => {
    setTimeout(() => {
    expect(fetchData()).toBeDefined();
    done();
    }, 5000); // arbitrary delay
  });

Refactor:

.. code-block:: javascript

  test("Fetch data asynchronously", async () => {
    const result = await fetchData();
    expect(result).toBeDefined();
  });

.. note::
  Avoid using arbitrary delays. Prefer promises, mocks, and async test support.