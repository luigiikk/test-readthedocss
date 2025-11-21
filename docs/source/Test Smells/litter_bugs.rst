Litter Bugs
=============
This smell occurs when tests leave persistent side effects (files, DB records, etc.), causing pollution.

Example:

.. code-block:: javascript

  test("create tmp file", () => {
    fs.writeFileSync("tmp.txt", "data");
    expect(true).toBe(true);
  });

Refactor:

.. code-block:: javascript

  afterEach(() => {
    fs.existsSync("tmp.txt") && fs.unlinkSync("tmp.txt");
  });

.. note::
  Tests must clean up everything they create.