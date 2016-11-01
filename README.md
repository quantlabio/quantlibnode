quantlib [![npm version](https://badge.fury.io/js/quantlib.svg)](http://badge.fury.io/js/quantlib)
========

QuantLib Async Bindings for Node.js

Getting started
---------------

```sh
npm install quantlib
```

Example
-------

```js
var ql = require('quantlib');

var mtx1 =
[
  [1.00000,	0.97560,	0.95240,	0.93040,	0.90940,	0.88940,	0.87040,	0.85230,	0.83520,	0.81880],
  [0.97560,	1.00000,    0.97560,    0.95240,    0.93040,    0.90940,    0.88940,    0.87040,    0.85230,    0.83520],
  [0.95240,	0.97560,	1.00000,	0.97560,	0.95240,	0.93040,	0.90940,	0.88940,	0.87040,	0.85230],
  [0.93040,	0.95240,	0.97560,	1.00000,	0.97560,	0.95240,	0.93040,	0.90940,	0.88940,	0.87040],
  [0.90940,	0.93040,	0.95240,	0.97560,	1.00000,	0.97560,	0.95240,	0.93040,	0.90940,	0.88940],
  [0.88940,	0.90940,	0.93040,	0.95240,	0.97560,	1.00000,	0.97560,	0.95240,	0.93040,	0.90940],
  [0.87040,	0.88940,	0.90940,	0.93040,	0.95240,	0.97560,	1.00000,	0.97560,	0.95240,	0.93040],
  [0.85230,	0.87040,	0.88940,	0.90940,	0.93040,	0.95240,	0.97560,	1.00000,	0.97560,	0.95240],
  [0.83520,	0.85230,	0.87040,	0.88940,	0.90940,	0.93040,	0.95240,	0.97560,	1.00000,	0.97560],
  [0.81880,	0.83520,	0.85230,	0.87040,	0.88940,	0.90940,	0.93040,	0.95240,	0.97560,	1.00000]
];

ql.SymmetricSchurDecomposition('mtx#1',mtx1).then(function(obj){

  ql.SymmetricSchurDecompositionEigenvalues(obj).then(function(r){
    console.log(r);
  });

}).catch(function(e){
  console.log(e);
});

```

```sh
>
[ 9.270906840163782,
  0.4207173234885105,
  0.12674770658244172,
  0.059239731356788505,
  0.03595303870722261,
  0.024956978505270924,
  0.019117669503864024,
  0.01580103250921176,
  0.01377474504269164,
  0.012784934140218302 ]
```
