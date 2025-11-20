Using Complicated X-Path or CSS Selectors
===========================================
This smell occurs when selectors contain deeply nested DOM chains, making tests fragile because small UI structure changes will break them.

Example:

.. code-block:: javascript

  const btn = document.querySelector("#root > div > main > form > div:nth-child(3) > button");
  btn.click();

Refactor:

.. code-block:: javascript

  const btn = document.querySelector("[data-test='submit']");
  btn.click();

.. note::
  Prefer stable selectors such as data-test attributes instead of complex DOM traversal.