# Lagrange's four-square calculator (Rust, WASM)

**This package is used for [four-square-sum](https://github.com/powergee/four-square-sum) project.**

**Lagrange's four-square theorem**, also known as **Bachet's conjecture**, states that *every natural number can be represented as the sum of four integer squares.* ([ref](https://en.wikipedia.org/wiki/Lagrange%27s_four-square_theorem))

This algorithm can calculate one of the below:
* **an arbitrary solution** of any non-negative integer *N* by **randomized polynomial time.**
* **an optimal solution**, which use the fewest numbers, of any non-negative integer *N* by the time complexity proportional to the fourth square root of *N*.

The randomized polynomial algorithm is [based on MICHAEL 0. RABIN et al.](https://onlinelibrary.wiley.com/doi/10.1002/cpa.3160390713)

## Usage

```rust
#[wasm_bindgen(js_name = findSolution)]
pub fn find_solution_str(n: String, find_optimal: bool) -> String {}
```

Import the function above into your applications.

```js
import init, { findSolution } from "four-square-sum-wasm";
init().then(() => {
    findSolution("1000", false); // ["6", "30", "8", "0"]
    findSolution("1000", true);  // ["10", "30", "0", "0"]
});
```

## Build

```bash
wasm-pack build --target web
```

## Test

```bash
wasm-pack test --chrome --headless
```

## Demostration and explanation

You can run the algorithm on [GitHub-Pages](https://powergee.github.io/four-square-sum/), which is implemented by React and Rust(Wasm). **There is also a short explanation about the background.**

## References

* [1] Rabin, M.O. and Shallit, J.O. (1986), Randomized algorithms in number theory. Comm. Pure Appl. Math., 39: S239-S256. [https://doi.org/10.1002/cpa.3160390713](https://doi.org/10.1002/cpa.3160390713)
* [2] Rabin, M. O., Efficient Algorithms, Lecture Notes MIT, 1977, transcribed by M. Lui.
* [3] Lagrange's four-square theorem, [https://en.wikipedia.org/w/index.php?title=Lagrange%27s_four-square_theorem&oldid=1070361127](https://en.wikipedia.org/w/index.php?title=Lagrange%27s_four-square_theorem&oldid=1070361127) (last visited Feb. 24, 2022).
* [4] Legendre's three-square theorem, [https://en.wikipedia.org/w/index.php?title=Legendre%27s_three-square_theorem&oldid=1030003352](https://en.wikipedia.org/w/index.php?title=Legendre%27s_three-square_theorem&oldid=1030003352) (last visited Feb. 24, 2022).
* [5] Fermat's theorem on sums of two squares, [https://en.wikipedia.org/w/index.php?title=Fermat%27s_theorem_on_sums_of_two_squares&oldid=1064865677](https://en.wikipedia.org/w/index.php?title=Fermat%27s_theorem_on_sums_of_two_squares&oldid=1064865677) (last visited Feb. 24, 2022).
* [6] Pollard's rho algorithm, [https://en.wikipedia.org/w/index.php?title=Pollard%27s_rho_algorithm&oldid=1044484908](https://en.wikipedia.org/w/index.php?title=Pollard%27s_rho_algorithm&oldid=1044484908) (last visited Feb. 24, 2022).
* [7] Brahmagupta–Fibonacci identity, [https://en.wikipedia.org/w/index.php?title=Brahmagupta%E2%80%93Fibonacci_identity&oldid=1072168983](https://en.wikipedia.org/w/index.php?title=Brahmagupta%E2%80%93Fibonacci_identity&oldid=1072168983) (last visited Feb. 24, 2022).