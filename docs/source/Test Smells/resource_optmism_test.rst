Resource Optimism
===================
This type of test smell occurs when the test assumes the availability of a resource (such as a file, database, or network service) without verifying its existence or state beforehand. This can lead to fragile tests that fail due to environmental issues rather than logic errors.

Example:

.. code-block:: javascript

  test('should read the file contents', () => {
    const data = fs.readFileSync(path, 'utf-8');
    expect(data).toBe('Hello, World!');
  });

Refactor:


.. note::
  Always check the availability and validity of external resources before using them in tests. This ensures more robust and predictable test behavior, especially in CI/CD or shared environments.