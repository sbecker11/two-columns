# Instructions

The remainder of this file are the prompts used to get OpenAPI to generate the two-column.html page automatically.


The complete chat history can be found here:

https://chat.openai.com/share/b7c269db-49b0-47b9-8fcb-e14a0ff89c78

# A few excerpts;


 create an html file with embedded style and script 
The html should create two equal-width columns that both fill the entire window height.

the right column a dark grey background with a non-scrollable canvas. add a white text element with id = "report" and a function named "report" that updates the value of the report element.

call report("started"); before the left column is initialized. 

the left column a black background and a vertically scrollable canvas. 
Starting at the top center add a vertical stack of 10 non-overlapping red divs, 
each red div should be 150x150px in size with a vt margin of 20px for vertical spacing.

on window resize the width of the left column and the canvas should be always be
updated so they are 1/2 the width of the window.

The horizontal center or hz-ctr of each red-div should always be updated to match the 
hz-ctr of its parent canvas whenever the canvas, the left column, and the window are changed.

report the window eventtype, and the new hz-ctr of
the first top-most red-div, the canvas, the left column,
and the window whenever the canvas, column, or window is loaded, resized, or re-loaded.

-=---=--

wrong:

create an html file with embedded style and script 
The html should create two equal-width columns that both fill the entire window height.

give the right column a dark grey background with a non-scrollable canvas and a white 
report-element. add a function named "report" to update the value of the report-element.

call report("started"); before the left column is initialized. 

give the left column a black background with a vertically scrollable canvas. 
Starting at the top center position add a vertical stack of non-overlapping red divs
as children to the canvas. Give each red div a size of 150x2150px and a vt 
margin of 20px. Arrange the red-divs vertical stack of divs spaced by 20px.
All red-divs should have the same horizontal centers and all red-divs should
be horizontally centered on its parent canvas.

on window resize the width of the left column and the canvas should always be
updated so they are 1/2 the width of the window.

whenever the canvas, the left column, and the window are changed the red-divs
should be translated so they are always visible and horizontally centered
in its parent canvas.

report the window event type, and the new horizontal centers of
the first red-div, canvas, left column, and window 
whenever the canvas, column, or window is loaded, resized, or re-loaded.


Good! Except make sure the report message is used to display the event type and the new hz centers whenever the window is loaded, resized, or reloaded

-------------

this requirement was not satisfied:
use the report function to report the window event type, and the new horizontal centers of
the first red-div, canvas, left column, and window 
whenever the window is loaded, resized, or re-loaded.


---------------

update the report messages to display in JSON format

----------------

whenever the canvas, column, or window is loaded, resized, or re-loaded 
create a report message in multi-line html format that includes :
window event type,
new horizontal centers of
the first red-div, canvas, left column, and window 

----------------

excellent!

now add a  50x50px div with border 1px solid white and z-index = 10 that is centered visibly in the left column at all times both horizontally and vertically. 
Recenter on canvas scroll and recenter on  window load, reload, or resize.
add center x and y coordinates of the center-div to the current report

----------------

almost there! the center div is not horizontally centered 

-----------------

the center div is now centered horizontally, but it is not yet centered vertically and re-centered vertically when the canvas is scrolled vertically

=================

nope. the centered div is still not being translated vertically to remain vertically centered when canvas is scrolled vertically

----------------
the red-divs are now missing.
Please regenerate the entire html page

----------------

the center div is still not being translated vertically to remain visible at left column center when canvas is scrolled vertically

----------------

still wrong. the center div is positioned at canvas vertical center at initial window load, but it is not shifted vertically to stay at visible center of left column as canvas is scrolled vertically.

----------------

report the canvas-relative center of the center-div not its center relative to itself.

 ----------------

the center-div is statically positioned on the stack but it needs to be translated on the vertical scroll.
It need to be moved down when the canvas is scrolled up
and it needs to be moved up when the canvas is scrolling down.

----------------

this is partially good - the centerDiv is not yet being shifted when its parent canvas
is being scrolled within its parent left-column.

----------------

wrong, the centerDiv is not being vertically centered in the left-column when the canvas is scrolled within its parent left-column

----------------

report the left-column scrollTop and left-column offsetHeight  as the canvas is being scrolled

----------------

regenerate the entire html page

----------------

All 3 of these report messages are almost identical. Refactor accordingly

----------------

regenerate the entire html page

----------------

the center div is properly centered on load and resize but not on scroll!

----------------

nope. centerDiv is being correctly centered on load and resize but NOT on the vertical scroll. Why is this?

----------------

add the canvas scrollTop and offsetHeight to the report

----------------

try adding handleCanvasScrolling to the left-column instead of canvas

----------------

Perfect. Regenerate the entire html file

----------------

excellent!!

----------------

now add a mousemove event handler to the canvas
 that reports the canvas-relative mouse coordinates 

----------------

on mousemove event also report canvas-relative coordinates of centerDiv

----------------

Additionally, update handleCanvasMouseMove to also report the 
centerDiv relative coordinates of the mouse

----------------

in handleCanvasMouseMove format the output string to mulit-line HTML format

----------------

PERFECT!!

----------------

now when creating each redDiv give it the following new properties
origCtrX = redDiv.left +  redDiv.width/2
origCtrY = redDiv.topt +  redDiv.height/2
randZ = a random int. value between 1 and 8

----------------

in createRedDiv after  document.createElement("div") how are the  offset attributes set?

----------------

add global constants 
minRandZ = 1 
maxRandZ = 8

in createRedDiv()
After a new redDiv has been added to the canvas
store the following dataAttributes to the redDiv:
originalRect - the redDiv's current rect voundary
originalRandZ - a random int value between minRandZ and maxRandZ

----------------


----------------


----------------


----------------


----------------


----------------


----------------


----------------


