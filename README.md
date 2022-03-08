# css-grid-flexbox

## Flexbox
- The first elements - but not envisioned to lay out whole web pages
- Excels at vertical centering and equal height
- Very easy to reorder boxes
- Disadvantage:
  - Wasnt designed to be locked down for layouts!
  - works in one dimension only.

Tree version flexbox:
- display: box
- display: flex-box
- display: flex

Minigame for example flexbox https://flexboxfroggy.com/

FlexBox Properties

```
Parent (Flex Container)
	display: flex | inline-flex;

	flex-direction: row | row-reverse | column | column-reverse;

	flex-wrap: wrap | nowrap | wrap-reverse;

	flex-flow (shorthand for flex-direction and flex-wrap) (flex-flow: row wrap;)


These next two properties work similarly, just on their different axes. 

	justify-content (main axis): flex-start | flex-end | center | space-between | space-around | space-evenly;

	align-items (cross axis): flex-start | flex-end | center | baseline | stretch;


Align-content spans multiple line boxes. 
	
	align-content: flex-start | flex-end | center | stretch | space-between | space-around | space-evenly;



Children (Flex Items)
	order: <integer>;

	flex-grow: <number>; 

	flex-shrink: <number>; 

	flex-basis: <length> | auto;

	flex: shorthand for grow, shrink, and basis (default:  0 1 auto)
	
	align-self: overrides alignment set on parent



Main axis = the axis declared in flex-direction
Cross axis = the other axis

i.e. if flex-flow: row wrap;  

      main axis = row
      cross axis = column

if flex-flow: column nowrap;

       main axis = column
       cross axis = row
```

Flexbox Explained
For each of the directions below, add these declarations to the existing ul or li elements.

The first grouping has to do with the flex-container, or the ul in this example.

- ul { display: flex; } This gets everything on a single line. By default, the direction is in a row and in standard order.

- ul {display: flex; flex-direction: X; } X = row, row-reverse, column, column-reverse This takes the elements and places them in a single row or a single column. Ordering is either in source order or the reverse of the source order. Flex-direction defines our main axis.

- ul { display: flex; flex-direction: as before, flex-wrap: X;} X = wrap, wrap-reverse, or nowrap flex-direction orders the individual items. flex-wrap orders the rows/columns created.

- ul { display: flex; flex-flow: X;} flex-flow is shorthand for flex-direction and flex-wrap It takes two arguments, just like the individual properties. Example: row wrap, row-reverse wrap, column nowrap, column-reverse wrap-reverse, etc Just because the row/column is reversed does not mean the wrap has to be reversed

- ul { display: flex; flex-flow: row wrap; justify-content: X; } X = flex-start, flex-end, center, space-between, space-around, space-evenly justify-content determines the distribution of the flex items within the flex container on the main axis — in other words, how should space be allocated relative to the width of each item? If flex direction is row, then horizontal is the main axis. When flex-direction is column, then column is the main axis.

- ul { display: flex; flex-flow: row wrap; justify-content: center; align-items: X} X = flex-start, flex-end, center, baseline, stretch This aligns our items on the cross axis. Since we’re working with a row currently, this is aligning elements in vertical space.

- ul { display: flex; flex-flow: row wrap; justify-content: center; align-items: center; align-content: X} *X = flex-start, flex-end, center, space-between, space-around, space-evenly Notice that changing align-content further aligns all boxes to the center of the ul. Without this, the boxes are distributed with space-around by default.

The next set of properties are about the individual flex-items, or the li’s in this example.

- .flex2{ border: 2px dotted blue; order: X; } X can be an integer. 1 will move the .flex2 boxes to the end of the list, while -1 will move them to the start of the list. 0 is neutral.

- .flex2{ border: 2px dotted blue; flex-basis: X; } flex-basis is analogous to width, but not quite the same thing. Width is an absolute measurement — an element is that wide, all the time. We can measure width in relative units (say 25% instead of 250px), but in the end, the measurement itself never changes. For flex-basis, we try to achieve a given width with the space available. It could be smaller than this width, or it could be wider, depending on the extra space and how that’s supposed to be distributed. Distribution of extra space is controlled by flex-grow and flex-shrink (below).

- .flex2{ border: 2px dotted blue; flex-grow: X; } X can be 0 or a positive integer. (It won’t break with a negative integer, but it won’t do anything either.) flex-grow, like flex-shrink (below), distributes extra space once each element is displayed on the page. In this example, our flex items are center-aligned (see justify-content: center on the ul). By assigning a value to flex-grow, any extra space will be assigned in greater proportion to this element, making it larger relative to the other items. Note there is no unit with this measurement — it’s simply a proportion.

- .flex2{ border: 2px dotted blue; flex-shrink: X; } X can be 0 or a positive integer. (It won’t break with a negative integer, but it won’t do anything either.) flex-shrink controls what happens to extra space as elements shrink. By assigning a value to flex-shrink, as elements get smaller on the page, this element will get smaller faster than the others. Note there is no unit with this measurement — it’s simply a proportion.

- .flex2{ border: 2px dotted blue; flex: G S B; } G = flex-grow S = flex-shrink B = flex-basis This is the shorthand for combining flex-grow, flex-shrink, and flex-basis.



Resource:
- https://flexboxfroggy.com/
