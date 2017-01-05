Problem Structure
========

Problems in LON-CAPA are written in XML. XML stands for **Extensible Markup Language**.

## Tags

XML elements are defined by tags. All tags begin with `<` and close with `>`. Most XML elements have an opening and closing tag; some elements only have one tag. Different tags have different functionality.

### Attributes

Attributes are tag modifiers: they have a `name` and a `value`. They follow this syntax:

```html
<tag name="value"> <!-- list attributes in opening tag only -->
</tag>
```

Attributes are critically important to many XML elements. For example, attributes specify the properties of `responses` in LON-CAPA problems. HTML elements also use attributes to specify display properties as well as resource paths (`src="<path-to-resource>"`).

## Common Tags

#### `<problem>` `</problem>`

- Begin and end a problem.

#### `<startouttext/>` `<endouttext/>`

- Used to display text. HTML written within these tags is displayed to students.

#### `<script type="loncapa/perl">` `</script>`

- Used for Perl scripting. Perl written within these tags adds functionality to a problem. For example, Perl variables with randomized values are used to create dynamic problems.

#### `<m>` `</m>`

- Used for writing LaTeX to typeset mathematical expressions. Read the [LaTeX section](/docs/loncapa/latex.md) for more information.

## Example

A simple example problem is as follows:

```xml
<!-- Problem -->
<problem>

<!-- Perl script -->
<script type="loncapa/perl">
$a = 2;
$ans = 3;
</script>

<!-- Display text -->
<startouttext/>
<!-- HTML and LaTeX -->
<p>Evaluate <m eval="on">$ 1 + $a $</m>.</p>
<endouttext/>

<!-- Response with Perl variable -->
<numericalresponse answer="$ans">
    <textline readonly="no" spellcheck="none"/>
</numericalresponse>

</problem>
```
