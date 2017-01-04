<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

# MathJax

MathJax ist eine JavaScript display engine, die die Verwendung von _LaTeX_ zur Darstellung kompexer mathematischer Formeln ermöglicht. Am Anfang einer Seite, die MathJax verwendet, muss dieser Code Javascript eingefügt werden:

```markdown
<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
```

So sieht ein Mathematik-Block aus:

```markdown
$$ 5 + 5 = 10 $$
```

$$ 5 + 5 = 10 $$

```markdown
$$ \forall x \in X, \quad \exists y \leq \epsilon $$
```

$$ \forall x \in X, \quad \exists y \leq \epsilon $$

Alternativ kann der Code auch inline mit dem restlichen Text gerendert werden:

```markdown
\$$ 1 + 1 = 2 $$
```

\$$ 1 + 1 = 2 $$

Hier gibt's die komplette Dokumenatation zu [MathJax und Latex](http://docs.mathjax.org/en/latest/tex.html) und hier ein [Wikibook zur Syntax](https://en.wikibooks.org/wiki/LaTeX/Mathematics).
