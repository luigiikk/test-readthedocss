Duplicated Code in Conditional
==================
This type of test smell occurs when the same code appears inside multiple branches of conditionals (e.g., if, else if, else) with different conditions. Repeating the same action in each branch reduces readability and increases maintenance effort.

Example:

Refactor:


.. note::
  Extract the duplicated code outside of the conditional blocks when possible. This improves clarity and avoids repetitive logic that can lead to bugs during updates.