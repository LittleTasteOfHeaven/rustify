### gcd_bitwise

**Disclaimer: The code is not mine.**

The code is part of the [coreutils](https://github.com/uutils/coreutils/blob/15da98d84e9a094ea72c5f51efcc2d8aa9e9184f/src/uu/factor/src/numeric/gcd.rs) project. I have forked it for ease of use, for those who dont want to pull in big dependencies for calculating gcd.

**Some notes:** This code uses stein's algorithm, that replaces division with arithmetic shifts, comparisons, and subtraction, for optimization of performance. For more info on how efficient this algorithm is, please refer to [this](https://en.wikipedia.org/wiki/Binary_GCD_algorithm#Efficiency), as it is complex to explain in short.

### Quick Start
```rust
use gcd_bitwise::interface::GcdBuilder;

fn main() {
    let num1 = 15;

    let num2 = 51;
     
    let gcd = GcdBuilder::new(num1, num2);
     
    let gcd = gcd.build();
     
    println!("gcd: {}", gcd); // 3   
}
```