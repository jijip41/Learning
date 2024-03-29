# Learning

## CSS Architecture

---

_Questions to consider_

1. Why are CSS naming conventions useful?
2. When might Specificity become a problem?
3. How can composition help us build UIs?

---

### CSS naming convention?

- Use hyphen Delimited string

> e.g.

> .redBox{...} (X)

> .red-box{...} (O)

- The BEM naming convention - more structured naming convention // It is used for larger, more interrelated pieces of UI that require a number of classes

> Hyphens for blocks - The sole root of the component
> Underscores for elements - A component part of the Block
> Double hyphens for modifiers - A variant or extension of the Block
> <br>

### JavaScript Hooks?

- Do not bind your CSS and JS ooto the same class in HTML.
- It is much cleaner, more transparent, and more maintainable to bind JS onto specific classes

> e.g.

```
<input type="submit" class="btn  js-btn" value="Follow" />
```

### Why CSS naming conventions?

- Know what a selector does, just by looking at its name (what type of thing a class does)
- have an idea of where a selector(class) can be used, just by looking at it
- know the relationships between class names, by looking at them

### Conlusion

- CSS is difficult to maintain and keep stylesheets maintainable is important.
- By using CSS naming convention, code will always look and feel familiar to all members of the team, especially when is involved in big projects.
- The BEM approch ensures that everyone who participates in projects works with a single codebase and speaks the same language.
- Increase development speed, debugging and the implementation of new features in legacy code.
- To make stylesheets maintainable, I should keep code transparent, sane and readable
- Then I can keep my stylesheets scalable.

---

### CSS Specificity?

- Specificity is the means by which browsers decide which CSS property values are the most relevant to an element and therefore, applied.

### CSS Specificity Rules?

- The browser uses the source order (i.e the cascade) of the CSS stylesheet to determine which CSS property values are the most relevant to apply to an element.
- This rule applies when the CSS selectors have equal specificity.
  ![alt text](https://cdn-media-1.freecodecamp.org/images/vS9jdbLJDgW1IWycyuIWGFlX9xPnJxekCte-)
- The higher the specificity of a CSS selector, the more likely that browsers will apply its CSS declarations over another.

### Why problems?

- No matter how well considered your naming, regardless of how perfect your source order and cascade are managed, and how well you’ve scoped your rulesets, just one overly-specific selector can undo everything.
- If I use hugely over-specific selector, it's trumping the specificity of the one defined later- working against CSS' source-order based application of styles.
- Then I will have to refactor my CSS and HTML or write a more specific selector to override it --> **Think about time and cost!**
- If I go with writing a more specific selector option, I will nedd another selector to override it.

### Specificity can...

- limit your ability to extend and manipulate a codebase
- interrupt and undo CSS' cascading, ingeriting nature
- cause avoidable verbosity in your project
- prevent things from working as expected when move into different environments
- lead to serious developer frustration

### Simpliest tips for easier life when writing CSS

- try and keep specificity as low as possible at all times.
- make sure there isn't a lof ov variance between selectors in your codebase
- not using IDs in your CSS
- not nesting selectors
- not qualifying classes
- not chaining selectors

## Responsive Design

---

## Advanced CSS

---

## Advanced DOM

---

_Questions to consider_

1. What is a NodeList?

- How is it different from an array?
- what's the difference between "live" and "static" NodeLists?

2. What is the `<template>` element?

- How can we use this to render dynamic UI?

### Nodelist vs Array?

- **NodeList** is a collection of nodes that can be used to access and manipulate DOM elements.
- **NodeList** usually retuend by properties such as `Node.childNodes` and methods such as `document.querySelectorAll()`.
- **NodeList** Properties: `NodeList.length`
- **NodeList** Methods: `NodeList.item()`, `NodeList.entries()`, `NodeList.forEach`, `NodeList.keys()`, `NodeList.values()`.
- **Array** is a JavaScript object which can hold more than one value at a time.

### Live vs Static NodeLists

- **Live NodeLists**: Changes in the DOM automatically update the collection.

```
const parent = document.getElementById('parent');
let child_nodes = parent.childNodes;
console.log(child_nodes.length); // let's assume "2"
parent.appendChild(document.createElement('div'));
console.log(child_nodes.length); // outputs "3"
```

- **Static NodeLists**: Any changes in the DOM does not affect the content of the collection. The ubiquitous `document.querySelectorAll()` method returns a static NodeList.

**_It's good to keep this distinction in mind when choosing how to iterate over the items in the Nodelist, and whether you should chche the list's length._**

### `<template>` element?

- `<template>` element stores HTML markup but browser ignores this contents(only check if syntax is valid)
- HTML markup held by `<template>` is not rendered immediately when a page is loaded.
- We can access and use HTML markup in JS. - access `template.content` from JS, clone it to reuse in a new component.

- (bonus) we can put styles and scripts into `<template>`
