# motion-benchmark

This is benchmark library for RubyMotion.
This library provides methods to measure and report the time used to execute your code.

## Installation

```
$ [sudo] gem install motion-benchmark
```

## Usage

This gem can be used in `Rakefile` of your RubyMotion project by requiring.

```
require 'rubygems'
require 'motion-benchmark'
```

And then, you would write the code to measure, like:

```
n = 50000
Benchmark.bm do |x|
  x.report { for i in 1..n; a = "1"; end }
  x.report { n.times do   ; a = "1"; end }
  x.report { 1.upto(n) do ; a = "1"; end }
end
```

This library provides the same APIs as standard Ruby.
You could see the APIs references at [http://ruby-doc.org/stdlib-1.9.3/libdoc/benchmark/rdoc/Benchmark.html](http://ruby-doc.org/stdlib-1.9.3/libdoc/benchmark/rdoc/Benchmark.html)

## Tips

### Run with Release mode

When you run your app on simulator with `rake` command, its benchmark result might show slow performance because it is not optimized when compiled the app.

You could enable optimization with `rake mode=release`.


### Run on iOS device

You could see benchmark result of your app which is running on iOS device with `rake device debug=1` or `rake device mode=release debug=1`.

