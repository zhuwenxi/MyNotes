# Notes of CSS Definition Guide

## Selector

### Universal Selector
1. `* {color: red;}`: Universal selector.

### Class Selector
2. `.classA.classB {color: red}`: Multi-class selector.

### Attribute Selector
3. `h[class] {}`: Attribute selector.
4. `h[class="p"]`: Attribute selector based on exact attribute value.
5. `h[class~="p"]`: Select whose attribute contains "p".
6. `h[class^="p"]`: ...begin with p.
7. `h[class$="p"]`: ...end with p.
8. `h[class*="p"]`: ...contains substring p.
9. `h[class|="p"]`: ...is equal to "p" or start with "p-".

### Descendant Selector
1. `h1 em {color: grey}`

### Children Selector
1. `h1 > strong {color: red}`

### Sibling Selector
1. `h1 + p {margin-top: 0}`

## Pseudo Class and Pseudo Element
###  Link Pseudo Class
1. `:link`: Refers to any anchor not been visited.
2. `:visited`: Refers to anchors visited.

### Other Pseudo Class
1. `:focus`
2. `:hover`
3. `:active`
4. `:first-child`: select who is the first child of it's parent.

### Pseudo Element
1. `first-letter`
2. `first-line`

## Color

### Named Color
1. `aqua`: 浅绿色。 rgb(0%, 100%, 100%)（看上去像是青色）
2. `fuchsia` : 紫红色。rgb(100%, 0, 100%)
3. `lime`：绿黄色。rgb(0, 100%, 0)（这个才像浅绿色嘛）
4. `olive`：橄榄色。 rgb(50%, 50%, 0)（墨绿）
5. `marron`：栗色。 rgb(50%, 0，0)（枣红色）
6. `navy`：海军蓝。rgb(0, 0, 50%)（深蓝）
7. `teal`：茶色。rgb(0, 50%, 50%)（靛青）

Remaining: white, black, gray, silver, red, green, blue, yellow, orange, purple.  （颜色值可以查看P82的表）

### Color by RGB
1. Percentage Notation: e.g. rgb(100%, 100%, 100%)。 (Webkit系的浏览器似乎不支持这种方式，IE没有测过。// 看上去似乎是中文输入法百分号捣的乱)
2. Integer-triplet Notation: e.g. rgb(255, 255, 255).
3. Hexadecimal RGB Color: e.g. #FF0000.
4. Shortened Hexadecimal RGB Color: e.g. #FFF

### Web-safe Color
能被20%整除的颜色值是安全的，例如rgb(20%, 40%, 80%)或者rgb(51, 102, 255)

## Length Units

### Absolute Length Units
1. `in`: Inches. (1 inch = 2.54 centimeter) 
2. `cm`: Centimeters.
3. `mm`: Millimeters.
4. `pt`: Points. (1 inch = 72 point)
5. `pc`: Picas. (1 picas = 12 point)

### Relative Length Units
1. `em`:  Equal to current `font-size` , e.g. If current `font-size` is 14px, then 1em = 1px.
2. `ex`: Like `em`, the value equal to a lowercase "x". (Many user agent get "ex" by dividing "em" in half.)

## Font 
### font-family
1. *Serif*: Times, Georgia.
2. *Sans-Serif*: Helvetica, Geneva, Verdana, Arial and Univers.
3. *Monospace*: Each character is exactly the same width as others. No serif.
4. *Cursive*: To emulate human handwriting.
5. *Fantasy*

### font-weight
Values could be: normal, bold, bolder, lighter, 100, 200, 300, 400, 500, 600, 700, 800 and 900.

### font-size
Values could be: xx-small, x-small, small, medium, large, x-large, xx-large, smaller, larger, &lt;length>, &lt;percentage>. Among these values, "medium" is default, which is usually 16px.
 
## Text
### text-indent
 Values: `<length> | <percentage> | inherit`, the value could be negative and *only apply to inline element*.

### text-align
Values: `left | center | right | justify | <string> | inherit`, *only apply to inline element* .

### line-height
Control the distance between baselines (Leading: 行距).
Values: `<length> | <percentage> | <number> | normal | inherit`, among these values, *number* means the scaling factor, who respect to it's *font-size*.

### vertical-align
Values: `baseline | sub | super | top | text-top | middle | bottom | text-bottom | <percentage> | <length> | inherit`, *vertical-align* only applies to inline element.

### word-spacing
Values: `<length> | normal | inherit`

### letter-spacing
Values: `<length> | normal | inherit`

### text-transform
Value: `uppercase | lowercase | capitalize | none | inherit`

### text-decoration
Values: `none | underline | overline | line-through | blink | inherit`, *text-decoration* is not inherited.

### text-shadow
Values: `color length length length`

### white-space
Values: `normal | nowrap | pre | pre-wrap | pre-line | inherit`

### direction
Text direction.
***

## Box Model	
P208

1. `width` and `height` don't apply to inline non-replaced elements.

### border-style
Values: `none | hidden | dotted | dashed | solid | double | groove | ridge | inset | outset`

## Background

### background-image
`background-image: url(...)`

### background-repeat
Values: `repeat | repeat-x | repeat-y | no-repeat | inherit`

### background-position

### background-attachment
Value:s: `scroll | fixed | inherit`

## Floating and Positioning

### float
1. Values: `left | right | none | inherit`.
2. *margins* around floated elements don't collapse.
3. A floated element generates a block box, regardless of the kind of the element it is. You have to set a *width* for the floated element.

### Nine rules of the floated element's placement.
1. 浮动元素向左/右浮动不能超过它父元素的content。
2. 后续的浮动元素不能覆盖之前的浮动元素，最多能“紧靠”着前一个浮动元素。
3. 一个左浮动的元素不能和一个右浮动的元素相互覆盖，他们会显现在不同的行上。
4. 浮动元素不能超出父元素的上界。
5. 浮动元素的不能超过上一个浮动元素的上界。
6. 浮动元素的上界不能超过它之前一个inline元素的上界。
7. 左浮动元素的右边框不能超过父元素的右边框，除非它自己太宽了。
8. 浮动元素必须被放置在它能到达的最高点（在符合其它规则的前提下）。
9. 一个左浮动的元素必须放置在尽量左的地方（在符合规则8的前提下）

### 负的margin值导致的覆盖
inline覆盖floated, floated覆盖block。

### clear
Values: `left | right | both | none | inherit	`

### position
Values: `static | relative | absolute | fixed | inherit`

### min-height, min-width, max-height & max-width

### overflow
Values: `visible | hidden | scroll | auto | inherit`

### clip
Values: `rect(top, right, bottom, left) | auto | inherit`, only applies to *absolute* position.

### visibility
Values: `visible | hidden | collapse | inherit`

### absolute position
1. absolute元素的父元素是它最近的一个position值不是static的祖先。
### top: auto | left: auto的奇妙
P322

### z-index