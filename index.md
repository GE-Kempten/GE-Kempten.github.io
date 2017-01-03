<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

# Willkommen

Auf diesem Wiki werden Notizen zu Modulen des Studiengangs Informatik Game Engineering an der Hochschule Kempten gesammelt.

|1. Semester                            |
|---------------------------------------|
|[Lineare Algebra & Analytische Geometrie](/1/lineare-algebra-und-analytische-geometrie)|
|[IT Systeme](/1/it-systeme)|
|[Einführung in die Informatik](/1/einfuehrung-in-die-informatik)|
|[Modellierung und Animation](/1/modellierung-und-animation)|
|[Programmieren 1 (für Games)](/1/programmieren-1-fuer-games)|

Alle Beiträge stehen unter der [Creative Commons BY-NC-SA 4.0 International Lizenz](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.de).

## So funktioniert's

Die Website ist aus Markdown-Dateien aufgebaut wird kann über [GitHub](https://github.com/GE-Kempten/Wiki/edit/master/index.md) bearbeitet werden.

Immer wenn ein neuer Commit in diesem Repository erscheint, wird diese Seite duch [Jekyll](https://jekyllrb.com/) aktualisiert.

### Markdown

Markdown ist eine Markup-Language mit einer sehr einfachen Syntax. Funktionen sind unter anderem:

```markdown
Code Blocks mit Syntax Highlighting beginnen und enden mit drei Backticks (`)

# Überschrift 1
## Überschrift 2
### Überschrift 3

1. Nummerierte
2. Liste

- Liste
- mit
- Aufzählungszeichen

**Fett**
_Kursiv_
`Code`

| Das      | ist      | eine    |
|:--------:|---------:|---------|
| wirklich | tolle    | Tabelle |

[Link](url)

![Bild](src)
```

Hier gibt's noch mehr Informationen zu [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### MathJax

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
