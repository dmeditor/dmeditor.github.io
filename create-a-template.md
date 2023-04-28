
[Home](/) | [Create a widget](/create-widget) | [Create a template](/create-a-template.md) | [API](/api) | [Data format](/data-format) | [github project](https://github.com/dmeditor/dmeditor)

## Create a widget template(styled widget)

A widget template gives freedom of styling a widget with mostly only css. eg. add a line under h2. Those styled widgets are mostly specific for your projects.

There are 2 ways to styleize a widget, first way is in React( eg. in App.tsx ), second way is in <script> or external js file.

### Way 1. Register from react(eg. in your App.tsx)

```javascript
import { registerTemplate } from "dmeditor";

registerTemplate(
        blocktype: 'heading',        
        identifier:'blocktext_heading_sample', 
        name:'Block heading text', 
        css:`background:#ffcc00; 
        h2{
            text-align:center;
        }`,
        initData: ()=>{
          const data = {type:'heading', settings:{level: 2}};
          return {...data, data:'Hello1', common:{...data.common, color: '#9C27B0' }}
        }
);
```
### Way 2. Register from global `<script>`
DMEditor reads global variable `dmeditor`'s `templates` property for all templates.

```javascript
var dmeditor = {
templates:[
  {
          blocktype: 'heading',        
          identifier:'blocktext_heading_sample', 
          name:'Block heading text', 
          css:`background:#ffcc00; 
          h2{
              text-align:center;
          }`,
          initData: ()=>{
            const data = {type:'heading', settings:{level: 2}};
            return {...data, data:'Hello1', common:{...data.common, color: '#9C27B0' }}
          }, 
      }
]
}
```
