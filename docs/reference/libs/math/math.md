---
layout: blog
title: Math
---
## Math

This module implements various mathematical functions.

Except when explicitly noted otherwise, all return values are floats. The underlying implementations works on double precision floats that are converted back to single precision if the VM does not support double precision.

No exceptions are raised: in case of error, the return value can be infinite or NaN. Such cases can be checked with the provided functions.

The following constants are defined:

* `pi` = 3.14159265
* `e`  = 2.71828182


### function `tan`
```python
tan(x)
```

Return the tangent of *x* radians.

### function `cos`
```python
cos(x)
```

Return the cosine of *x* radians.

### function `sin`
```python
sin(x)
```

Return the sine of *x* radians.

### function `atan2`
```python
atan2(y, x)
```

Return ``atan(y / x)``, in radians. The result is between ``-pi`` and ``pi``.
The vector in the plane from the origin to point ``(x, y)`` makes this angle
with the positive X axis. The point of `atan2` is that the signs of both
inputs are known to it, so it can compute the correct quadrant for the angle.
For example, ``atan(1)`` and ``atan2(1, 1)`` are both ``pi/4``, but ``atan2(-1,
-1)`` is ``-3*pi/4``.

### function `atan`
```python
atan(x)
```

Return the arc tangent of *x*, in radians.

### function `acos`
```python
acos(x)
```

Return the arc cosine of *x*, in radians.

### function `asin`
```python
asin(x)
```

Return the arc sine of *x*, in radians.

### function `degress`
```python
degress(rad)
```

Converts *rad* from radians to degrees.

### function `radians`
```python
radians(degree)
```

Converts *degree* from degrees to radians.

### function `exp`
```python
exp(x)
```

Return ``e**x``.

### function `log`
```python
log(x[, base])
```

With one argument or with *base* non positive, return the natural logarithm of *x* (to base *e*).

With two arguments, return the logarithm of *x* to the given *base*,
calculated as ``log(x)/log(base)``.

### function `pow`
```python
pow(x, y)
```

Return ``x`` raised to the power ``y``.

Unlike the built-in ``**`` operator, `math.pow` converts both
its arguments to type `float`.  Use ``**`` or the built-in
`pow` function for computing exact integer powers.

### function `sqrt`
```python
sqrt(x)
```

Return the square root of *x*.

### function `isnan`
```python
isnan(x)
```

Return ``True`` if *x* is a NaN (not a number), and ``False`` otherwise.

### function `isinf`
```python
isinf(x)
```

Return ``True`` if *x* is a positive or negative infinity, and
``False`` otherwise.

### function `floor`
```python
floor(x)
```

Return the floor of *x*, the largest integer less than or equal to *x*.

### function `ceil`
```python
ceil(x)
```

Return the ceiling of *x*, the smallest integer greater than or equal to *x*.

### function `trunc`
```python
trunc(x, n)
```

Return the value of *x* truncated to the *n* decimal.