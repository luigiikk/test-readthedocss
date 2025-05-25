Verify in Setup
========================
This type of test smell occurs when the test setup used to prepare the test environment contains assertions, violating the purpose of the test setup and compromising clarity and reliability.

Example:

.. code-block:: javascript

  afterEach(function() {
    const metasets = this.chart._metasets;
    expect(metasets.length).toEqual(this.chart.data.datasets.length);
    for (let i = 0; i < metasets.length; i++) {
    expect(metasets[i].index).toEqual(i);
    expect(metasets[i]._dataset).toEqual(this.chart.data.datasets[i]);
    }
  });

Refactor:


.. note::
The test setup should not contain assertions. Assertions should be part of the actual test cases to maintain clarity and proper test structure.