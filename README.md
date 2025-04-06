# CPFEH

Crystal Plasticity Finite Element Homogenization model for
[Dyalog APL](https://www.dyalog.com/)

## Example

    eg.apls

Expected output:

        grains      steps       ∆time       iter        iterc       seconds
            50          10   5.00E¯2           440         447        0.97
           100          10   5.00E¯2           410         418        2.46
           150          10   5.00E¯2           440         447        6.15
           200          10   5.00E¯2           440         447        8.34
           250          10   5.00E¯2           440         447       11.21
            50         100   5.00E¯2          4400        4407       24.53
            50         500   5.00E¯2         22000       22007      155.05
            50        1000   5.00E¯2         44000       44007      338.61   r.csv  tex.csv  f.csv

Timings (in the last column) may vary.
