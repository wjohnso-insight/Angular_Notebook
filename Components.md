# Components

Components are identified with the

`@Component()` decorator

See [[Insight/Learning /Angular/Decorators]]

Implementation of a Component is distributed between 3 files:

- [name].component.ts - Component class code, written in TypeScript
- [name].component.html - Component [[Insight/Learning /Angular/Templates]], written in HTML
- [name].component.css - Components price CSS styling, written in CSS

# “Every component must be declared in exactly one NgModule”

When you create a component using the [[Insight/Learning /Angular/Angular CLI]], this declaration is automatically made in the [[Insight/Learning /Angular/AppModule]] top level class definition.

*app.module.ts from the “Tour of Heroes” tutorial*

![Screen Shot 2021-02-12 at 10.14.01 AM.png](https://res.craft.do/user/full/35b7910a-02c9-b6ae-7bc0-106a5eab9e46/doc/61F43369-14B1-41BF-AC9D-1FA49BBD3E17/499DC1CB-6F7D-470D-9B7D-F35DC55ECD25_2)

Note that the 'HeroesComponent', which was created with the [[Insight/Learning /Angular/Angular CLI]], is present in the [`@NgModule()`](craftdocs://open?blockId=5B05EE0A-9F87-4B2D-938D-2DBC28017C0F&spaceId=35b7910a-02c9-b6ae-7bc0-106a5eab9e46) decorator.

