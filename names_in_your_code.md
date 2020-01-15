# Naming your style

Opinions differ over what is the best way to name elements in your styling.
Some say to keep it short and some say to be as detailed as possible, some say to work specific and some say to work atomic.
Summed up there is no one way to name your code, but im going to look in two ways and their pro’s and cons

## No classes
With this style of naming you defer from using classes as a reference point form your styling to your markup. This means that you target elements in you html by referencing to the name of the element (like ```main```) and use pseudo selectors (like ```:nth-child(4)```) for more specified selection.


#### Pro’s
- Separation of concerns: styling functionality and structure have been made separate with HTML, CSS and JS and adding classes might blur the lines between markup and styling.
- It makes you think more about structuring of your code
- It makes you thing about semantics more: by not relying on classes you are forced to give markup the right name to group elements instead of making everything a ```<div>``` with a class

#### Cons
- While separation of concerns is better in the HTML one could argue that the CSS now is about both structure as well as styling
- More syntax and longer selectors
- Making a minor change in markup might be a major styling change since naming is dependent on the structure of the markup

## BEM
BEM
BEM(Block Element Modefier) is a naming structure with uses specific naming for elements while relying on classes as target and not element names.
The reasoning for this convention is to make code mor lightweight, modular en reusable. by dividing elements up in larger blocks, elements and modifiers that show different states of components.
example:
```
<form class="form form--theme-xmas form--simple">
  <input class="form__input" type="text" />
  <input
    class="form__submit form__submit--disabled"
    type="submit" />
</form>
```
```
.form { }
.form--theme-xmas { }
.form--simple { }
.form__input { }
.form__submit { }
.form__submit--disabled { }
```
For larger projects this makes it that you can only have to style elements  you use multiple times once. combined with docs and a design system this can speed up development a lot.
Companies with large platforms(facebook, twitter, Bootstrap , GitHub) have applied this way of naming for that reason, and it is often used when using other methodologies like SMACCS od Atomic design

#### Pro’s
- Re-usability: by naming elements it is easier to transfer elements from one project to another
- The styling files can stay lighter when a project grows
- less conflicts due to specific naming
- Better performance since browsers work faster with class selectors than element names

#### Cons
- Names can become really long for selectors since you have to define the block > element > needed modifiers every time
- HTML gets bloated and ugly when a project grows it can cause the classList to become really large
- When you use this you are tempted faster to reuse from old projects to save time and it can make that you keep making the same elements


## Conclusion
Both ways have their pro’s and their cons and after looking into different kinds of naming I found one conclusion: 
> There is not one right way to name your code

At the end of the day it is not important to have the “best” way of naming your code. The most important thing is picking one convention for a project and bing consistent with is so it is clear the next time you (or someone else) continues working on it.

So long story short, there is no perfect way except the one that you can work the best with and keeps it clear for you and others.
