Unused Imports
=================
This test smell occurs when an import from another module is never used in the test code. 


Example:

.. code-block:: javascript

  import { X } from "helpers";
  import { Y } from "unusedHelpers";

  test("uses X", () => {
    expect(X()).toBeDefined();
  });

Refactor:

.. code-block:: javascript

  import { X } from "helpers";

  test("uses X", () => {
    expect(X()).toBeDefined();
  });

.. note::
  Remove unused imports to avoid confusion, unnecessary dependencies and maintenance overhead.