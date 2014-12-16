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