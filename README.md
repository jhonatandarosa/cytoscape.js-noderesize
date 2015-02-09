cytoscape-noderesize
================================================================================


## Description

A plugin that creates a node resize control, based on https://github.com/cytoscape/cytoscape.js-edgehandles


## Dependencies

 * Cytoscape.js >=2.3.8
 * jQuery >= 1.4


## Usage instructions

Download the library:
 * via npm: `npm install cytoscape-noderesize`,
 * via bower: `bower install cytoscape-noderesize`, or
 * via direct download in the repository (probably from a tag).

`require()` the library as appropriate for your project:

CommonJS:
```js
var cytoscape = require('cytoscape');
var noderesize = require('cytoscape-noderesize');

noderesize( cytoscape ); // register extension
```

AMD:
```js
require(['cytoscape', 'cytoscape-noderesize'], function( cytoscape, noderesize ){
  noderesize( cytoscape ); // register extension
});
```

Plain HTML/JS has the extension registered for you automatically, because no `require()` is needed.


## API

Please briefly describe your API here:

```js
cy.noderesize({
  handleColor: '#000000', // the colour of the handle and the line drawn from it
  hoverDelay: 150, // time spend over a target node before it is considered a target selection
  enabled: true, // whether to start the plugin in the enabled state
  minNodeWidth: 30,
  minNodeHeight: 30,
  triangleSize: 10,
  lines: 3,
  padding: 5,

  start: function(sourceNode) {
    // fired when noderesize interaction starts (drag on handle)
  },
  complete: function(sourceNode, targetNodes, addedEntities) {
    // fired when noderesize is done and entities are added
  },
  stop: function(sourceNode) {
    // fired when noderesize interaction is stopped (either complete with added edges or incomplete)
  }
});
```
