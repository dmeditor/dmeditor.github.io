[Home](/) | [Development](/development) | [API](/api) | [Data format](/data-format) | [github project](https://github.com/dmeditor/dmeditor)

## Create a widget style

A widget style is customizing style of a widget. eg. add a background image for heading.

There are 2 ways to styleize a widget, first way is in React( eg. in App.tsx ), second way is in <script> or external js file.

### Way 1. Register from react(eg. in your App.tsx)

See [sample style](https://github.com/dmeditor/dmeditor-sample/blob/main/src/SampleStyle.tsx)

```typescript
import { css } from "@emotion/css";
import { registerStyle } from "dmeditor";

registerStyle({
    blocktype: 'heading',        
    identifier:'Sample', 
    name:'Sample style', 
    css:css`background:#ffcc00; 
    h2{
        text-align:center;
    }`
 }
);
```
### Way 2. Register from global `<script>`
DMEditor reads global variable `dmeditor`'s `styles` property for all styles.

Note: in below code, css property's value is a style string, while in Way 1 it's invoking css function from emotion.

```javascript
var dmeditor = {
styles:[
  {
          blocktype: 'heading',        
          identifier:'sample', 
          name:'Block heading text', 
          css:`background:#ffcc00; 
          h2{
              text-align:center;
          }` 
      }
]
}
        
```
