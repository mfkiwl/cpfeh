# CPFEH

Crystal Plasticity Finite Element Homogenization model for
[Dyalog APL](https://www.dyalog.com/)

## Example

    eg.apls

Expected output:

        grains      steps       ∆time       iter        iterc       seconds
            50          10   5.00E¯2           440         445        1.38
           100          10   5.00E¯2           410         414        1.84
           150          10   5.00E¯2           440         445        4.59
           200          10   5.00E¯2           440         445        6.38
           250          10   5.00E¯2           440         445        8.71
            50         100   5.00E¯2          4341        5262       21.24
            50         500   5.00E¯2         21499       26020      112.33
            50        1000   5.00E¯2         43707       52728      230.37   r.csv  tex.csv  f.csv

Timings (in the last column) may vary.
