LaTeX
=====

LON-CAPA supports the use of LaTeX to typeset mathematical expressions.

LaTeX can be written within the `<m></m>` tags. In order to display Perl variables in LaTeX, use `<m eval="on">$ *LaTeX with variables here* $</m>`.

Here are some examples of commonly used LaTeX commands.

| Purpose | Source | Output |
|---------|--------|:------:|
| Subscript | `range = y_{max} - y_{min}` | $$range = y_{max} - y_{min}$$ |
| Superscript (exponent) | `a^2 + b^2 = c^2` | $$a^2 + b^2 = c^2$$ |
| Fraction | `\frac{\pi}{2}` | $$\frac{\pi}{2}$$ |
| Large Parentheses | `\left( \frac{1}{2},\frac{3}{4} \right)` | $$\left( \frac{1}{2},\frac{3}{4} \right)$$ |
| Summation | `\sum_{i=0}^{n} i` | $$ \displaystyle \sum_{i=0}^{n} i $$ |
| Integral | `\int_{0}^{\infty} e^{t} dt` | $$ \displaystyle \int_{0}^{\infty} e^{t} dt $$ |
| Evaluation at limits | <code>\left.\frac{x^3}{3}\right&#124;_0^1</code> | $$\left.\frac{x^3}{3}\right|_0^1$$ |
| Case definitions | `f(n) = \begin{cases} \frac{n}{2}, & \text{if } n\text{ is even} \\ 3n+1, & \text{if } n\text{ is odd} \end{cases}` | $$ f(n) = \begin{cases} \frac{n}{2}, & \text{if } n\text{ is even} \\ 3n+1, & \text{if } n\text{ is odd} \end{cases} $$ |
| Matrices | `\begin{bmatrix} 0 & \cdots & 0 \\ \vdots & \ddots & \vdots \\ 0 & \cdots & 0 \end{bmatrix}` | $$ \begin{bmatrix} 0 & \cdots & 0 \\ \vdots & \ddots & \vdots \\ 0 & \cdots & 0 \end{bmatrix} $$ |

When including normal text in LaTeX, one should use the `\text{}` environment.

| Source | Output | Good? |
|--------|:------:|:-----:|
| `2 pies + 3 pies = 5 pies` | $$2 pies + 3 pies = 5 pies$$ | 👎 |
| `2 \text{ pies} + 3 \text{ pies} = 5 \text{ pies}` | $$2 \text{ pies} + 3 \text{ pies} = 5 \text{ pies}$$ | 👍 |
| `Let x = 5` | $$Let x = 5$$ | 👎 |
| `\text{Let } x = 5` | $$\text{Let } x = 5$$ | 👍 |

Spaces in LaTeX source code do not produce whitespace. In order to produce whitespace, one may use a whitespace command, such as `\,` or `\;`, or include a space character in a `\text{}` environment.

| Source | Output | Good? |
|--------|:------:|:-----:|
| `2 \text{apples}` | $$2 \text{apples}$$ | 👎 |
| `2   \text{apples}` | $$2    \text{apples}$$ | 👎 |
| `2 \, \text{apples}` | $$2 \, \text{apples}$$ | 👍 |
| `2 \; \text{apples}` | $$2 \; \text{apples}$$ | 👍 |
| `2 \text{ apples}` | $$2 \text{ apples}$$ | 👍 |

Greek letters and mathematical symbols have specific commands in LaTeX. Go [here](http://web.ift.uib.no/Teori/KURS/WRK/TeX/symALL.html) to find a full list of symbols. Below are examples of some commonly used symbols.

| Source | Output |
|--------|:------:|
| `0 \le 1, x \ge y, P \ne NP` | $$0 \le 1, x \ge y, P \ne NP$$ |
| `\forall x \forall y \exists z \, P(x) \wedge Q(y) \rightarrow R(z)` | $$\forall x \forall y \exists z \, P(x) \wedge Q(y) \rightarrow R(z)$$ |

#### HTML vs LaTeX

One might wonder when to use HTML and when to use LaTeX: after all, the two have overlapping features, such as creating tables and lists.

In general, LaTeX should be used for typesetting inline math expressions and creating math-related figures and HTML should be used for all other formatting.

For example, it is better to use the `matrix` and `cases` environments in LaTeX than to attempt to format similar figures using HTML and CSS. However, rather than creating a table using pure LaTeX, it may be better to create a table using HTML (`<table>`, `<tr>`, `<td>`). LaTeX may then be used in the contents of the table cells.
