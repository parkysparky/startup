# CS 260 Notes

- [My startup](https://startup.cs260.click)
- [My simon](https://simon.cs260.click)

## Helpful links

- [Course instruction](https://github.com/webprogramming260)
- [MasteryLS](https://masteryls.com/)
- [Canvas](https://byu.instructure.com)
- [MDN](https://developer.mozilla.org)

### Web Server Setup  
We are using a preconfigured server for this class.  
AMI ID: `ami-094c4a0be0b642a24` located within the region `US East (N. Virginia) - us-east-1`  
  
### AWS

Oodles of services. Important to set budgets. Any more than 1 elastic IP costs money. I set one so I can use the same IP and associate it with a domain name.  

Access the server from the production directory with the following command:  
`ssh -i keys/production.pem ubuntu@wechoose.click`  

### DNS  
Domains have levels like in the reference image below  
![subdomain.secondary.top](./images/domainNameParts.jpg)


### HTML

**anchor** tag example
```html
<a href="https://github.com/parkysparky/"> author</a>
```

**img** tag example (consider verifying open source image here)
```html
<img src="https://imgs.search.brave.com/5K7j_XVJQwU6JRe8g-TdYe4lyGfwyhp1wuWUotCRsw8/rs:fit:500:0:1:0/g:ce/aHR0cHM6Ly9pbWFn/ZS5zaHV0dGVyc3Rv/Y2suY29tL2ltYWdl/LXBob3RvL2NvbXBv/c2l0aW9uLXZhcmll/dHktZnJ1aXRzLXdp/Y2tlci1iYXNrZXQt/MjYwbnctNjQ1NzQ2/NTMuanBn" alt="Fruit Basket" width="200"> </img>
```

#### Deploying 
Use the script they made, it is easier. This example deploys the given Simon code
```
./deployFiles.sh -k ../keys/production.pem -h wechoose.click -s simon
```
if that does not work, I may need to change the permissions on the script file using the following command
```
sudo chmod +x deployFiles.sh
```


### CSS 
Prof. Christiansen said if we do all 24 levels of [Flexbox Froggy](https://flexboxfroggy.com/) he would give a little extra credit.   

#### **Selectors**

**Combinators**  
CSS styles are applied to HTML elements using selectors. Typically the HTML element name is the selector, and when more precision is needed you apply combinators to the selectors to choose exactly the elements to which you wish to apply a given style rule.  

| Combinator | Meaning | Example | Description |
| :--- | :--- | :--- | :--- |
| Descendant | A list of descendants | `body section` | Any section that is a descendant of a body |
| Child | A list of direct children | `section > p` | Any p that is a direct child of a section |
| General sibling | A list of siblings | `div ~ p` | Any p that has a div sibling |
| Adjacent sibling | A list of adjacent sibling | `div + p` | Any p that has an adjacent div sibling |

**ID selector**  
Any HTML element can have an ID. IDs should be unique so that the CSS applies only to that element  

**Attribute selector**  
Attribute selectors allow you to select elements based upon their attributes. You use an attribute selector to select any element with a given attribute (`a[href]`). You can also specify a required value for an attribute (a[href="./fish.png"]) in order for the selector to match. Attribute selectors also support wildcards such as the ability to select attribute values containing specific text (`p[href*="https://"]`).
```CSS
p[class='summary'] {
color: red;
}
```

**Pseudo selector**  
CSS also defines a significant list of pseudo selectors which select based on positional relationships, mouse interactions, hyperlink visitation states, and attributes.


#### **Declarations**

**Properties**
CSS rule declarations specify a property and value to assign when the rule selector matches one or more elements. There are oodles of possible properties defined for modifying the style of an HTML document. Listed below are the more commonly used ones
|Property          |Value                             |Example          |Discussion                                                                    |
|------------------|----------------------------------|-----------------|------------------------------------------------------------------------------|
|background-color  |color                             |`red`              |Fill the background color                                                     |
|border            |color width style                 |`#fad solid medium`|Sets the border using shorthand where any or all of the values may be provided|
|border-radius     |unit                              |`50%`              |The size of the border radius                                                 |
|box-shadow        |x-offset y-offset blu-radius color|`2px 2px 2px gray` |Creates a shadow                                                              |
|columns           |number                            |`3`                |Number of textual columns                                                     |
|column-rule       |color width style                 |`solid thin black` |Sets the border used between columns using border shorthand                   |
|color             |color                             |`rgb(128, 0, 0)`   |Sets the text color                                                           |
|cursor            |type                              |`grab`             |Sets the cursor to display when hovering over the element                     |
|display           |type                              |`none`             |Defines how to display the element and its children                           |
|filter            |filter-function                   |`grayscale(30%)`   |Applies a visual filter                                                       |
|float             |direction                         |`right`            |Places the element to the left or right in the flow                           |
|flex              |                                  |                 |Flex layout. Used for responsive design                                       |
|font              |family size style                 |`Arial 1.2em bold` |Defines the text font using shorthand                                         |
|grid              |                                  |                 |Grid layout. Used for responsive design                                       |
|height            |unit                              |`.25em`            |Sets the height of the box                                                    |
|margin            |unit                              |`5px 5px 0 0`      |Sets the margin spacing                                                       |
|max-[width/height]|unit                              |`20%`              |Restricts the width or height to no more than the unit                        |
|min-[width/height]|unit                              |`10vh`             |Restricts the width or height to no less than the unit                        |
|opacity           |number                            |`.9`               |Sets how opaque the element is                                                |
|overflow          |[visible/hidden/scroll/auto]      |`scroll`           |Defines what happens when the content does not fix in its box                 |
|position          |[static/relative/absolute/sticky] |`absolute`         |Defines how the element is positioned in the document                         |
|padding           |unit                              |`1em 2em`          |Sets the padding spacing                                                      |
|left              |unit                              |`10rem`            |The horizontal value of a positioned element                                  |
|text-align        |[start/end/center/justify]        |`end`              |Defines how the text is aligned in the element                                |
|top               |unit                              |`50px`             |The vertical value of a positioned element                                    |
|transform         |transform-function                |`rotate(0.5turn)`  |Applies a transformation to the element                                       |
|width             |unit                              |`25vmin`           |Sets the width of the box                                                     |
|z-index           |number                            |`100`              |Controls the positioning of the element on the z axis                         |

**Units**
Units define the size of a property. The table shows a sample of sizing using absolute sizing, relative to the letter 'm' or as a percentage of the parent element, or as a percentage of the viewport.
|Unit|Description                                                     |
|----|----------------------------------------------------------------|
|px  |The number of pixels                                            |
|pt  |The number of points (1/72 of an inch)                          |
|in  |The number of inches                                            |
|cm  |The number of centimeters                                       |
|%   |A percentage of the parent element                              |
|em  |A multiplier of the width of the letter `m` in the parent's font|
|rem |A multiplier of the width of the letter `m` in the root's font  |
|ex  |A multiplier of the height of the element's font                |
|vw  |A percentage of the viewport's width                            |
|vh  |A percentage of the viewport's height                           |
|vmin|A percentage of the viewport's smaller dimension                |
|vmax|A percentage of the viewport's larger dimension                 |


**color**
There are a few key ways to assign color value. They are described in the table below
|Method      |Example                |Description                                                                                                                                                                                                      |
|------------|-----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|keyword     |`red`                    |A set of predefined colors (e.g. white, cornflowerblue, darkslateblue)                                                                                                                                           |
|RGB hex     |`#00FFAA22 or #0FA2`     |Red, green, and blue as a hexadecimal number, with an optional alpha opacity                                                                                                                                     |
|RGB function|`rgb(128, 255, 128, 0.5)`|Red, green, and blue as a percentage or number between 0 and 255, with an optional alpha opacity percentage                                                                                                      |
|HSL         |`hsl(180, 30%, 90%, 0.5)`|Hue, saturation, and light, with an optional opacity percentage. Hue is the position on the 365 degree color wheel (red is 0 and 255). Saturation is how gray the color is, and light is how bright the color is.|

#### **Fonts**
You can import fonts in CSS. You can import open source ones (Google has a bunch) from websites and then style with a fun custom font.
```CSS
@import url('https://fonts.googleapis.com/css2?family=Rubik Microbe&display=swap');

p {
  font-family: 'Rubik Microbe';
}
```

#### **Responsive Design**
**Viewport**

```css
<meta name="viewport" content="width=device-width,initial-scale=1"  
```
This tells the browser to not scale the page.  

**Display Types**   

Here is a table of the Responsive Display Types

|Value |Meaning                                                                                                                 |
|------|------------------------------------------------------------------------------------------------------------------------|
|none  |Don't display this element. The element still exists, but the browser will not render it.                               |
|block |Display this element with a width that fills its parent element. A `p` or `div` element has block display by default.       |
|inline|Display this element with a width that is only as big as its content. A `b` or `span` element has inline display by default.|
|flex  |Display this element's children in a flexible orientation.                                                              |
|grid  |Display this element's children in a grid orientation.                                                                  |


with the given HTML  
```html
<div class="none">None</div>
<div class="block">Block</div>
<div class="inline">Inline1</div>
<div class="inline">Inline2</div>
<div class="flex">
  <div>FlexA</div>
  <div>FlexB</div>
  <div>FlexC</div>
  <div>FlexD</div>
</div>
<div class="grid">
  <div>GridA</div>
  <div>GridB</div>
  <div>GridC</div>
  <div>GridD</div>
</div>
```

styled with the following CSS  
```CSS
.none {
  display: none;
}

.block {
  display: block;
}

.inline {
  display: inline;
}

.flex {
  display: flex;
  flex-direction: row;
}

.grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
}
```

They will generate a website that look like this:

![Types of Responsive Design](./images/readme/responsiveDesignTypes.png)


**@media**
You can use media queries to detect the orientation and size of the user's screen. With this information you can make lots of design decisions. For example, you could choose to make entire pieces of your application disappear, or move to a different location. For example, if we had an aside that was helpful when the screen is wide, but took up too much room when the screen got narrow, we could use the following media query to make it disappear.

```CSS
@media (orientation: portrait) {
  aside {
    display: none;
  }
}
```

The two most important data types for Responsive Design are **grid** and **flex**.  

**Grid**
Example:
HTML:  
```HTML

```

CSS:  
```CSS
.container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  grid-auto-rows: 300px;
  grid-gap: 1em;
}
```

This code yields a program that can dynamically update the arrangement of the grid like so:  
![Updating grid](./images/readme/cssGrid.gif)


**Flex**  
Justify is parallel to direction. align-content is perpendicular to direction. default is horizontal.   


**Frameworks** - premade CSS package that offers numerous classes and functions. Bootstrap was the most popular, it has now been passed up by Tailwind  

If a CSS class is nested inside another, that inheritance can be used in the HTML document



### React

React files use type .jsx that file type is a combination of Javascript and HTML

testing push from new computer

For a required commit I must input the following text: I love web programming
