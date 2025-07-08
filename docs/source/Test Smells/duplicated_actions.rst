Duplicated Actions
==================
This type of test smell occurs when certain actions or sequences (e.g., object creation, setup steps, repeated API calls) appear in multiple places across different tests. This repetition leads to bloated test code and increases the chance of inconsistencies during updates.

Example:

Refactor:


.. note::
  Move duplicated actions into helper functions, setup methods, or shared utilities to reduce redundancy and improve maintainability.