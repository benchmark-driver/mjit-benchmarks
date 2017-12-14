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

## License

Copyright (C) 2017 Vladimir Makarov <vmakarov@redhat.com>.

See [COPYING](./COPYING) too.
