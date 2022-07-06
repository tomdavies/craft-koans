# With great freedom, comes great responsibility

Craftcms is a highly flexible tool. It places almost no restrictions on how you author your templates. When used wisely, this is a strength. But when used without care, things can quickly get out of hand. Patterns become muddied. Reuse becomes difficult. What you expected to take an hour, ends up taking a whole day.

Fortunately, by learning some principles for clean code, and following some reasonable simple practices we can avoid all this code and stay on the correct path.

## Why do template-centric projects tend to go awry?

The code you are writing will be read many more times than it is written.  You will spend more time changing and adapting existing code than writing new code, and probably more time reading code than doing either of those things. 

Often by far the most time-consuming part of making changes to existing code, is the time taken to understand what is already there:

- What does the code do?
- How does it do it?
- Does it work properly?
- Where is it used and it what ways?
- What (unexpected) effects may my planned changes have?

The more code there is, the more must be understood. The less consistent the codebase is as a whole, the harder it is to apply learnings gleaned from one part to another. 

Conversely, the more consistent the code is with the standards and practices your team has adapted, the easier it is to understand

## The Solution: *Optimise for Time To Comprehension*

Simple & consistent beats clever (almost) every time.

Generally, try to write as little code as is required for it to be easily understood, but if forced choose clarity over compactness.

When you can't be simple and consistent, make sure you use comments or documentation to explain why things are they way they are. Often through doing so you will come to a better way of formulating your code.

## The Practices

View writing code as it truly is: the practice of leaving messages for future developers to understand (including yourself), just as much as it is the practice of sending messages for computers to understand.

By embracing the following practices together, we can spend less time in a state of friction and more time in flow.