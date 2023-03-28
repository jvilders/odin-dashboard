# Dashboard mockup for The Odin Project

## Context
The final assignment for the intermediate HTML and CSS course was to recreate (or freely design, but I wasn't that creative) a dashboard design, using CSS Grid for layout whenever possible. This isn't because Grid > Flex, but because the course introduced Grid and this assignment was to hammer home how to work with it.

The assignment is not meant to be responsive but some parts resize a little bit.

Recognizing my own habits, I time-boxed the assignment this time to avoid spending too long trying to refine the final 5%. I usually end up in some advanced rabbit-hole to solve an issue that I had implementing something the assignment didn't even ask for.

## Learnings
### Grid layout vs logical grouping
I ran into this mostly in creating the HTML for the sidebar element: There are clearly three groups of items in the sidebar, but these do share some alignment. It's easy to ensure this shared alignment if I 'flatten' those groups and have all the element as children of the sidebar (the grid container), but then I lose the grouping. Similarly if I keep the logical nesting, ensuring the proper alignment means using some shared CSS variables for spacing. Intuitively there is both a logical grouping *and* an alignment on some shared grid, but I could not find a way to have both in a nice way. This is where the css subgrid property might help in the future, but currently it's not supported by all major browsers yet.

I've added both icons and the icons' text as children, but it's also possible to pack these together into a 'sidebar-item' or something and lay out the icon and text within that. Which is the right option? I don't know.

### Color palettes are hard
I thought I'd challenge myself and make a dark mode toggle as well and while I succeeded in creating the toggle, I couldn't really come up with a pleasing dark color palette. 

### You don't need everything at a narrower screen size
I was playing for a while with making the header a bit more responsive and had trouble with all the elements in it simply 
taking up too much space when decreasing the screen width. The eureka moment was that I could simply remove some of the elements at smaller screen sizes. It sounds obvious post-fact, but I kept trying to make the narrow screen layout be a mini-version of the 'regular' screen layout instead of adapting it more to what it needs. Definitely something I'll remember.

## Room for improvement
- Actually adding the CSS variables for the dark color palette so the switch does something.
- Having the sidebar disappear at narrower screen sizes, maybe by making it fold in somehow (`display: none`, manipulating width, using negative margin?).
- At narrower screen sizes, change grid layout of main content to move/hide the announcements and trending items area.