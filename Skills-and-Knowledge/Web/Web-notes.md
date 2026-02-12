- W3C: Word Wide Web Consortium

# UI Colors
- You should use HSB format, because it gives easier tuning options
- (Hue, Saturation, Brightness)

## Brand colors
- buttons, links, navigation, icons

### Choosing a brand color
- looks good on a button background, multiple places

## Supporting colors
- error messages, confirmation, information dialogs
- Standard colors to decide:
- Green for success
- Orange for warning
- Red for error
- Blue for information
- Colors should go well with the brand color
- Saturation and brightness should be close to the base color

## Neutrals
- almost all of the ui is made of neutral colors, that are usually some sort of gray
- buttons, backgrounds, text

- pick a middle gray
![[Pasted image 20260208135431.png]]
- main color to the 500 spot

![[Pasted image 20260208135449.png]]
- line where the rest of the colors will be chosen

![[Pasted image 20260208135525.png]]
- darkest shade to 90 to 100 saturation and 20 to 30 brightness

![[Pasted image 20260208135538.png]]
- 5 to 10 saturation and 95 to 100 brightness

![[Pasted image 20260208135553.png]]
- middle point for 300 and 700
- and again with the rest

- same process with all the colors
![[Pasted image 20260208135620.png]]

- with neutrals the curve is different and the darkest isn’t that far on the right
![[Pasted image 20260208135633.png]]
- after picking colors, they should be tested if they ar coherent with each other, if not then tune

# HTML
## HTML DOM
- JavaScript can change: HTML content, Attribute values, Styles

## Events
- Event: something that happens to HTML elements
 
# CSS
- Cascading Style Sheet
- Selector – Decloration (Property:Value)
  

