
[Home](/) | [Create a widget](/create-widget) | [API](/api) | [Data format](/data-format) | [github project](https://github.com/dmeditor/dmeditor)

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

### Mobile styling & rendering
For mobile styling, there are 2 typical ways: 
- 1) Use `dmeditor-view-mobile` as css class filter 
- 2) Use `useGetDevice` for custom rendering.

We recommand trying to use way 1), because it's better for performance, but sometimes way 2) is almost the only way(eg. move image to top of the widget in mobile if it's hard only using css).


### Device hook
Hook `useGetDevice` from `dmeditor/utils` can be used to detect mode. Returns 'mobile'|'tablet'|''


### Css classes

class |Description|
------|-----|
dmeditor-view | Root class for viewing |
dmeditor-view-mobile | Mobile view |
dmeditor-view-tablet | Tablet view |
block-container | container div for a block element |
inblock | Same level as block-container, if the widget is embed in other widget, this class will be added to .block-container |
block-type-\<type\> | Child of block-container, for each widget. eg. `block-type-image` |

### Css variables

Below css variables are for css `calc` function only.

variable |Description|
------|---|
dme-main-width|DMEditor's root element in pixel
dme-container-width|Width of DM Editor's 'container', used for eg. setting full screen. By default it's 100vw, but if you want to embed full screen image to another container, change this variable in css of that container. 




