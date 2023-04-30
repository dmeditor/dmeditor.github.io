[Home](/) | [Create a widget](/create-widget) | [Create a template](/create-a-template.md) | [API](/api) | [Data format](/data-format) | [github project](https://github.com/dmeditor/dmeditor)

## Create your widget

Below is a simple example which rendering a fixed url's image and set a input box so the user can enter width.  *Check [Sample widget implementation](https://github.com/dmeditor/dmeditor-sample/blob/main/src/SampleWidget.tsx) as example*
### Step 1. Implement a widget
```typescript
import { css } from "@emotion/css";
import { Input, Slider } from "@mui/material";
import { BlockProperty, ToolDefinition, ToolRenderProps } from "dmeditor";

import {PropertyGroup, PropertyItem, Ranger} from 'dmeditor/utils';
import { useState } from "react";

//Implementation
export const SampleWidget = (props:ToolRenderProps)=>{
   ///add status control here
   const [width, setWidth] = useState(300);

    return <div>
    {/* property */}           
            <BlockProperty blocktype={'sample'}>
                <PropertyItem label="Width">       
                    <Slider aria-label="Width" valueLabelDisplay="auto" defaultValue={width} step={5} max={800} onChange={(e, v)=>setWidth(v as number)} />             
                </PropertyItem>               
            </BlockProperty>

            <div style={ {width: width} } className={css`height:300px; background:#ffe3e3`}>
            {props.data.data} <br />
            Width: {width}</div>        
            </div>
}


//Define toolSampleWidget
export const toolSampleWidget:ToolDefinition = {
    type: 'sample',
    name: 'Sample widget',
    menu:  {category:'basic',icon: <span>A</span> },
    initData: ()=>{return {type:'sample', data:'This is a sample.', settings:{}}},
    view: (props:{data:any})=><SampleWidget view={true} data={props.data} inBlock={false} active={false} onChange={()=>{}} />,
    render: (props:ToolRenderProps)=><SampleWidget {...props} />
}

```

### Step 2. Register the tool(and new category) (can be in App.tsx)

```typescript
import { registerTool, registerCategory } from "dmeditor";

//register a category if it doesn't exist
registerCategory({identifier:'content', text:'Content'});

//register the tool
registerTool(toolSampleWidget);
```


### Styling

For styling, DM Editor uses emotion css, so you are free to style whatever you want. We have some predefined css variables & classes so you can use in your widget: See [Mobile styling & rendering ](/api#mobile-styling--rendering-when-developing-a-widget)


### Library for intraction(eg. dropdown, input)
For intraction, you can use third party libaray in side `BlockProperty`, eg. Boostrap React / MUI / Ant design. We use MUI for intraction(input, model, dropdown, etc) for now.


#### Data format

See [data format](/data-format) for more.

