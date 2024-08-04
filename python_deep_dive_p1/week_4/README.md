# 4. Numeric Types
We have 4 types of numbers in python
1. `(int)`Integer $\mathbb{Z}$ - $\{\pm1, \pm2, \pm3, ..\}$
2. `(fractions.Fraction)`Rational $\mathbb{Q}$ - $\{\dfrac{p}{q} | p, q \in \mathbb{Z}, q \neq 0\}$
3. `(float)` or `decimal.Decimal`Real $\mathbb{R}$
4. `(complex)`Real $\mathbb{C}$
5. `(bool)` Boolean, 0 or 1

## Int Data type
- Integers are represented using base 2 (binary) digits.
- The int object in Python uses variable number of bits (32, 64, 96 etc.)

```python
# check data type
print(type(100))

# check number of bytes
import sys

sys.getsizeof(100) # overhead
```

## Arithmetic Operations
- `int / int` returns a `float`
- `%` returns `remainder` - modulo operator 
- `//` means floor division