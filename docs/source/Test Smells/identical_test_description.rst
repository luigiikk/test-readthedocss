Identical Test Description
============================
This type of test smell refers to test cases that have identical descriptions within the same test scope.

Example:

.. code-block:: javascript

  it('has expected extent', function () {
    const sources = [
    getZoomifySource(),
    getZoomifySourceWithExtentInFirstQuadrant(),
    ];
    const expectedExtents = [
    [0, -size[1], size[0], 0],
    [0, 0, size[0], size[1]],
    ];
    for (let i = 0; i < sources.length; i++) {
    const tileGrid = sources[i].getTileGrid();
    expect(tileGrid.getExtent()).to.eql(expectedExtents[i]);
    }
    });
    it('has expected extent', function () {
    const sources = [getZoomifySource(), getIIPSource()];
    for (let i = 0; i < sources.length; i++) {
    const tileGrid = sources[i].getTileGrid();
    const expectedExtent = [0, -h, w, 0];
    expect(tileGrid.getExtent()).to.eql(expectedExtent);
    }
  });

Refactor:

.. code-block:: javascript

  it('has expected extent for Zoomify sources', function () {
    const sources = [
    getZoomifySource(),
    getZoomifySourceWithExtentInFirstQuadrant(),
    ];
    const expectedExtents = [
    [0, -size[1], size[0], 0],
    [0, 0, size[0], size[1]],
    ];
    for (let i = 0; i < sources.length; i++) {
    const tileGrid = sources[i].getTileGrid();
    expect(tileGrid.getExtent()).to.eql(expectedExtents[i]);
    }
  });

    it('has expected extent for IIP source', function () {
    const sources = [getZoomifySource(), getIIPSource()];
    for (let i = 0; i < sources.length; i++) {
    const tileGrid = sources[i].getTileGrid();
    const expectedExtent = [0, -h, w, 0];
    expect(tileGrid.getExtent()).to.eql(expectedExtent);
    }
  });

.. note::
  Test cases with identical descriptions can lead to confusion and make it harder to track individual test results. It is recommended to rename the tests to provide unique and descriptive titles.