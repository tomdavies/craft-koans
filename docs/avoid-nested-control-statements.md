# Avoid nested control statements

Code with nested control statements tends to be harder to read, as it requires the reader to keep track of more state when reading.

Look to flatten your conditionals and other control statements where sensibly possible.

Avoid:

```twig
{% if currentUser %}
  {% if currentUser.can('doSomething') %}
    <a href="/do-something">Do something</a>
  {% elseif currentUser.can('doAnotherThing') %}
    <a href="/do-another-thing">Do something else</a>
  {% else %}
    <span>You don't have permission to do anything 😢</span>
  {% endif %}
{% else %}
    <a href="/login">Log in</a>
{% endif %}
```

Instead:


```twig
{% if not currentUser %}
  <a href="/login">Log in</a>
{% elseif currentUser.can('doSomething') %}
  <a href="/do-something">Do something</a>
{% elseif currentUser.can('doAnotherThing') %}
  <a href="/do-another-thing">Do something else</a>
{% else %}
  <span>You don't have permission to do anything 😢</span>
{% endif %}
```