This is the project files for beginners Udacity Lessons. Based on html code. So everything here should be pretty straight forward.

hyper text markup language uses the http portion of internet markup meaning code uses keywords for structure

html is a sequence of tags that tell the web browser how to make/show a webpage. combined with css and js it is a part
    of proper full stack websites.

html is the skeleton of the web page, css is the skin and js is the brain.

All html starts with <!DOCTYPE html> ; this tells the browser to render the code as html

following the above, all the actual code will be enclosed in <html> and </html> tags.

inside the <html> tags, there are the <body> tags which include all the content you actually see on the page.

the div tag can be used to create your own text element.

block elements structure the page into coherent blocks. includes p,lists,headings,article,section,blockquote

inline elements differentiate a part of text to give it a particular function or meaning.
    include a(link),em(emphasised words, italics),strong(important words, bold)

there are 6 types of headings. h1 to h6. dont skip heading levels. use css to customise them instead.

span element can be used to separate a chunk of text within a tag to be styled differently to the rest.
    e.g. This sentence has a red bit <span class=”red”>this is the red bit</span> back to black
obviously the above requires a style sheet with a class called red which turns text red.

blockquote's are used for citations, like so:
    <blockquote cite="https://www.wikiwand.com/en/Scooby-Doo_(character)">
      <p>Ruh-roh--RAGGY!!!</p>
      <footer>—Scooby Doo, <cite>Mystery Incorporated</cite></footer>
    </blockquote>

3 types of lists in html.
    unordered - lists in no specific order
    ordered - lists in a specific order
    description - lists with name/value pairs

The description lists is for things like glossary. It has <dl> tag enclosing description terms (<dt>) and description descriptions (<dd>)
    <dl>
        <dt>Beast of Bodmin</dt>
        <dd>A large feline inhabiting Bodmin Moor.</dd>

        <dt>Morgawr</dt>
        <dd>A sea serpent.</dd>
    </dl>

src attribute for saying where to pull an image or resource from.
href attribute for a link that leads to another webpage somewhere, or to another part of the same page (an anchor) or to another page
    thats part of the same website.
When attaching a stylesheet to html page, you create a href with 'rel' attribute equal to "stylesheet", and a 'type'
    attribute equal to "text/css" and the href contains the file path from project root to the css file in question.
    <link rel="stylesheet" href="css/style.css">

alt attribute for images is for accessibility reasons and as an alternative text to display when image cant be accessed.

title tag in heading is for tab title, search engine result, social media link heading

form inputs are added with an input tag, with an additional type attribute to specify type
    <!-- A text input -->
        <input type="text" />
    <!-- A checkbox -->
        <input type="checkbox" />
    <!-- A radio button -->
        <input type="radio" />

A drop down menu uses the select tag:
    <label for="colour-select">Choose a colour:</label>
    <select id="colour-select">
      <option value="">--Please choose a colour--</option>
      <option value="blue">Blue</option>
      <option value="red">Red</option>
    </select>

A text area is for lots of multi line text input. like a youtube comment:
    <label for="learn">What do you hope to learn today?</label>
    <textarea id="learn" name="learn" rows="5" cols="30">
        I hope to learn about...
    </textarea>

CSS

good css is like good code, you shouldn't be repeating the same rules for multiple elements. Find a way to select all
    elements that require a certain styling in one block of styles.

there are 3 ways to select an element for css styling. ids and classes you know. the third type is selecting by 'type'
    this is when you select all p tags to be a certain way, or all tags of a certain 'type'

id's are selected by #elementid, classes by .elementclass, and types are just selected by their names, i.e. div{styling}

color property of an element generally affects text colour. background-color property affects element background

a css pseudo-class is a keyword added to the selector for a specific state of the selected element. like if you only
    want styles to affect when mouse is hovering over an element, you can use selector:hover{styling}

You can also select elements to apply css to by the attributes of those elements. in short:
 >   [attr] This selector will select all elements with the attribute attr, whatever its value.
 >   [attr=val] This selector will select all elements with the attribute attr, but only if its value is val.
 >   [attr~=val] This selector will select all elements with the attribute attr,
     but only if val is one of a space-separated list of words contained in attr's value.

For example, to select all images that contain the alt attribute, img[alt]{styling} will do the trick

select multiple elements for styles like so: h1, h2, h3{styling}.

Its good practice to have multiple css files, for different parts of the web page to make maintenance easier. To do this
you import the other css files into your main css file, like so:
    // at the top of your main CSS file
    @import “./layout”; //css for page layouts
    @import “./images”; //css to style all images

CSS has an importance hierarchy so it knows what styling to use when an element has clashing styles applied to it from
different sources.
    Type selectors are least important. type styling applies when others dont clash.
    Class selectors override type. they are more specific and therefore more important. This includes pseudo-classes and attribute selections
    ID selectors override class related styling. more specific.
    Inline styling (applied inside the html tag, with the style attribute) overrides ID as it applied to 1 specific tag.

    ID>Class>Type  <-- main hierarchy

You can override the above hierarchy by using the !important keywords after a particular style. This will make that styles
priority  greater than any other clashing style that applies to the same element. Use like so:
    element { color: blue  !important; }

