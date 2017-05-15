# d3.forceBounce

[![NPM](https://nodei.co/npm/d3-force-bounce.png?compact=true)](https://nodei.co/npm/d3-force-bounce/)

An elastic collision force type for the d3-force simulation engine.

## Quick start

```
import d3ForceBounce from '3d-force-bounce';
```
or
```
d3.forceBounce = require('3d-force-bounce');
```
or even
```
<script src="//unpkg.com/3d-force-bounce/dist/3d-force-bounce.min.js"></script>
```
then
```
d3.forceSimulation()
    .nodes(<myNodes>)
    .force('bounce', d3.forceBounce()
        .radius(5)   
    );
```

## API reference

| Method | Description | Default |
| ------------------ | -------------------------------------------------------------------------------------------------------------------------- | ------------- |
| <b>elasticity</b>([<i>number</i>]) | Getter/setter for every collision's <i>coefficient of restitution</i>, aka <i>elasticity</i>. A value of `1` represents a purely elastic collision with no energy loss, while a `0` will fully eliminate the bounce in the collision direction. Values `>1` can be used to introduce acceleration at each collision. Values `<0` are not recommended. | 1 |
| <b>radius</b>([<i>num</i> or <i>fn</i>]) | Getter/setter for the node object radius accessor function (`fn(node)`) or a constant (`num`) for all nodes. | 1 |
| <b>mass</b>([<i>num</i> or <i>fn</i>]) | Getter/setter for the node object mass accessor function (`fn(node)`) or a constant (`num`) for all nodes. Mass affects the symmetry of the energy transfer between two colliding nodes. By default it is proportional to the node's area. | `Math.pow(radius(node), 2)` |
| <b>onImpact</b>([<i>fn</i>]) | Callback function triggered at every collision, with the signature `onImpact(node1, node2)`  ||

## Local development

```
npm install
npm run watch
```
