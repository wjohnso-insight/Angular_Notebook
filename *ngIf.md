# *ngIf

## *”A structural directive that conditionally includes a template based on the value of an expression coerced to Boolean."*

![Screen Shot 2021-02-13 at 1.45.56 PM.png](https://res.craft.do/user/full/35b7910a-02c9-b6ae-7bc0-106a5eab9e46/doc/469CAF1A-002E-4E15-9096-500690B7CE54/3BA2975B-11F1-4383-A730-E41E8FA4CDDB_2)

```typescript
<div *ngIf="condition">Content to render when condition is true.</div>
```

Or expanded syntax:

```typescript
<ng-template [ngIf]="condition"><div>Content to render when condition is
true.</div></ng-template>
```

From an else block:

```typescript
<div *ngIf="condition; else elseBlock">Content to render when condition is true.</div>
<ng-template #elseBlock>Content to render when condition is false.</ng-template>
```

Most commonly used to conditionally show an inline template, as seen in the following example. The default `else` template is blank.

```typescript
@Component({
  selector: 'ng-if-simple',
  template: `
	<button (click)="show = !show">{{show ? 'hide' : 'show'}}</button>
	show = {{show}}
	<br>
	<div *ngIf="show">Text to show</div>
`
})
export class NgIfSimple {
  show = true;
}
```

