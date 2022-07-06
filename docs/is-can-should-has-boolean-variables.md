# Use is-/can-/should-/has- prefixes when naming boolean variables

Variables with boolean values are frequently used as "flags" to vary the output of a template via conditional statements or ternary expressions.

By prefixing boolean variable names with is-/can-/should-/has- we can make our code more natural language-like, increasing readability.

Avoid:

```twig
{% for page in pages %}
  {% set current = currentPage.index == page.index %}
  <li class="bg-white inline-block p-2 text-center {{ current ? 'font-bold'}}">
    {{ page.label }}
  </li>
{% endfor %}
```

Instead:

```twig
{% for page in pages %}
  {% set isCurrent = currentPage.index == page.index %}
  <li class="bg-white inline-block p-2 text-center {{ isCurrent ? 'font-bold'}}">
    {{ page.label }}
  </li>
{% endfor %}
```


