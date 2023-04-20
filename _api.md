## For using DM Editor

### DMEditor

Property|Required|Type|Description|
------|---|-----|----|
data|true|Array<any>||
browseImage|false|(props:BrowseProps)=>JSX.Element|When calling browse image, by default it will propmpt a input dialog|
browseLink|false|(props:BrowseProps)=>JSX.Element|When calling browse image, by default it will propmpt a input dialog|
pageTab|false|()=>JSX.Element|Function component to render page tab|
getFileUrl|false|(path:string)=>string|When get file url. Use path if it's not set|
getImageUrl|false|(path:string)=>string|When getting image url. Use path if it's not set|
  

### DMEditorView


Property|Required|Type|Description|
------|---|-----|----|
data|true|Array<any>||
getFileUrl|false|(path:string)=>string|When get file url. Use path if it's not set|
getImageUrl|false|(path:string)=>string|When getting image url. Use path if it's not set|

### BrowseProps
  
Property|Required|Type|Description|
------|---|-----|----|
type||||
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
