The Operating System Evangelist
===============================
This smell occurs when tests rely on OS-specific behavior, such as newline format or file system paths.

Example:

.. code-block:: javascript

  test("new line test", () => {
    expect(formatText("hello")).toBe("hello\r\n"); // Fails on Linux
  });

Refactor:

.. code-block:: javascript

  test("new line test", () => {
    const result = formatText("hello");
    expect(result.includes("hello")).toBe(true);
  });

.. note::
  Avoid assertions that differ depending on operating system.