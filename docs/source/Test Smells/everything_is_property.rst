Everything Is A Property
=========================
This test smell occurs when a test class keeps what should be temporary variables in instance variables (properties), rather than local variables, thus blurring scope and increasing risk of leakage between tests. 

Example:

.. code-block:: javascript

  class MyTests {
  subject;
  setupData;

  beforeEach(() => {
    this.setupData = { x:1 };
    this.subject = new Subject(this.setupData);
  });

  test("does work", () => {
    expect(this.subject.doSomething()).toBe(1);
  });


  }

Refactor:

.. code-block:: javascript

  test("does work", () => {
    const setupData = { x:1 };
    const subject = new Subject(setupData);
    expect(subject.doSomething()).toBe(1);
  });

.. note::
  Use local variables inside each test method when possible, to improve isolation and clarity.