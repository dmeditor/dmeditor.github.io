## Create a template

Here is an template example, which contains an image, a heading(with Gradient style) and a text.

```typescript
import { registerTemplate } from "dmeditor";

registerTemplate(
    { blocktype: 'list', 
    id:'heading_text', 
    name:'Heading text',  
    data:{
        type: 'list',
        children: [
            {
             type:'image', 
              data:{url:'https://cdn.jsdelivr.net/gh/dmeditor/templates@main/forsythia_1280.jpg'}
            },
            {
             type:'heading', 
            settings:{level:2},
            style: 'gradient',
            data:'Heading'
            },
            {
             "type":"text", id:'a2', "data":[
                {type:"paragraph","children":[
                    {"text":"Default text 1"}
                ]},           
              ]
            }
           ]          
        }
     },
     );
     
```
