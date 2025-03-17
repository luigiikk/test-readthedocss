Sensitive Equality
========================
This type of test occurs when a comparison with the toString method is used in an assertion. In the example, the test case uses the method in the assertion, comparing a test that is sensitive to the specific implementation of the toString() method, resulting in a test that is prone to errors.

.. code-block:: javascript

   test("it should check user age to be equal 
   to 13", () => {
   const user = getUser();
   expect(user.age.toString()).toBeEqual('13');
   });


Refactor:

.. code-block:: javascript

   test("it should check if user age is 13", () => {
   const user = getUser();
   expect(user.age).toBe(13);
   });



.. note::
   The test is comparing the value using toString(), making it sensitive to any changes in the implementation of this method. Ideally, it should compare the numeric value directly to ensure a more robust verification