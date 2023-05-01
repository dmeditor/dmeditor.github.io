[Home](/) | [Development](/development) | [API](/api) | [Data format](/data-format) | [github project](https://github.com/dmeditor/dmeditor)

## Create a widget template(styled widget)

A widget template is customization of a widget. eg. add a background image for heading.

There are 2 ways to styleize a widget, first way is in React( eg. in App.tsx ), second way is in <script> or external js file.

### Way 1. Register from react(eg. in your App.tsx)

See [sample template](https://github.com/dmeditor/dmeditor-sample/blob/main/src/SampleTemplate.tsx)

```typescript
import { css } from "@emotion/css";
import { registerTemplate } from "dmeditor";

registerTemplate({
    blocktype: 'heading',        
    identifier:'Sample', 
    name:'Sample template', 
    css:css`background:#ffcc00; 
    h2{
        text-align:center;
    }`,
    initData: ()=>{
      const data = {type:'heading', settings:{level: 2}};
      return {...data, data:'Hello1', common:{color: '#9C27B0' }}
    }
 }
);
```
### Way 2. Register from global `<script>`
DMEditor reads global variable `dmeditor`'s `templates` property for all templates.

Note: in below code, css property's value is a template string, while in Way 1 it's invoking css function from emotion.

```javascript
var dmeditor = {
templates:[
  {
          blocktype: 'heading',        
          identifier:'sample', 
          name:'Block heading text', 
          css:`background:#ffcc00; 
          h2{
              text-align:center;
          }`,
          initData: ()=>{
            const data = {type:'heading', settings:{level: 2}};
            return {...data, data:'Hello1', common:{color: '#9C27B0' }}
          }, 
      }
]
}
        
```