You can use '>' to select elements that are direct children of a certain element. #div > p {styling} will apply styles to
p tags nested directly inside the #div (not children of children etc.). can use this to target li items inside ul or ol tags.

div + p{style} will select p tags that come immediately after a div tag has closed. If other tags come between div and p,
then p will not be selected for that styling.

div ~ p will select all p tags that come after a div tag (this means after closing part of div tag, not nested p's),
 even if other tags come in between them.

Space; #container p {style} will select all p tags inside #container.

The Box model: each element in a html page has height, width, border, margin (outside border) and padding (inside border).
    Each element, to css, is a rectangular box. the boxes content has height and width. The space between content and
    border is called padding. this is what surrounds the content (doesn't eat into content). The border surrounds the padding and
    seperates it from the margin (unless you set it to 0) and there is then a margin the surrounds the border and keeps other elements or the edge of the page a certain distence away.

display property:
    display: inline  //will make elements horizontal as wide as the content inside them and will position elements next
                       to each other.
    display: inline-block //just like inline, elements as wide and tall as their content. But this allows you to add
                            width and height to element. you cant do that with inline.
    display: block //elements are as horizontally wide as their parent and are stacked on top of each other.
    display:none //elements have 0 width and height. i.e. they are invisible. You may want elements to be invisible
                   under certain circumstances and this is a way to achieve that.

When elements overlap they are ordered along the 'Z-Axis'. a z-index property can be used to decide which element overlaps
over which one. a larger z-index value will overlap an element with a smaller z-index value.
  -->   z-index:1;

Absolute vs Relative units:
Absolute units are the same on all screen sizes and pixel densities. Include: px, in, mm, cm
Relative units are relative to variables like the screen size or pixel count. Include: %, em, vw, eh
    %  : percentage of something, suck as browser window or parent element.
    em : equal to the font size of the element in question. If elements font is 12px then 2em = 24px.
    vw : units of viewport width (browsers rendering space). Each unit is 1/100th of width.
    vh : same as vw but for viewport height.

em is very useful for defining font sizes relative to each other. Body could have some base font size and you could then
    link all other font sizes to that by using em. Then, to change the page font size you would only need to change one value
    and the rest of the text would adjust relative to it. magic.

Typography:
This is the art of designing every part of text using css properties until you get a completely customised text.
    text-align: center, left or right to align text a certain way - think word alignment buttons to center for poems or
        headings, but left for blocks of text.
    font-size: 2em like mentioned, use em to set font size relative to the rest of the page. always have body tag css
        values to set default values for things like this.
    color: self explanatory
    line-height: 2em will make each line take up twice the vertical space so they are more spread out. use em units for this.
        margin-top and bottom is used to give paragraphs space between each other. line-height is for lines within those paragraphs.
    width: xyz % using percent to give line length a limit to make text easier to follow.
    text-decoration: add underline to text. set to none to remove links underlining
    font-family takes multiple values as not all users will have all fonts installed on their OS so if 1 doesn't work, system will
        use another font. safe fonts include : https://web.mit.edu/jmorzins/www/fonts.html
    font-weight is between 100 and 900. the bigger, the bolder. only use multiples of 100.

remember, to apply multiple classes to an element just separate those classes by a space - no commas or colons
    <div class"class1 class2 class3">

<del> tag gives text a strike through line

In CSS, font weights are expressed as numeric values between 100 and 900. Fortunately, there are relatively standardized,
 human-friendly terms for each of these numeric values. “Black” usually means 900, “bold” is 700, “regular” is 400, etc.
  Most families don’t supply a face for every single weight. For example, Roboto is missing “extra light” (200),
  “semi bold” (600), and “extra bold” (800).

You can add fonts externally by adding a link to them in html head:
     <link href="font-link" rel="stylesheet">
 after adding that, you can add the font name in css.

There are 6 ways to define colours in html.
    Hexadecimal colors
    RGB colors
    Predefined/Cross-browser color names
    RGBA colors
    HSL colors
    HSLA colors

the first 3 are most common.
    hexadecimal is just # then 6 numbers or letters, #RRGGBB, where #0000ff = blue
    rgb(red, green, blue) where each colour is replaced by a number between 0 and 255 for the intensity of that colour. rgb(0,0,255)=blue
    140 color names are predefined in css. see here https://developer.mozilla.org/en-US/docs/Web/CSS/color_value

border-radius: 20px  this property will give boxes rounded corners. it will also cut off words so you'll need to add padding.
    You can also use percentages to select border radius.

background-image: url("path/to/image.png") use this to give an element an image as background
background-size: contain/cover etc use to change if image is repeated or stretched.

FLEXBOX:

aligns and positions elements within a parent element.
The parent element is called the container, and the child elements are called items. There are separate css properties
    that apply to each one.
Set the display property of a div element to flex, the its nested elements will automatically become flex items. You can then use flex syntax.

Container:
    flex-direction: column or row will change if items are stacked in a column or spread in a row
        column-reverse and row-reverse will reverse the order of the items inside container

Items:
    order: 1 //use order property to order items inside container. 1 is first, 2 after etc.

Flex-box uses axis and direction.
    the main axis is defined by flex-direction which has 4 possible values (mentioned above in container bit):
    The two row settings with set the main axis horizontally (inline), and the two column settings will set the main
    axis vertically (block-direction).
Whichever axis is not the main axis is called the alternate axis, or cross axis. The axis decide the flow of content in
rows or columns.

This means the flex-direction sets the main axis which also affects justify-content and align items - so changing flex
    direction will change those properties too.

Moving the HTML code for the elements themselves to reorder
    the default is that elements are ordered in the order that they appear in the html. change that to change order.
Appending -reverse to row or column will reverse the order in the specified row or column
    already mentioned in container bit above
Using the order property of the individual items inside the grid
    already mentioned in items bit above

To align items on the cross axis use align-items with the possible values:
    stretch
        stretches items to fill the cross axis.
    flex-start
        items will position themselves at the top/left depending on cross axis
    flex-end
        items will position themselves at the bottom/right depending on the cross axis
    center
        will center position of items along the cross axis. their position will be centered but size unaltered.

To justify content on the main axis use justify-content, which has the possible values:
    flex-start
        all elements aligned to the left/top of the container depending on axis
    flex-end
        all elements aligned to right/bottom of container depending on axis
    center
        will center all elements in main axis with even space to either wide of all elements. the elements themselves
            get no extra margin - they are close. the space is between all elements and edge of container.
    space-around
        will put equal space around each item along the main axis. distance between items and edge of container will not be equal.
    space-between
        will put equal space between items themselves, but first/last items will be along edge of container.
    space-evenly
        will put equal space between each item and between first/last items and edge of container.


CSS GRID:

Flexbox is for how content flows, Grid is for how content is placed - i.e. grid works nicely for page layouts,
    flex works nicely for regions within the grid.

flex box is great for content of a website (divs, p's, heading's) while grid is good for layout of page itself - header, main, sidebar, footer etc.

display: grid;  add this to the container div to use css grid.
width will define width of grid. but if combined width of rows/columns exceeds width of grid then grid width is ignored and items overflow.

once you have a grid, you need to set divs for columns and rows:
    grid-template-columns:60px 60px //the number of values entered is the number of columns there are. the size of each column is specified.
    grid-template-rows: 60px 60px //the number of values entered is the number of rows there are. the size of each row is specified.
    grid-gap: 20px  //gap between each row or column in the grid - not between first/final row/column and edge of grid. that is 0.

You can name grid areas (like blocks) and then assign elements to various 'areas' or blocks.
    assigning grid position uses the order grid-row-start, grid-column-start, grid-row-end and grid-column-end
    this way you can state the row and column an element starts in and ends in.
   .item_class or #item_id{
     grid-area: 1/2/3/3 //so here, element is positioned from rows 1-3, and columns 2-3.
   }

you can also name the areas and then assign each element to an area by its name rather that order.
    .container_class{
        display:grid; //set display to grid
        grid-template-columns:60px 60px //create two columns and two rows
        grid-template-rows:60px 60px
        grid-template-areas: "topleft topright"         //each row MUST have its own naming row, with each area being named like so.
                             "bottomleft bottomright";
    }

the grid area is not the number of rows and columns the grid has. not necessarily. You set the grid area of each part of
the page to something. the sidebar could have "grid-area: sd;" then when creating grid-template-areas inside the container
item you can say grid-template-areas:"sd sd sd mc mc mc mc mc mc" so that main content (mc) is twice as wide as grid. assuming
the grid template columns are set equal in width.
 >   to be honest - its probably easier for each row/col to be an area. splitting them into multiple grids and columns via area
    property feels to complex to keep track of.

A better way to use grid is to divide up the page into fractions using the fr property. instead of setting column sizes
    in pixels, you can say grid-template-column: 1fr 1fr 1fr; and you create 3 columns equally sized in all the space available
    after the gap size is calculated.
    a shortcut to 1fr 1fr 1fr is repeat(3, 1fr) which repeats the 1fr value 3 times.
    to make one column/row bigger than others relatively then give those particular elements a bigger fr value.

Some cases require an unlimited number for rows (like with scrollable content feed reddit etc.).
To do this you can use the grid-auto-rows property like so
    grid-auto-rows:minmax(100px, auto); minmax function takes the minimum height of each row and maximum height - an auto maximum height says to make each row as tall as its content requires.

You can nest grids inside each other, by adding display:grid to a grid area/unit/block whatever, you can make that into its own grid.

RESPONSIVE WEBSITE DESIGN

    you can use media queries with specific break points to make websites that respond differently to smaller devices than larger ones.

    @media(min-width:900px){CSS STYLESHEET} will only apply that styling for screens with viewport width bigger than 900px.
        min-width is the minimum width of the browser window before the styling contained in the brackets is applied.
        You can create multiple css stylesheets for different sizes screens and import them all into the main one. Or split
        css sheets by what they are styling (like images) then have each one style images differently for different screen sizes.

original css styling will still apply when a media query is used, but everything in the query will override original code
    if the minimum requirement is met.

