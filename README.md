### ruby-stacktrace

Have you ever wanted to know what your Ruby program is doing?
`ruby-stacktrace` can tell you! Maybe.

**this is alpha, Linux-only software**. It will very likely crash. If it
crashes, the rest of your system should be fine (it shouldn't crash your
Ruby)

### How to use it

1. Download recent release of `ruby-stacktrace` (download from [here](https://github.com/jvns/ruby-stacktrace/releases))
1. Find the PID of the Ruby process you want to investigate (like 7723)
1. run `sudo ./ruby-stacktrace top 7723`
1. It'll either work (and tell you which functions are being the most)
   or crash
1. I would not run this on a production system today, but I don't know
   of any specific reason you shouldn't (other than that it's sketchy
   alpha software)

If it crashes, you can file an issue and attach the Ruby binary for the
process it couldn't spy on. I have approximately no time to fix issues,
so I will probably not fix the bug. Pull requests are very welcome!

### Requirements

1. Linux (It uses a Linux-only system call)
2. A recent release of `ruby-stacktrace` (download from [here](https://github.com/jvns/ruby-stacktrace/releases))
3. A Ruby version compiled with debugging symbols (check by running
   `file` on your Ruby binary)

I've tested this succesfully on Ruby versions 2.1.6 and 2.2.3. No
promises though.

### Developing ruby-stacktrace


1. Install cargo from [crates.io](https://crates.io/)
1. `cargo build` to build
1. `cargo test` to test
1. `cargo bench` for benchmarks

The build artifacts will end up in `target/release`

### Authors

(in alphabetical order)

* Julia Evans
* Kamal Marhubi