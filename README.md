# flot
Quick, dirty convert between IEEE754 hex and f32/f64.

If the number contains a decimal point, convert float -> hex. Else, convert hex -> float.

Hex values are automatically padded to 8/16 characters (appended zeroes) before processing.

Warning: hardly any input validation.

```
Options:
   -a :   Autodetect and show one result.
            - If detected as hex:
                numbers of length <= 8 will be treated as 32b, else 64b.
            - If detected as float:
                use the 'f' suffix to treat as single, else treated as double.

   -p :   Print float values with guaranteed precision
            - 9  sig figs printed for float
            - 17 sig figs printed for double

Examples:  flot 3f8
           flot 0x4200000000000000
           flot 1.2
           flot -a 3f8         (treated as 32b)
           flot -a 4014000000  (treated as 64b)
           flot -a 3.5f        (treated as single)
           flot -a 1.2         (treated as double)
```
