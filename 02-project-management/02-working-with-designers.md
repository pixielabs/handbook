# Working with designers

## Software preferences
Through experience we've found it can be difficult for us to implement designs
implemented in Photoshop or Illustrator. Our favourite app to receive designs
in is [Sketch](https://www.sketch.com). Our second favourite is
[Figma](https://www.figma.com) provided it's a fully paid up account.

## Mobile first
It is very exciting for clients to see desktop designs, however we always push
to have mobile designs first. We can adapt mobile views to desktop views
quickly. The reverse is rarely true. Intuitively, working with less screen
space is harder than working with more.

## Breakpoints
We build fluid websites, that is, websites that work well at every possible
screen size and resolution. However it's not possible for designers to give
us designs for every single resolution! When we implement designs, we make
changes to the look and feel at the following breakpoints, so the more of
these we receive in designs, the more accurately we can match the desired
look & feel to the fluid design:

 - Tiny: Up to 640px
 - Small: >640px
 - Medium: >768px
 - Large: >1024px
 - XL: >1280px
 - 2XL: >1536px

Note that we strongly encourage that we are provided an additional design
at a width larger than 1536px to make it clear which design elements should
be constrained to 1536px and which should be full width/full bleed.

## How we check our design implementation
We don't implement designs that only work at discrete breakpoints; we test them
throughout every possible window size from 375px up to 2560px and beyond. But
we pay special attention to the following points:

 - Small mobile: 375px
 - Medium mobile: 425px
 - Tablet: 768px
 - Laptop: 1024px
 - Large laptop: 1440px
 - Desktop: 2560px

## Colours and style guides
We welcome style guides with standardised guidance on colours, margins etc.
but a style guide is only useful if the designs adhere to it. Before designs
are signed-off, we should check as a team that they conform to the style guide
e.g. there are no non-standard colours and other design elements such as borders
or repeated components are 100% consistent with the style guide.

If we've already made a decision to use a certain style framework like
[Tailwind](https://tailwindcss.com/) we should encourage the designer(s) to just
use the colours available there, or to provide a colour scheme in _exactly the
same structure_. We've found in the past that adding arbitrary colour schemes
to Tailwind really restricts the power of Tailwind.

## Inconsistent content in designs
Before thinking about designs, we consider what content in the project is
changeable and what is fixed. This should inform the designs. For example, if a
nav bar has a fixed number of links then designing the nav bar is relatively
straightforward. However, if the nav bar has a variable number of links based on
multiple app states, we need to consider how the nav bar will look with the
minimum number of links and the maximum. Is the design still functional at the
limits? Is it still aesthetically pleasing?

Fickle content is highlighted to the designer before they start work, and is
revisited before the designs are accepted. If possible, designs of changeable
components at the upper and lower limits should be made.
