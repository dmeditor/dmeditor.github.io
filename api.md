
[Home](/) | [Create a widget](/create-widget) | [API](/api) | [Data format](/data-format) | [github project](https://github.com/digimakergo/dmeditor)

## API

For using DM Editor

### DMEditor

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
