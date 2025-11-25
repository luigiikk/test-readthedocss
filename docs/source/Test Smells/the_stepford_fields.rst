The Stepford Fields
====================
This test smell occurs when too many fields in test data contain the same value, making it difficult to detect when the wrong field is being used, because everything happens to pass given identical values. 


Example:

.. code-block:: javascript

  const person = {
    title: "Test",
    firstName: "Test",
    lastName: "Test",
    company: "Test"
  };
  expect(person.getFullName()).toBe("Test Test Test");
  expect(person.getCompanyName()).toBe("Test");

Refactor:

.. code-block:: javascript

  const person = {
    title: "Mr",
    firstName: "John",
    lastName: "Doe",
    company: "AcmeCorp"
  };
  expect(person.getFullName()).toBe("Mr John Doe");
  expect(person.getCompanyName()).toBe("AcmeCorp");

.. note::
  Use varied and realistic values for each field so mistakes (e.g., using wrong field) become visible.