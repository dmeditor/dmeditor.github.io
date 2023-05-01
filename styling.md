[Home](/) | [Development](/development) | [API](/api) | [Data format](/data-format) | [github project](https://github.com/dmeditor/dmeditor)

# Styling

### Mobile styling & rendering when developing a widget
For mobile styling, there are 2 typical ways: 
- 1) Use `dmeditor-view-mobile` as css class filter 
- 2) Use `useGetDevice` for custom rendering.

We recommand trying to use way 1), because it's better for performance, but sometimes way 2) is almost the only way(eg. move image to top of the widget in mobile if it's hard only using css).


### Device hook
Hook `useGetDevice` from `dmeditor/utils` can be used to detect mode. Returns 'mobile'|'tablet'|''

### Css variables

Below css variables are for css `calc` function only.

variable |Description|
------|---|
dme-main-width|DMEditor's root element in pixel
dme-container-width|Width of DM Editor's 'container', used for eg. setting full screen. By default it's 100vw, but if you want to embed full screen image to another container, change this variable in css of that container. 



### Css classes

class |Description|
------|-----|
dmeditor-view | Root class for viewing |
dmeditor-view-mobile | Mobile view |
dmeditor-view-tablet | Tablet view |
dme-block-container | container div for a block element |
inblock | Same level as block-container, if the widget is embed in other widget, this class will be added to .block-container |
dme-block | Block element, children of block container
dme-blocktype-\<type\> | Child of block-container, for each widget. eg. `block-type-image` |
dme-blocklist|Block list container, eg. in Image Text widget, heading and text are under `dme-blocklist`

### Css classes in widgets
TBD
