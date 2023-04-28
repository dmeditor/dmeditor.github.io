[Home](/) | [Create a widget](/create-widget) | [Create a template](/create-a-template.md) | [API](/api) | [Data format](/data-format) | [github project](https://github.com/dmeditor/dmeditor)

## Create your widget

Below is a simple example which rendering a fixed url's image and set a input box so the user can enter width.  *Check [Full Image implementation](https://github.com/digimakergo/dmeditor/blob/main/src/blocks/BlockImage.tsx) as example*
### Step 1. Implement a widget
```javascript

//define a tool
import { ToolRenderProps } from "dmeditor";

import {PropertyGroup, PropertyItem, Ranger} from 'dmeditor/utils';

//Implementation
export const BlockImage = (props:ToolRenderProps)=>{
   ///add status control here
   const [url, setUrl] = useState(props.data.data as string);
   const [width, setWidth] = useState(300);

    return <div>
    {/* property */}           
            <BlockProperty title={'Image'} active={props.active}>
                <PropertyItem label="Width">
                    <input type="text" defaultValue={width} onChange={(e)=>setWidth(parseInt(e.target.value))} />
                </PropertyItem>               
            </BlockProperty>

            <img width={width} src={imageUrl} />        
            </div>
}


//Define toolImage
export const toolImage = {
    type: 'image',
    name: 'Image',
    menu:  {category:'basic',icon: <ImageOutlined /> },
    initData: ()=> {type:'image', data:'http://test.com/svg.png', settings:{}},
    view: (props:{data:any})=><BlockImage view={true} data={props.data} inBlock={false} active={false} onChange={()=>{}} />,
    render: (props:ToolRenderProps)=><BlockImage {...props} />
}
```

### Step 2. Register the tool(and new category) (can be in App.tsx)

```typescript
import { registerTool, registerCategory } from "dmeditor";

//register a category if it doesn't exist
registerCategory({identifier:'content', text:'Content'});

//register the tool
registerTool(toolImage);
```


### Styling

For styling, DM Editor uses emotion css, so you are free to style what every you want. We have some predeined css variable & classes so you can use in your widget: See [Mobile styling & rendering ](/api#mobile-styling--rendering-when-developing-a-widget)


### Library for intraction(eg. dropdown, input)
For intraction, you can use third party libaray in side `BlockProperty`, eg. Boostrap React / MUI / Ant design. We use MUI for intraction(input, model, dropdown, etc) for now.


#### Data format

See [data format](/data-format) for more.

