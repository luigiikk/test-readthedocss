Hardcoded Environment Configuration
====================================
This test smell occurs when tests contain hard-coded environment values such as hostnames, ports, or credentials, making them dependent on a specific machine or configuration. This prevents tests from running in different environments reliably.

Example:

.. code-block:: javascript

  test("Connects to DB", () => {
  const db = connect("localhost", 5432);
  expect(db.isConnected()).toBe(true);
  });

Refactor:

.. code-block:: javascript

  const DB_HOST = process.env.DB_HOST;
  const DB_PORT = process.env.DB_PORT;

  test("Connects to DB", () => {
    const db = connect(DB_HOST, DB_PORT);
    expect(db.isConnected()).toBe(true);
  });

.. note::
  Use environment variables or configuration files for flexibility and portability.