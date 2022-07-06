# Clarify complex conditionals with well named variables

Conditionals that use multiple comparisons, negate statements and/or use ternary syntax can be hard for humans to parse and are a frequent source of logic errors.

By using well named variables we can make the intent of the condition more easily understood.

Avoid:

	{% if currentUser and (currentUser.can('doSomething') or currentUser.can('doAnotherThing')) and not currentUser.admin %}
	  You can do things 🥳
	{% else %}
	    Sorry, you don't have permission to do anything 😢
	{% endif %}
	

Instead:

	{% set userCanDoThings = currentUser and currentUser.can('doSomething') or currentUser.can('doAnotherThing') %}
	{% set userIsAdmin = currentUser and currentUser.admin %}
	
	{% if userCanDoThings and not userIsAdmin %}
	  You can do things 🥳
	{% else %}
	    Sorry, you don't have permission to do anything 😢
	{% endif %}
	
Example state variable names

~~`current`~~  => `isCurrent`
