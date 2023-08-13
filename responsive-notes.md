# Responsive Design

## Percentages

They are relative of their parent element. If parent element are block level, then they are 100% of the screen size.

## Images

As images are in-line elements, their default width is to fit its content. So eventhough it can be within a block level element, it will expand out to fit its content.

Width vs max-width. max-width: 100%, doesnt cause the image

## Control width of images

Set container width and max-width. Width in % and max-width in px.

## ems and rems

They are relative font sizes to their parent font size. So if parent font size is 10px, 1.5em, will be 15px. So we can set one font size in body. Then everywhere in the document, we use ems. So everyone will auto adjust.

ems has a cascading effect problem. Font sizes multiply through each child. Also, ems for font-sizes are relative to theri parent. But ems for everything else, is relative to the font-size.
rems are relative to the root element, which is the html element (16px). We can also use % on font sizes.

## General rule of thumb 

- Font-size = rem
- Padding and margin = em
- Widths = em or percentage

For different screen sizes, we will have different font-sizes. So if we use ems for padding and margin, it will adjust to the relative font size / content for different screen sizes.

## Flexbox

Normal block elements are row-wise, one stack over another. With display flex set on the parent, childs will columns.
.container
    .columns
        .cols
        .cols
        .cols
    .columns
        .cols
        .cols

### justify-content
Spacing out the columns, we can use justify-content: space-between, for that we need to make sure there is some space left around the elements so that it can be distributed between them. Justify content works horzontally.

### align-items
works on the vertical axis. By default, each cols height is strechted to match max height. flex-start, gives height to each col same as its content. center, aligns the in the center vertically.

### flex-direction
row: parent is row, so childs are cols of the row, side by side.
column: paretn is col, so childs are rows of the col, stacked over each other.

Whenever we change the flex-direction, the main axis changes. justify-content works along the main axis. align-items works opposite of it.


## Margin & Padding

Margin is space between neighbouring elements. Padding is space between content and elements border. All elements by default have margins and padding applied to it.

## Block level elements

The default height of block-level elements is usually determined by their content and any padding, margin, and border properties applied to them. Unlike the default width, which for block-level elements is typically 100% of their containing block, the default height is not set to a specific value by default.

## Media Queries

@media media-type and (media-feature){
    elem {

    }
}

@media all and (min-width: 400px){
    body{
        background: purple;
    }
}

All media queries should be after their default styles to prevent them for being overriden by more general styles.

## Navigation

<nav>
    <ul>
        <li><a href="index.html">Home</a></li>
        <li><a href="about.html">About me</a></li>
        <li><a href="recent-posts.html">Recent posts</a></li>
    </ul>
</nav>

## Compound selectors

.container p {} targets all <p> elements that are descendants of .container.
.container > p {} targets only the direct child <p> elements of .container.

## text-align: center

if the container has full width, then text align, will align the content in the center. Else not.

## margin

If you have h1, p, nav. If you only remove margin of p, it may still not work because there will still be magin top and bottom of the h1 and nav element. So we need to remove margin from those as well.

## Combining selectors

When you are needing to copy the same css in different elements, it makes sense to combine them.
h1,h2,h3{
    font-family: 'serif'
}

## a:hover, a:focus

hover for mouse, focus for keyboards (assistive tech)

## arranging styles and layouts

Arrange more general styles at the top. Then add your class styles.
Do typography first then layouts.
Do big layouts, then the smaller layouts.

## class modifiers

always add different css properties using piece by piece class. For ex. if you want to make your container flex, rather than adding display flex in the .container, create another class .container-flex and add it there. This is because in future, there may be content that doesnt need display flex.

## cool trick for images
img{
    max-width: 100%,
    display: block
}

## Work mobile-first

make your layour for small screen first cause those are much easier using their defaults. After that make your layouts for the bigger screen using media queries.

## Padding - then border - than a margin.

## flexbox order
can be used to reposition childs of flex container. Smaller order comes first.

## block level space
if we dont provide a width, block level elements want to occupy 100% space.

## Finding breakpoints
the point when our layout is breaking should be the breakpoint.