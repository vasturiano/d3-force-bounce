d3.forceBounce
==============

[![NPM package][npm-img]][npm-url]
[![Build Size][build-size-img]][build-size-url]
[![NPM Downloads][npm-downloads-img]][npm-downloads-url]

An elastic collision force type for the d3-force simulation engine.

This force is similar to [d3.forceCollide](https://github.com/d3/d3-force#forceCollide), but allows for fully elastic collisions that [conserve kinetic energy](https://en.wikipedia.org/wiki/Momentum#Elastic_collisions). This makes <i>d3.forceCollide</i> appropriate for preventing the overlap of nodes, and <i>d3.forceBounce</i> better suited when the intent is to achieve an elastic collision effect, with varying degrees of elasticity (coefficient of restitution).

Here's a [visual comparison](https://observablehq.com/@vasturiano/collision-forces-comparison) between the two forces.

It can be used, for example to [simulate particle collisions](https://observablehq.com/@vasturiano/entropy) or in a [Newton's cradle](https://observablehq.com/@vasturiano/newtons-cradle).

See also [d3.forceSurface](https://github.com/vasturiano/d3-force-surface).

## Quick start

```js
import d3ForceBounce from 'd3-force-bounce';
```
or using a *script* tag
```html
<script src="//cdn.jsdelivr.net/npm/d3-force-bounce"></script>
```
then
```js
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

## ❤️ Support This Project

If you find this module useful and would like to support its development, you can [buy me a ☕](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=L398E7PKP47E8&currency_code=USD&source=url). Your contributions help keep open-source sustainable!
[![paypal](https://www.paypalobjects.com/en_US/i/btn/btn_donate_SM.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=L398E7PKP47E8&currency_code=USD&source=url)


[npm-img]: https://img.shields.io/npm/v/d3-force-bounce
[npm-url]: https://npmjs.org/package/d3-force-bounce
[build-size-img]: https://img.shields.io/bundlephobia/minzip/d3-force-bounce
[build-size-url]: https://bundlephobia.com/result?p=d3-force-bounce
[npm-downloads-img]: https://img.shields.io/npm/dt/d3-force-bounce
[npm-downloads-url]: https://www.npmtrends.com/d3-force-bounce