- Selector
- Simple: Element name, id, class
- Combinator: Relationship between selectors
- Descendant selector (space): (div p {) p inside div
- Child selctor (>): (div > p) p that is a child of div (not child child)
- Adjacent sibling selctor (+): (div + p) p imeaditely after div (both must have same parent)
- General sibling selector (~): (div ~ p) all p:s after div (both must have same parent)
- Pseudo-classes: State of element
- For example: a:link, a:visited, a:hover, a:active (hover and active must be in this order)
- Pseudo-element: Used to style specified parts of an element
- For example: p::after, p::first-line
- Attribute: Use attribute value to select elements
- For example: a[target=”_blank”]

- Comments: /* */

- Colors:
- RGB, HEX, HSL


- Background
- Color, Picture, Repeat, Position, Attachment, Shorthand
  
- Borders

- Margins
- SOMETIMES can collapse.

- Padding
- Box-sizing: border-box: this keeps the width

- Vendor prefix: experimental features that work on some browsers

- Inheritance
- Shorthand

- Height and width
- Does not include padding, borders, or margins

- Box model
- Margin, border, padding, and content

- Outline
- Basically a border
- Can have an offset from border

- Text

- Fonts
- Serif, Sans-serif, Monospace, Cursive, Fantasy
- Callback font
- Font Pairings

- Icons

- Links
- Link buttons

- Lists
- Unordered, Ordered

- Tables
- <tr>: row
- <th>: header
- <td>: data

- Display
- Block, Inline, None, Visibility

- Position
- Static, Relative, fixed, Absolute, Sticky

- Z-index

- Overflow
- Visible, Hidden, Scroll, Auto

- Float
- Left, Right, None, Inherit

## SCSS
- Can use variables
- Syntactically Awesome Stylesheet
- Css extension
- Css pre-processor
- Varables: $
- Variables: strings, numbers, colors, booleans, lists, nulls
- **Transpiling**: Convert sass to css
- Comments: // and /* */
- Availability depends on level of nesting
- !global at the end will make the it global
- @import imports sass, scss or css files
- Partials: use an _ in fron of scss file so that will not be transpiled directly (when impoting, forget _)
- @mixins: Reuse css with @include
- @extend: Use similar style without a need to write it again
- Sass functions?


nav ul {
}

nav li {
}
->
nav {
ul {
}
li {
}
}

Text-align
Text-transform
Text-overflow

->
Text: {
Align
Transform
overflow

# JavaScript
## Progress (W3)
- Comments

## System
## History
- Ecma international

## Versions

## Frameworks/Libraries

## Code location

- <script></script>

## Async

## AJAX

- **A**synchronous **J**avaScript **A**nd **X**ML.
- Update a web page without reloading the page
- Request data from a server - after the page has loaded
- Receive data from a server - after the page has loaded
- Send data to a server - in the background

## Assign Events Using the HTML DOM
<button id="myBtn" onclick="displayDate()">Try it</button>

<script>  
document.getElementById("myBtn").onclick = displayDate;
</script>

## This
## Important
## Styling conventions
## Variables
- var, let, const (let and const were added 2015)
- after decloration: undefined
- _ is often used as an alias for private (hidden) variables

## Scope
- Block
- Function
- Var redeclared creates new variable only for function
- Global

## Hoisting
- Var yes
- Let and Const no
- Declaration is hoisted, initialize not
- Won’t work in strict mode

## Sets
## Maps
## Objects
- objects: {}
- properties: name:values pairs in objects (object.name or object[name]

## JSON
## Iterables

## Arithmetic
- Nullish Coalescing: x ?? y (returns x if it is not null or undefined, otherwise returns y)

## Comparison
- Equal to: ==

## Assignment

## Data types
- Types are dynamic: x = 5; x = “jotain”;

## Typeof
## Type conversion

## Classes

## Functions
- $ is often used as an alias for the main function. (in jQuery, $ is used to select all HTML elements)
- yield: pauses function
- Function*: generator function
- a method: function stored as a property

## Arrow function

## Error

## Strict mode

## Less Important (maybe)
## Syntax
- multiple whitespaces are ignored
- 80 char line length. Break after operator
- Literals: fixed values
- Identifiers: must begin with a letter, a dollar sign or an underscore. **Case sensitive!**

## Comments
- // or /* */

## Arrays
- arrays: []

## Try catch
### Loops
## If
- Ternary operator

## String
- Both “ and ‘

## RegExp
## Math
## Operators
## Numbers
- let y = 10e5 (100000)

## Bitwise
## Dates
## Output
- window.alert(something) (window-part optional)
- console.log(jotain)
- window.print(): print current window

## Debugging
## Directory
## Performance
## Testing
## Best practices
## Modules

## Mistakes

## Random
- Vercel
- Dx: developer experience
- Turbopack
- Webpack
- Plugins
- Modular bundling
- Turborepo
- Lint?
- Vite
- Native esm
- Parcel
- Routing
- Directory routes
- Data fetching
- Server components
- Ssr (server side rendering)
- Serialization
- Isr
- Ssg
- Caching
- Remix (forms)
- Api routes
- React query
- Shopify
- Lodash
- Monorepo
- ES modules

# TypeScript

## Plan
- watch youtube tutorials
- no need for the moment
- just start building and expand your knowledge as you go

## Random
- ts is converted to js before use (in browsers at least)

## Interface vs Type?
- object model with predefined props
- you can create must have props and also option to add more props
- type has better syntax?
- basically they are identical?
- interface can be defined multiple times and merged, but type can’t
- when to use this exactly?

## Variable Types
- primitive

## Any
- should not be used

# Reacy
## General
### Lists and keys
- Keys preferably ids. Only on last resort, use index
- Keys go with map() function
- Keys have to be unique between siblings but not globally
- Keys are for react, they don’t go through like props

### Different component
- Using it multiple times
- Makes code less complex

### Fragments
- <> </>
- <React.Fragment>
- Can have keys as attribute

## Routing

## JSX
- JavaScript XML
- HTML in JS

## Events

## React Bootstrap
- Breadcrumbs : something / something / something
- NavBar

## Style, css
- Inline
- Separate object
- Css file
- Modules
- Sass, scss

## Class
- State
- State is similar to props, but it is private and fully controlled by the component

## Funcion
- Hook

## Data
- Data flows down
- Forms

## Props
- Name props from the component’s point of view
- Don’t change props values

## Performance
- Memo
- Using it makes the function to re-render only when it’s props change
- Profiler
- Is there to monitor performance

## Backend communication
## Authentication
## Async

## Portal
![[Pasted image 20260208140900.png]]
![[Pasted image 20260208140904.png]]

## Lib
- Create a file for every third party library and create a “facade pattern”. Use that library only from this location.

# Next
- react framework
- building blocks to create apps
- easier to build fast, SEO-friendly and scalable web apps
- static websites

benefits:
- performance
- SEO
- scalability
- dev exp