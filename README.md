# MJIT-benchmarks

Port of micro benchmark set in [vnmakarov/ruby/MJIT-benchmarks](https://github.com/vnmakarov/ruby/tree/rtl_mjit_branch/MJIT-benchmarks)
for benchmark\_driver.gem

## Usage

`bin/bench` is a wrapper of `benchmark-driver` command.

See `benchmark-driver -h` (or `bin/bench -h`) for available options.

```
$ bin/bench benchmarks/aread.yml --rbenv 'trunk;mjit,-j;yarv-mjit,-j'
Calculating -------------------------------------
                          trunk        mjit   yarv-mjit
               aread    51.799     261.759     101.217  i/s -      1.000k in 19.305428s 3.820305s 9.879750s

Comparison:
        aread (mjit):       261.8 i/s
   aread (yarv-mjit):       101.2 i/s - 2.59x  slower
       aread (trunk):        51.8 i/s - 5.05x  slower
```

### Results

Here is result of `bin/bench -o markdown --rbenv '2.0.0-p0;2.5.0-rc1;yarv-mjit,-j;mjit,-j' benchmarks/*` on my environment.

|           |2.0.0-p0   |2.5.0-rc1  |yarv-mjit  |mjit       |
|:----------|:----------|:----------|:----------|:----------|
|aread      |1.00       |1.01       |2.49       |11.52      |
|aref       |1.00       |0.98       |3.58       |18.27      |
|aset       |1.00       |1.34       |3.40       |18.19      |
|awrite     |1.00       |1.10       |2.72       |10.52      |
|call       |1.00       |1.33       |3.54       |5.00       |
|const      |1.00       |0.97       |3.87       |16.06      |
|const2     |1.00       |1.05       |4.12       |16.69      |
|fannk      |1.00       |1.03       |1.00       |0.89       |
|fib        |1.00       |1.31       |3.10       |3.68       |
|ivread     |1.00       |0.94       |4.78       |11.57      |
|ivwrite    |1.00       |1.08       |3.10       |11.23      |
|mandelbrot |1.00       |0.94       |1.25       |1.67       |
|meteor     |1.00       |3.02       |3.22       |4.01       |
|nbody      |1.00       |1.05       |1.63       |2.43       |
|nest-ntimes|1.00       |1.06       |1.37       |2.06       |
|nest-while |1.00       |0.97       |1.63       |3.13       |
|norm       |1.00       |1.07       |1.04       |2.37       |
|nsvb       |1.00       |0.93       |0.88       |1.00       |
|sieve      |1.00       |1.22       |1.79       |2.41       |
|trees      |1.00       |1.17       |1.47       |2.02       |
|while      |1.00       |0.96       |4.17       |50.89      |

## License

Copyright (C) 2017 Vladimir Makarov <vmakarov@redhat.com>.

See [COPYING](./COPYING) too.
