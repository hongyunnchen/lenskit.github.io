---
title: Release 1.2
version: 1.2
milestone: 17
layout: release
---

-   Added `LenskitConfiguration` class and deprecated `LenskitRecommenderEngineFactory`.
    Use `LenskitRecommenderEngine.build()` to build an engine from a configuration.

-   Added `PreferenceDomainBuilder` to build preference domains.

-   `PreferenceDomain` now uses a precision of 0 to represent continuous scales (#issue(327));
    the value is still formally undefined behavior, but code which (incorrectly) depended on the
    precision when a domain does not have a precision may need to be corrected.

-   Implemented new `lenskit-groovy` module to load LensKit
    configurations from Groovy-based configuration files.  See the
    [config package JavaDoc](/apidocs/org/grouplens/lenskit/config/package-summary.html)
    for information on how to use this support.

-   `SparseVector` performance improvements, particularly for dot products.

    - Sparse vectors now expose `Pointer`s over their entries
      directly, allowing pointer-based access more efficiently than
      with `IteratorPointer`.

    - Pairwise iteration in `Vectors` uses direct pointers.

    - Dot products now use pairs of pointers directly, rather than
      indirectly using pairwise iteration.


