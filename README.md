# complex.lua

*Version 0.1*

*complex.lua* is a small Lua ligrary that implements complex numbers. It started as an [answer on Code Review Stack Exchange](/home/alexander/sources/FormatterII/README.md).

## Usage:
- `complex = require 'complex` — require the library,
- `complex.IMAGINARY_CHAR = 'j'` — use electrical notation for serialisation,
- `complex.PREFIX = true` — use *i*/*j* as a prefix for serialisation,
- `complex.PARENTHESES = true` — serialise complex numbers in parentheses,
- `i = complex.i` — set *i*,
- `complex (re, im)` will return the complex number with real part `re` and imaginary part `im`,
- `z = complex (re, im); z1 = complex (z)` will copy `z` to `z1`,
- `z.r` and `z.i` are real and imaginary parts of `z`, respectively,
- `z.conjugate ()` — complex conjugation,
- `+`, `-`, `*` and `/` operators work as expected; both Lua (real) numbers and complex number can be operands: `local z = 1 + complex.i`, `local z = complex.i + 1`, `local z = complex (1, 0) + complex.i` will set `z` to the same value,
- unary `-` will work as expected,
- `==` will work as expected,
- `<` will give a correct result when both operands are real. In addition, it will return true only if the real parts of operands are equal and the imaginary part of the first one is less than that of the secon one, which can facilitate sorting,
- `complex:abs ()` — the absolute value,
- `complex:arg ()` — the argument,
- `complex:abs2 ()` — the absolute value squared,
- `complex.polar (abs, arg)` — return a complex number with the absolute value of `abs` and argument of `arg`,
- `complex:exp ()` — exponent of a complex number,
- `x ^ y` will return a complex number, if either Euler's or de Moivre's formula is applicable, i.e., if either the first operand is positive number, or the second argument is real integer,
- `tostring (x)` will serialise the complex number rather prettily (e.g., `5 - 5i`, `-5i` or `5`) subject to `complex.IMAGINARY_CHAR`, `complex.PREFIX` and `complex.PARENTHESES`.

## Requirements
- Lua 5.1, 5.2, 5.3, 5.4 or LuaJIT.

# Credits
*complex.lua* is written by Alexander Mashin in 2020 and 2024, originally as a rework of the [code](https://codereview.stackexchange.com/q/252982/230923) written by [Nick](https://codereview.stackexchange.com/users/77934/nick). *Lua* is created by Roberto Ierusalimschy. *lrexlib* is written by Reuben Thomas and Shmuel Zeigerman.
