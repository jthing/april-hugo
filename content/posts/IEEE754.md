---
title: "IEEE754"
date: 2023-08-03T00:00:00+02:00
draft: false
---

## Half precision floating point {#half-precision-floating-point}

To fully support GPU programming April needs a new floating point formats.

In APL floating point is set by setting ⎕FR to a number representing the IEEE standard
number so ⎕FR←754 sets the precision to 16 bit floating point.
For more information see [Wikipedia](<https://en.wikipedia.org/wiki/Half-precision_floating-point_format>).
