# CPFEH

Crystal Plasticity Finite Element Homogenization model for
[Dyalog APL](https://www.dyalog.com/)

## Example

    eg.apls

Expected output:

        grains      steps       ∆time       iter        iterc       seconds
            50          10   5.00E¯2           440         447        2.03
           100          10   5.00E¯2           510         518        3.46
           150          10   5.00E¯2           580         587        6.80
           200          10   5.00E¯2           640         647        9.87
           250          10   5.00E¯2           740         747       16.69
            50         100   5.00E¯2          8000        8007       42.60
            50         500   5.00E¯2         43500       43507      220.02
            50        1000   5.00E¯2         94000       94007      539.99   r.csv  tex.csv  f.csv

Timings (in the last column) may vary.
