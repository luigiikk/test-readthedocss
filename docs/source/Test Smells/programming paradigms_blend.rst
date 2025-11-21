Programming Paradigms Blend
===============================
This smell occurs when tests rely on global state or mixed programming paradigms (OO + procedural), making tests hard to isolate.

Example:

.. code-block:: javascript

  let sharedCounter = 0;

  test("increment", () => {
    sharedCounter++;
    expect(sharedCounter).toBe(1);
  });

Refactor:

.. code-block:: javascript

  test("increment local counter", () => {
    let counter = 0;
    counter++;
    expect(counter).toBe(1);
  });

.. note::
  Remove global mutable state from tests.