Remote Control Mocking
========================
This test smell occurs when a class that depends on a service is tested by mocking the service’s complex dependencies, instead of simply mocking the service itself. 


Example:

.. code-block:: javascript

  // Controller depends on Repository -> ConnectionFactory -> Connection
  const mockConnection = mock(Connection);
  const mockFactory = { getConnection: () => mockConnection };
  const repository = new Repository(mockFactory);
  const controller = new Controller(repository);

  test("controller returns data", () => {
    when(mockConnection.query(...)).thenReturn(testData);
    expect(controller.handleRequest()).toBe(testData);
  });

Refactor:

.. code-block:: javascript

  const mockRepository = mock(Repository);
  const controller = new Controller(mockRepository);

  test("controller returns data", () => {
    when(mockRepository.getData()).thenReturn(testData);
    expect(controller.handleRequest()).toBe(testData);
  });

.. note::
  Mock as close to the boundary of the unit under test as possible, to avoid over-mocking deep dependencies.