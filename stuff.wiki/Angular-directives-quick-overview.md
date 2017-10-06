
Angular "directives" can be usefully thought of as custom extensions to HTML, both Angular-wide extensions and custom to your specific application.

The Angular designers consciously aimed for this "extending HTML" feel to directives. They visually look like HTML extensions:

**A new element**

```
<date-picker></date>
```

**An HTML `class` attribute**

```
<input type="text" class="date-picker"/>
```

**A custom attribute on an element**

```
<input type="text" date-picker/>
```

**An HTML comment**

```
<!--directive:date-picker-->
```

What directives actually _are_ under the hood is simply JavaScript functions that manipulate and add behaviors to HTML DOM elements. 

A main advantage of the directive, in addition to being intuitive-looking as its declarative aspect resides inline in your markup, is that it's a **reusable** component. 

Regular declarative markup (regular HTML) can be mixed and matched in many ways to construct arbitrarily complex web pages. The behavior of those elements is configurable via attributes. Similarly, your custom declarative markup can be mixed and matched to construct your complex web application. This is more maintainable because the reuse of components cuts down the overall amount of code and centralizes and standardizes the logic of your app.