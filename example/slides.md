---
theme: ../../slidev-theme-behackl-kfu
author: Benjamin Hackl
presenterName: Benjamin Hackl
affiliation: Department of Mathematics and Scientific Computing @ University of Graz
mdc: true
---

# A _**Somewhat Long Title**_ for a Math Talk or Lecture

### Some Subtitle, Maybe Software | _**Conference**_ @ Place, Country

<template #extra>

Extra content: Joint work with [Some Colleague](#) and [Other Colleague](#)

</template>


---

# Powered by _**Slidev**_

Slidev is a slide maker and <span v-mark.yellow>presentation tool</span> designed for developers.

This theme, leaning on the CD of the University of Graz, has been created by [Benjamin Hackl](https://benjamin-hackl.at).

<p v-click>

To start a new presentation, simply start a new file `slides.md`
with a bit of content like

</p>
<div v-click="3">

```md {none|1-5|all}{lines: true, at: '+1'}
---
theme: path/to/slidev-theme-behackl-kfu
presenterName: Benjamin Hackl
affiliation: Department of Mathematics and Scientific Computing / University of Graz
---

# Fancy Main Title

### With Some Subtitle

```

</div>
<div v-click>

Then startup the preview server using

```bash
$ npx slidev
```

</div>

---

# Navigation

Hover on the bottom-left corner to see the navigation's controls panel

## Keyboard Shortcuts

|     |     |
| --- | --- |
| <kbd>space</kbd> / <kbd>tab</kbd> / <kbd>right</kbd> | next animation or slide |
| <kbd>left</kbd>  / <kbd>shift</kbd><kbd>space</kbd> | previous animation or slide |
| <kbd>up</kbd> | previous slide |
| <kbd>down</kbd> | next slide |


---

# Admonitions!

::admonition{kind="warning" title="Warning" icon="mdi:warning"}
here is something important!
::

::admonition{kind="danger" title="Very dangerous!" icon="mdi:skull"}
here is something dangerous!
::

::admonition{kind="info" title="Interesting ..." icon="mdi:info"}
here is something interesting!
::

::admonition{title="Uni Graz branding!" kind="kfu"}
Here is something KFU related!
::

::admonition{title="Defaults?"}
Let us also try and get some default values up and running?
::

---

# An Inequality ...

- Bóna--DeJonge-question $\iff a_n / C_n > a_{n+1} / C_{n+1}$ for $n\geq 3$
- After some further manipulations, this is equivalent to...

<v-click>
<block title="Proposition">

$a_n / C_n$ is decreasing for $n \geq 3$ if and only if
$$ F(n) := \sum_{k=1}^n k \sigma(k) (k^2 - 3n + 2) (2k^2 - n) \binom{2n}{n-k} < 0 $$
for $n \geq 5$.

</block>
</v-click>

---

# ... followed by __Asymptotics!__

<div style="font-size: 18px;">

- Split *binomial sums* into "central" and "tails" regions, <br>show
  contribution of tails is negligible
- Approximate $\binom{2n}{n-k}$ in "central" region, complete tails
- Mellin for integral representation; shift line of integration + collect residues

</div>

<decor class="top-15 right-40">
<mdi-compass />
</decor>

<block v-click title="Theorem (H.&ndash;Wagner, 2024)">

For $n \to \infty$, we have
$$ F(n) = \binom{2n}{n} \Big( -\frac{n^2}{8} + \frac{n}{24} + o(n) \Big) $$

</block>
<div v-click>

- **Not good enough!** No information about error -- can only
  say sequence is _eventually decreasing_...

</div>

---

# *__Act II__* -- `dependent_bterms` in SageMath

<v-clicks depth="2">

- **$B$-terms:** $O$-terms with explicit constant + validity point,
  e.g., $B_{n\geq 100}(42 n^3)$

- Package extends SageMath; assume $n\to\infty$:

  - Support for additional monomially bounded variable $n^\alpha \leq k \leq n^\beta$

  - Taylor expansions with (and at) $B$-terms


</v-clicks>

<div class="grid grid-cols-[2fr_1fr] gap-4">
<div>
<v-clicks at="5">

- Installation:
  ```sh
  $ sage -pip install dependent_bterms
  ```

- Try it! Interactive demo at [behackl.dev/asy/dbt](https://behackl.dev/asy/dbt), or
  view [static version](https://github.com/behackl/dependent_bterms/blob/main/toolbox_demo.ipynb)
  on GitHub

</v-clicks>
</div>
<div>
<decor v-click="5" class="bottom-30 right-30"><mdi-laptop/></decor>
</div>
</div>


---
layout: image-right
image: https://picsum.photos/900/600
---

# Code

Use code snippets and get the highlighting directly!

```py
def fibonacci(n):
    if n == 0:
        return 0
    if n == 1:
        return 1
    return fibonacci(n-1) + fibonacci(n-2)
```

---
layout: two-cols-header
---

This spans both columns, might only be evident if used
with a sufficiently long text?

::left::

This is a list in the left column.

- First item
- Second item
- Third item
- And final item

::right::

And this is right column. We could put a little
decoration element here?

<decor class="bottom-10 right-50"><mdi-flower/></decor>

---
layout: end
class: "text-center"
---

# Thank you!



