<!--

@license Apache-2.0

Copyright (c) 2026 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# erfinvf

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Evaluate the [inverse error function][inverse-error-function] for a single-precision floating-point number.

<section class="intro">

The [inverse error function][inverse-error-function] is defined in terms of the [Maclaurin series][maclaurin-series]

<!-- <equation class="equation" label="eq:inverse_error_function" align="center" raw="\operatorname{erf}^{-1}(z)=\sum_{k=0}^\infty\frac{c_k}{2k+1}\left (\frac{\sqrt{\pi}}{2}z\right )^{2k+1}" alt="Inverse error function."> -->

```math
\mathop{\mathrm{erf}}^{-1}(z)=\sum_{k=0}^\infty\frac{c_k}{2k+1}\left (\frac{\sqrt{\pi}}{2}z\right )^{2k+1}
```

<!-- </equation> -->

where `c_0 = 1` and

<!-- <equation class="equation" label="eq:inverse_error_function_series_coefficients" align="center" raw="c_k=\sum_{m=0}^{k-1}\frac{c_m c_{k-1-m}}{(m+1)(2m+1)} = \left\{1,1,\frac{7}{6},\frac{127}{90},\frac{4369}{2520},\frac{34807}{16200},\ldots\right\}" alt="Series coefficients."> -->

```math
c_k=\sum_{m=0}^{k-1}\frac{c_m c_{k-1-m}}{(m+1)(2m+1)} = \left\{1,1,\frac{7}{6},\frac{127}{90},\frac{4369}{2520},\frac{34807}{16200},\ldots\right\}
```

<!-- </equation> -->

</section>

<!-- /.intro -->



<section class="usage">

## Usage

```javascript
import erfinvf from 'https://cdn.jsdelivr.net/gh/stdlib-js/math-base-special-erfinvf@deno/mod.js';
```

#### erfinvf( x )

Evaluates the [inverse error function][inverse-error-function] for a single-precision floating-point number.

```javascript
var y = erfinvf( 0.5 );
// returns ~0.4769

y = erfinvf( 0.8 );
// returns ~0.9062

y = erfinvf( -1.0 );
// returns -Infinity

y = erfinvf( 1.0 );
// returns Infinity
```

The domain of `x` is restricted to `[-1,1]`. If `|x| > 1`, the function returns `NaN`.

```javascript
var y = erfinvf( -3.14 );
// returns NaN
```

If provided `NaN`, the function returns `NaN`.

```javascript
var y = erfinvf( NaN );
// returns NaN
```

The [inverse error function][inverse-error-function] is an [odd function][odd-function] (i.e., `erfinvf(-x) = -erfinvf(x)`). Thus, in accordance with the [IEEE 754][ieee754] standard, if provided `-0`, the function returns `-0`.

```javascript
var y = erfinvf( -0.0 );
// returns -0.0
```

</section>

<!-- /.usage -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```javascript
import uniform from 'https://cdn.jsdelivr.net/gh/stdlib-js/random-array-uniform@deno/mod.js';
import logEachMap from 'https://cdn.jsdelivr.net/gh/stdlib-js/console-log-each-map@deno/mod.js';
import erfinvf from 'https://cdn.jsdelivr.net/gh/stdlib-js/math-base-special-erfinvf@deno/mod.js';

var opts = {
    'dtype': 'float32'
};
var x = uniform( 100, -1.0, 1.0, opts );

logEachMap( 'x: %0.4f, erfinvf(x): %0.4f', x, erfinvf );
```

</section>

<!-- /.examples -->

<!-- C interface documentation. -->



<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

</section>

<!-- /.related -->

<!-- Section for links. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## Copyright

Copyright &copy; 2016-2026. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/math-base-special-erfinvf.svg
[npm-url]: https://npmjs.org/package/@stdlib/math-base-special-erfinvf

[test-image]: https://github.com/stdlib-js/math-base-special-erfinvf/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/math-base-special-erfinvf/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/math-base-special-erfinvf/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/math-base-special-erfinvf?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/math-base-special-erfinvf.svg
[dependencies-url]: https://david-dm.org/stdlib-js/math-base-special-erfinvf/main

-->

[chat-image]: https://img.shields.io/badge/zulip-join_chat-brightgreen.svg
[chat-url]: https://stdlib.zulipchat.com

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/math-base-special-erfinvf/tree/deno
[deno-readme]: https://github.com/stdlib-js/math-base-special-erfinvf/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/math-base-special-erfinvf/tree/umd
[umd-readme]: https://github.com/stdlib-js/math-base-special-erfinvf/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/math-base-special-erfinvf/tree/esm
[esm-readme]: https://github.com/stdlib-js/math-base-special-erfinvf/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/math-base-special-erfinvf/blob/main/branches.md

[inverse-error-function]: https://en.wikipedia.org/wiki/Error_function#Inverse_functions

[maclaurin-series]: http://mathworld.wolfram.com/MaclaurinSeries.html

[odd-function]: https://en.wikipedia.org/wiki/Even_and_odd_functions

[ieee754]: https://en.wikipedia.org/wiki/IEEE_754-1985

<!-- <related-links> -->

<!-- </related-links> -->

</section>

<!-- /.links -->
