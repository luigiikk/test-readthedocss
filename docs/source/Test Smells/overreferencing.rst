Overreferencing
================
This test smell occurs when a test method references application code too many times (many calls to production code) rather than focusing on a clear behavior. 

Example:

.. code-block:: javascript

  test("complex scenario", () => {
    const a = subject.method1();
    const b = subject.method2(a);
    const c = subject.method3(b);
    expect(subject.method4(c)).toBe(true);
  });

Refactor:

.. code-block:: javascript

  test("should complete workflow", () => {
    expect(subject.completeWorkflow()).toBe(true);
  });

.. note::
  Limit the number of references to production code in a single test — aim for clarity in what behaviour is being verified.