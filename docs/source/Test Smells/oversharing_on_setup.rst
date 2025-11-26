Oversharing On Setup
======================
This test smell occurs when every test sets up a lot of shared data or dependencies — even if only some tests need them — causing overhead and confusion.



.. note::
Only set up what each test (or suite) truly requires; avoid one huge shared setup for everything.