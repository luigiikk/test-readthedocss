Web-Browsing Test
====================
This smell occurs when a test requires internet access to run.

Example:

.. code-block:: javascript

  test("fetch products", async () => {
    const products = await fetch("https://api.store.com/products
  ");
    expect(products).toBeDefined(); // Fails offline
  });

Refactor:

.. code-block:: javascript

  global.fetch = jest.fn(() => Promise.resolve([]));

  test("fetch products", async () => {
    const products = await fetch();
    expect(products).toEqual([]);
  });

.. note::
  External services should be mocked or stubbed.