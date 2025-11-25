Exception Catch/Throw
======================
This test smell occurs when the passing or failing of a test case depends on custom exception-handling code or exception throwing within the test in a way that may mask real problems and hamper debugging. 


.. note::
Use the test framework’s built-in exception assertions rather than manual catch/throw logic to make tests clearer and maintainable.