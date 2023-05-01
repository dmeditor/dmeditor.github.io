

[Home](/) | [Create a widget](/create-widget) | [Create a template](/create-a-template.md) | [API](/api) | [Data format](/data-format) | [github project](https://github.com/dmeditor/dmeditor)

## API

For using DM Editor



### DMEditor
Use DM Editor for editing.

Property|Required|Type|Description|
------|---|-----|----|
data|true|Array\<any\>|Data for editing. See [data format](./data-format) for detail.|
onChange|false|(data: Array\<any\>)=>void| Trigged when there is data change
browseImage|false|(props:BrowseProps)=>JSX.Element|When calling browse image, by default it will propmpt a input dialog|
browseLink|false|(props:BrowseProps)=>JSX.Element|When calling browse image, by default it will propmpt a input dialog|
pageTab|false|()=>JSX.Element|Function component to render page tab|
getFileUrl|false|(path:string)=>string|When get file url. Path is used if it's not set|
getImageUrl|false|(path:string)=>string|When getting image url. Path is used if it's not set|
  

### DMEditorView
Use DM Editor for viewing.

Property|Required|Type|Description|
------|---|-----|----|
data|true|Array\<any\>|See [data format](./data-format) for detail.|
getFileUrl|false|(path:string)=>string|When get file url. Path is used if it's not set|
getImageUrl|false|(path:string)=>string|When getting image url. Path is used if it's not set|

<!--
### BrowseProps
  
Property|Required|Type|Description|
------|---|-----|----|
type|true|'file'\|'image'|Image or file|
adding||||
onConfirm||||
onCancel||||
defalutValue||||  



  
## For creating widget

### ToolDefinition

### BlockList

### Ranger

### PickColor

### PropertyGroup

### PropertyItem
-->

## Developing widget

### registerTool

Name|Parameter|Description
-----|---|---|
registerTool|ToolDefinition|Register a block type to the system.

Below is a ToolDefinition example:

```javascript
{
    type: 'image',
    name: 'Image',
    menu:  {category:'basic',icon: <ImageOutlined /> },
    initData: ()=> {type:'image', data:'http://test.com/svg.png', settings:{}},
    view: (props:{data:any})=><BlockImage view={true} data={props.data} inBlock={false} active={false} onChange={()=>{}} />,
    render: (props:ToolRenderProps)=><BlockImage {...props} />
}
```

### ToolDefinition

Property|Type|Description
-----|---|---|
type|string| Type of the block type
menu|object. See example above| The block type shown in the tool menu after clicking 'plus'(add) icon.
initData|any see [data format](/data-format)| Initial data of the block type
view| (props:{data:any})=>JSX.ReactElement| When rendering in view mode, most case reuse `render`'s implementation with view = tue
render|(props:ToolRenderProps)=>JSX.ReactElement| When rendering in edit mode

### ToolRenderProps


Property|Required| Type |Description|
-----|--|---|-----|
data|true|any see [data format](/data-format)|data of the widget
active|true|boolean| If it's active(selected when mouse clicks)
adding|false|boole| If it's adding
view|false|boolean| If it's viewing
inBlock|false|boolean| If it's inside another widget
onChange|true|(data:any, debounce?:boolean)=>void| Callback when change. Use debounce when change is intense (eg. text typing).
onCancel|false|()=>void| Callback when cancel adding the widget
onDelete|false|()=>void| Callback when delete is triggered


### Device hook
Hook `useGetDevice` from `dmeditor/utils` can be used to detect mode. Returns 'mobile'|'tablet'|''

