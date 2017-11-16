# pierce

## Installation

```bash
npm install pierce
```

## Getting Started

I'll be compiling a lot of my commonly used machine learning, signal processing, and statistics JavaScript modules here for easy reference.

```javascript
var pierce = require('pierce');

// Statistics
var stat = pierce.stat;

var a = [
	[1, 5],
	[3, 2]
];

console.log(stat.cov(a)); // [ [ 2, -3 ], [ -3, 4.5 ] ] (Covariance matrix)
console.log(stat.mean(a)); // [ 2, 3.5 ] (Mean of each column)

// Machine learning
var LDA = pierce.lda;

var class1 = [
	[0, 1],
	[1, 2]
];
 
var class2 = [
	[8, 8],
	[9, 10]
];

var classifier = new LDA(class1, class2);

var unknownPoints = [
    [-1, 0],
    [7, 9]
];

console.log(classifier.project(unknownPoints[0])); // -98 (value less than 0 is class 1)
console.log(classifier.project(unknownPoints[1])); // 20 (value greater than 0 is class 2)

// Signal processing
var CSP = pierce.csp;

var a = [
	[-1, -1],
	[1, 1]
];

var b = [
	[-1, 1],
	[1, -1]
];

var csp = new CSP(a, b);

console.log(csp.project(a, 2)); // [ [ 1.414, 0 ], [ -1.414, 0 ] ]
console.log(csp.project(b, 2)); // [ [ 0, -1.414 ], [ 0, 1.414 ] ]
```
