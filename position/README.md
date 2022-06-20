Types of positions:
1. relative
2. absolute
3. fixed
4. static
5. sticky

I.
Static positioning is the default that every element gets. It just means "put the element into its normal position in the document flow — nothing special to see here."

II.
Relative positioning is the first position type we'll take a look at. This is very similar to static positioning, except that once the positioned element has taken its place in the normal flow, you can then modify its final position, including making it overlap other elements on the page.

III.
An absolutely positioned element no longer exists in the normal document flow. Instead, it sits on its own layer separate from everything else. This is very useful: it means that we can create isolated UI features that don't interfere with the layout of other elements on the page. For example, popup information boxes, control menus, rollover panels, UI features that can be dragged and dropped anywhere on the page, and so on.
top, bottom, left, and right behave in a different way with absolute positioning. Rather than positioning the element based on its relative position within the normal document flow, they specify the distance the element should be from each of the containing element's sides. So in this case, we are saying that the absolutely positioned element should sit 25px from the top of the "containing element" and 90px from the left.

Which element is the "containing element" of an absolutely positioned element? This is very much dependent on the position property of the ancestors of the positioned element.
If no ancestor elements have their position property explicitly defined, then by default all ancestor elements will have a static position. The result of this is the absolutely positioned element will be contained in the initial containing block. The initial containing block has the dimensions of the viewport and is also the block that contains the <html> element. In other words, the absolutely positioned element will be displayed outside of the <html> element and be positioned relative to the initial viewport.

So an absolutely positioned element will be positioned top,left,bottom or right with respect to its first parent
element which is positioned(i.e not static).

IV.
z-index???

When elements start to overlap, what determines which elements appear over others and which elements appear under others? In the example we've seen so far, we only have one positioned element in the positioning context, and it appears on the top since positioned elements win over non-positioned elements. What about when we have more than one?

Eg: The absolute element which is blue in color overlaps the yellow static element.
I have added another silver absolute element which is at the same position as the blue absolute element.
=>Positioned elements later in the source order win over positioned elements earlier in the source order.
=>By default, positioned elements all have a z-index of auto, which is effectively 0.
This means because absolute blue element comes after absolute silver element in the source, the blue overlaps
the silver element.
For the silver element to overlap the blue element, you need to set the z-index of the silver element to any
positive number that exceeds the z-index of the blue element(if z-index exists for the blue element)

V.
Like absolute positioning fixes an element in place relative to its nearest positioned ancestor, fixed positioning usually fixes an element in place relative to the visible portion of the viewport.
This means that you can create useful UI items that are fixed in place, like persistent navigation menus that are always visible no matter how much the page scrolls.


VI.
There is another position value available called position: sticky, which is somewhat newer than the others. This is basically a hybrid between relative and fixed position. It allows a positioned element to act like it's relatively positioned until it's scrolled to a certain threshold (e.g., 10px from the top of the viewport), after which it becomes fixed.
