Unrestricted Imports
======================
This test smell occurs when a module imports more from another module than needed, resulting in unnecessary coupling and bloated dependencies. 


Example:

.. code-block:: javascript

  // In test file
  import { A, B, C, D } from "utils";
    test("does A", () => {
    expect(A()).toBe(true);
  });

Refactor:

.. code-block:: javascript

  // In test file
  import { A } from "utils";
    test("does A", () => {
    expect(A()).toBe(true);
  });

.. note::
  Import only what the test requires to minimise coupling and improve clarity of dependencies.