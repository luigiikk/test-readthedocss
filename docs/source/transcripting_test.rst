Transcripting Test
========================
The specified test smell occurs when print commands are used within the test case. In the example, it is evident that different "console" commands are used within the test block to display messages in the terminal, which can impact performance, and security, and cause visual clutter in the test.
Example:

.. code-block:: javascript

   test("Test 1", () => {
   console.log("Loggin to the console");
   expect(someFinction()).toBe(true);
   });
   test("Test 2", () => {
   console.warn("Loggin to the console");
   expect(someFunction()).toBe(true);
   });
   test("Test 3", () => {
   console.error("Loggin to the console");
   expect(someFunction()).toBe(true);
   });

Refactor:

.. code-block:: javascript

   test("Test 1", () => {
   expect(someFinction()).toBe(true);
  });
   test("Test 2", () => {
   expect(someFunction()).toBe(true);
   });
   test("Test 3", () => {
   expect(someFunction()).toBe(true);
   });

.. note::
   The test itself provides error logs, so there's no need to use the console function