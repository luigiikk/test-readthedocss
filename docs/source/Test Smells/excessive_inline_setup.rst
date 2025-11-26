Excessive Inline Setup
=======================
This test smell occurs when too much setup is written inline (inside each test method) so that readers must scroll past or skip most of the test to get to the meaningful part (invocation/assertion). 

Example:

.. code-block:: javascript

  test("complex scenario", () => {
    // 20 lines of setup
    const a = new A();
    a.init();
    const b = new B(a);
    b.loadData();
    const c = new C(b);
    c.prepare();
    // finally:
    expect(c.run()).toBe(true);
  });

Refactor:

.. code-block:: javascript

  function minimalSetup() {
    const a = new A();
    a.init();
    const b = new B(a);
    b.loadData();
    return new C(b);
  }

  test("complex scenario", () => {
    const subject = minimalSetup();
    expect(subject.run()).toBe(true);
  });

.. note::
  Extract setup to helper functions or fixtures so each test focuses on the behaviour under test rather than setup noise.