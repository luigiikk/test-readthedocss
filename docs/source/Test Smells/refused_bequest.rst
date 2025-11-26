Refused Bequest
================
This test smell occurs when a mega setup (fixture) is inherited by many tests, some of which ignore parts of it, some use it, and most rely on only a small part — making it hard to parse what each test actually needs.



.. note::
Avoid large shared base fixtures that most tests ignore; keep per-suite setup specific to the suite’s needs.