---
theme: ../../slidev-theme-behackl-kfu
author: Benjamin Hackl
---

# A __Somewhat Long Title__ for a *Math Talk* or *Lecture*

#### Benjamin Hackl


---

# Powered by __Slidev__

Slidev is a slide maker and <span v-mark.red>presentation tool</span> designed for developers. It includes the following features:

<v-clicks>

- **Text-based** - focus on your content with Markdown, then style it later
- **Themable** - themes can be shared and reused as npm packages
- **Developer Friendly** - code highlighting, live coding with autocompletion
- **Interactive** - embed Vue components to enhance your expressions

</v-clicks>

<br>
<br>

Read more about [Why Slidev?](https://sli.dev/guide/why)

---

# ... to an Inequality ...

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

<block title="Theorem (H.&ndash;Wagner, 2024)">

For $n \to \infty$, we have
$$ F(n) = \binom{2n}{n} \Big( -\frac{n^2}{8} + \frac{n}{24} + o(n) \Big) $$

</block>

- **Not good enough!** No information about error -- can only
  say sequence is _eventually decreasing_...

---

# __Act II__ -- `dependent_bterms` in SageMath

- **$B$-terms:** $O$-terms with explicit constant + validity point,
  e.g., $B_{n\geq 100}(42 n^3)$ 
- Package extends SageMath; assume $n\to\infty$:
  - Monomially bounded variable $n^\alpha \leq k \leq n^\beta$
  - Taylor expansions with (and at) $B$-terms


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
layout: center
class: "text-center"
---

# Learn More

[Documentation](https://sli.dev) / [GitHub Repo](https://github.com/slidevjs/slidev)



