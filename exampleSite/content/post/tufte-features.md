+++
author = "AUTHOR NAME"
date = "2016-02-20T13:56:01-08:00"
meta = true
math = true
title = "Hugo-Tufte Features"
subtitle = "Fancy Subtitle"
toc = true
categories = ["katex", "latex", "tufte-css"]


+++

This is a quick demonstration post.  It serves as an example of the features
of this theme.  One of them is $ \LaTeX $ via [Katex](https://katex.org/). 
{{< section "begin" >}}
## A Bit About Mathematics

{{< epigraph pre="Shawn O'Hare, " cite="Math is Fun" >}}
This is an example of an epigraph with some math
$ \mathbb N \subseteq \mathbb R $
to start the beginning of a section.
{{< /epigraph >}}

<!--more-->

### Inline
Some inline math:
{{< marginnote "mn-example" >}}This is a margin note.{{< /marginnote >}}
$e^{i \pi} = -1$
 and $\sqrt{-1} = i $
and $ a_2 = 3 $.

### Display
And display math using this symbol `$$`:
{{< sidenote "sn-example" >}}This is a sidenote!{{< /sidenote >}}
$$
  -- \cdot_H -- \colon B(G,H) \times B(H, K) \to B(G, K), \quad ([X], [Y]) \mapsto [X \times_H Y].
$$

### Environments

Currently, certain $\LaTeX$ environments need to be escaped so that
the markdown processor does not override Katex.  Currently, display
environments should be enclosed in `<p>` tags and blank lines.
For instance:

<p>
$$
\begin{aligned}  
  \mu(A) &= \iint_{I^2} \chi_A (x,y) \ d(x,y) 
  = \int_I \left( \int_I  \chi_A (x,y) \ dx\right) dy 
  = \int_I 0 \ dy= 0 \quad \text{and} \\  
  \mu(A) &=\iint_{I^2}  \chi_A (x,y) \ d(x,y) 
  = \int_I \left(  \int_I \chi_A (x,y) \ dy \right) dx 
  =\int_I dx = 1,
\end{aligned} 
$$
</p>
<!-- See https://github.com/jgm/pandoc/issues/3953#issuecomment-334670625 -->

is produced from

```txt
<p>
$$
\begin{aligned}  
  \mu(A) &= \iint_{I^2} \chi_A (x,y) \ d(x,y) 
  = \int_I \left( \int_I  \chi_A (x,y) \ dx\right) dy 
  = \int_I 0 \ dy= 0 \quad \text{and} \\  
  \mu(A) &=\iint_{I^2}  \chi_A (x,y) \ d(x,y) 
  = \int_I \left(  \int_I \chi_A (x,y) \ dy \right) dx 
  =\int_I dx = 1,
\end{aligned} 
$$
</p>
```

### Blockquotes
Some blockquotes.  But first, we try to manually cite via
<cite>This is between cite tags and has math: $e^x $</cite>

{{< blockquote cite="www.shawnohare.com" footer="Shawn O'Hare" >}}
This is a blockquote with two paragraphs, that employs the
theme's `blockquote` shortcode. Lorem ipsum dolor sit amet,
consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
id sem consectetuer libero luctus adipiscing.
Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
{{< /blockquote >}}

### New thoughts

<span class="newthought">Sometimes a new thought</span> distinguishes a section,
as here.  There are currently two ways to create one.  One way is with raw
HTML such as: `<span class="newthought">...</span>"`.  The theme also provides
the `newthought` shortcode.

### Code
As an example of some inline code: `go test -v -short`.
And this is some block-code:
```go {linenos=table,hl_lines=["2-5"],linenostart=199}
package main

import "log"

func add(x int, y int) int {
  log.Println("We are going to take the sum of two numbers, and leave a long comment.")
  return x + y
}

func main() {
  y := add(1, 2)
  log.Println(y)
}
```

Here's an example without line numbers. 
```go {hl_lines=["2-5"],linenostart=199}
package main

import "log"

func add(x int, y int) int {
  log.Println("We are going to take the sum of two numbers, and leave a very very very long comment.")
  return x + y
}

func main() {
  y := add(1, 2)
  log.Println(y)
}
```

### Figure
Below we have an example of a regular width figure.
{{< figure
  src="https://github.com/edwardtufte/tufte-css/raw/gh-pages/img/exports-imports.png"
  class="class param"
  title="The image title."
  caption="This is the image caption."
  label="mn-export-import"
  attr="Image attribution"
  attrlink="attribute link"
  alt="alt"
  link="link"
 >}}
{{< section "end" >}}



{{< figure
  src="https://edwardtufte.github.io/tufte-css/img/rhino.png"
  class="class param"
  type="margin"
  label="mn-rhino"
  title="The image title."
  label="mn-export-import"
  caption="This is the image caption."
  attr="Image attribution"
  attrlink="https://edwardtufte.github.io/tufte-css"
  alt="alt"
  link="link"
 >}}
 But tight integration of graphics with text is central to Tufte’s work even when those graphics are ancillary to the main body of a text. In many of those cases, a margin figure may be most appropriate.
{{< section "end" >}}

Below is a full-width figure.
{{< figure
  src="https://edwardtufte.github.io/tufte-css/img/napoleons-march.png"
  type="full"
  label="mn-napoleonic-wars"
  title="Napoleonic wars"
  caption="This the image caption."
  attr="Image attribution"
  attrlink="attribute link"
  alt="Napoleonic wars"
  link="link"
 >}}
{{< section "end" >}}
