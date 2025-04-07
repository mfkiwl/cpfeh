# CPFEH

Crystal Plasticity Finite Element Homogenization model for
[Dyalog APL](https://www.dyalog.com/)

## Example

    eg.apls

Expected output:

        grains      steps       ∆time       iter        iterc       seconds
            50          10   5.00E¯2           410         413        1.10
           100          10   5.00E¯2           390         393        1.72
           150          10   5.00E¯2           410         413        4.81
           200          10   5.00E¯2           410         413        6.74
           250          10   5.00E¯2           410         413        9.06
            50         100   5.00E¯2          3972        4292       19.91
            50         500   5.00E¯2         19245       21493      103.64
            50        1000   5.00E¯2         37894       42642      181.07   r.csv  tex.csv  f.csv

Timings (in the last column) may vary.
