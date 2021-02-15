# 2 - Tour of Heroes Tutorial

## Official Angular Tutorial from docs

- ## **::Project Setup::**
   - Create a new workspace and boilerplate application
      - See [[Insight/Learning /Angular/ng new]] & [[Insight/Learning /Angular/Sessions/1 - Session One]]
   - Created repo on GitHub
   - Modified boilerplate
- ## **::The Hero Editor::**
# Created the heroes component

The tutorial references  importing a ‘symbol’ from the [Angular Core Library](craftdocs://open?blockId=89F32EF0-4425-454F-891D-CC14FBA369C3&spaceId=35b7910a-02c9-b6ae-7bc0-106a5eab9e46).

What does symbol mean here?

   - Used [[Insight/Learning /Angular/|  - Pipe]] operator to modify the hero.name [Property Binding](craftdocs://open?blockId=B8FDF3A7-1780-4EA5-B0BF-643BB1C7B787&spaceId=35b7910a-02c9-b6ae-7bc0-106a5eab9e46)
# ‘Edit the Hero’

This part of the tutorial asks you to create an input using [two-way data binding](craftdocs://open?blockId=737564BE-16DB-4DB6-9CC0-FC70FFAE8EEC&spaceId=35b7910a-02c9-b6ae-7bc0-106a5eab9e46)

<input> <— binding —> {{ hero.name }}

This is accomplished in the template using Angular’s two-way data binding syntax [[Insight/Learning /Angular/ngModel]]

After adding the binding to the template, you must also update the [[Insight/Learning /Angular/FormsModule]], which contains [[Insight/Learning /Angular/ngModel]]. This import should take place in the top level [[Insight/Learning /Angular/AppModule]] class.

   - ***Activity Summary***

![Screen Shot 2021-02-12 at 10.20.23 AM.png](https://res.craft.do/user/full/35b7910a-02c9-b6ae-7bc0-106a5eab9e46/doc/4E5A1399-22BA-41B3-9268-AE62512C663F/0D80C7DF-D986-4DAA-A81D-5D48669A9BA4_2)

- ## **::Display A List::**
# Create mock heroes

Creating an array of heroes: Hero to use as mock data to populate UI

   - Displaying heroes
- ## **::Style The Heroes::**
# Global vs. Component Scoped vs. Inline Styling

See [.styles ](craftdocs://open?blockId=8C4F4922-ABB0-490C-8B3B-291DE2D27874&spaceId=35b7910a-02c9-b6ae-7bc0-106a5eab9e46) property for inline styling at class level

For global styling see [styles.css](craftdocs://open?blockId=C201CE79-C688-4796-BB8B-168C4EDD21CC&spaceId=35b7910a-02c9-b6ae-7bc0-106a5eab9e46)

For path to component style sheet see [.styleUrls](craftdocs://open?blockId=C966B4F5-97AF-4245-99E3-E6538C86E820&spaceId=35b7910a-02c9-b6ae-7bc0-106a5eab9e46)

   - Update the private CSS styling for Heroes component
# Added click event to Heroes template

See [Event Binding](craftdocs://open?blockId=CAA16DA0-D21C-490A-A54D-D4BA1435CA54&spaceId=35b7910a-02c9-b6ae-7bc0-106a5eab9e46), [[Insight/Learning /Angular/event binding syntax]]

   - Added click event handler to class definition
# Added ngIf structural directive to conditionally render hero details in the Heroes component

![Screen Shot 2021-02-13 at 1.59.53 PM.png](https://res.craft.do/user/full/35b7910a-02c9-b6ae-7bc0-106a5eab9e46/doc/4E5A1399-22BA-41B3-9268-AE62512C663F/1FEC774D-BAF8-41A0-BDAD-91103DB20D8B_2)

   - Added Dynamic Class Binding to <li> to update CSS class on hero selection

![Screen Shot 2021-02-13 at 2.10.16 PM.png](https://res.craft.do/user/full/35b7910a-02c9-b6ae-7bc0-106a5eab9e46/doc/4E5A1399-22BA-41B3-9268-AE62512C663F/F7F2ECF0-FA09-4AEB-B570-D85659CCA206_2)

- ## **::Create A Feature Component::**
   - ## Split the hero component into smaller units
      - Make the HeroDetail Component with [[Insight/Learning /Angular/ng generate]]
      - Added HTML to component template
      - Add @Input()
# Show the HeroDetailComponent

![Screen Shot 2021-02-13 at 2.44.32 PM.png](https://res.craft.do/user/full/35b7910a-02c9-b6ae-7bc0-106a5eab9e46/doc/4E5A1399-22BA-41B3-9268-AE62512C663F/3565C1D3-67AD-449F-A008-3557B7F9B737_2)

      - Added HeroDetailComponent as a child of HeroesComponent
      - Used [one-way data binding](craftdocs://open?blockId=151CDB49-891E-43CF-8F02-29E7F1882143&spaceId=35b7910a-02c9-b6ae-7bc0-106a5eab9e46) to pass selectedHero as a hero prop to AppHeroDetailComponent

![Screen Shot 2021-02-13 at 2.45.05 PM.png](https://res.craft.do/user/full/35b7910a-02c9-b6ae-7bc0-106a5eab9e46/doc/4E5A1399-22BA-41B3-9268-AE62512C663F/E91D1AAF-C4E4-4168-AAB1-46BA9509108B_2)

- # **::Add Services::**
   - ## ::Create the HeroService::
      - Used CLI to create a new service
      - Imported hero interface and mock data and created getHeros() method
   - ## ::Provide the HeroService::
      - See [[Insight/Learning /Angular/Providers]]
      - ## ::Update Heroes Component::
         - Refactor heroes to simple array declaration
         - **::Inject the HeroService::**
# Add private heroService parameter to class constructor

```typescript
constructor(private heroService: HeroService) {}
```

![Screen Shot 2021-02-15 at 10.55.39 AM.png](https://res.craft.do/user/full/35b7910a-02c9-b6ae-7bc0-106a5eab9e46/doc/4E5A1399-22BA-41B3-9268-AE62512C663F/BD4718EA-F265-48C3-950C-7ADBD03EB842_2)

         - **::Add getHeroes()::**
            - Added getHeroes method
            - Call getHeroes method on init with ngOnInit()
   - # **::Observable Data::**
      - ## ::Observable HeroService::
         - Refactor hero service to return an [[Insight/Learning /Angular/RxJS/RxJS]] [[Insight/Learning /Angular/RxJS/Observable]]
# Refactor getHeroes services to return mock array of Heroes using RxJS of opperator

*RxJS ‘of’ operator emitting an object, array, and function*

```typescript
// RxJS v6+
import { of } from 'rxjs';
//emits values of any type
const source = of({ name: 'Brian' }, [1, 2, 3], function hello() {
  return 'Hello';
});
//output: {name: 'Brian'}, [1,2,3], function hello() { return 'Hello' }
const subscribe = source.subscribe(val => console.log(val));
```

      - ## ::Subscribe in HeroesComponent::

