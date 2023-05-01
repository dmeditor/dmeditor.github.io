
[Home](/) | [Create a widget](/create-widget) | [Create a template](/create-a-template.md) | [API](/api) | [Data format](/data-format) | [github project](https://github.com/dmeditor/dmeditor)

DM Editor is a block-based visual editor, written in React.

### Highlights
- Block based, real WYSIWYG(What you see is what you get)
- Intractive while editing, eg. click a tab and edit a tab's content
- Basic widgets: rich text, image, heading, table, video, iframe
- Intractive widgets: tab, accordion
- Get benefits of React ecosystem for creating widget, eg. sliding, resizing, dialog.
- Super easy to create widget template (mostly only css)

### Screenshots

<a href="https://www.digimaker.com/var/images/w/wzz/upload-2038061186-screen1.png"><img width="500px" src="https://www.digimaker.com/var/images/w/wzz/upload-2038061186-screen1.png" /></a>

<a href="https://www.digimaker.com/var/images/l/loe/upload-103887251-screen2.png"><img width="500px" src="https://www.digimaker.com/var/images/l/loe/upload-103887251-screen2.png" /></a>

### Installation

```
npm install dmeditor
```

### Usage

[Sample project](https://github.com/dmeditor/dmeditor-sample)

#### Edit
```typescript
import {DMEditor} from 'dmeditor';

//...
<DMEditor data={[]} />
```

#### View
```typescript
import {DMEditorView} from 'dmeditor';

//...
<DMEditorView data={data} />
```

#### Templates
Put below in your html to use our open source templates:

```html
<script src="https://cdn.jsdelivr.net/gh/dmeditor/templates@main/templates.js"></script>
```

### Server side rendering

DM Editor can be used directly in server side rendering via eg. NextJs. For non-nodejs environment(eg. .NET), you can run [dmeditor-server](https://github.com/dmeditor/dmeditor-server) to output html&js&css.


### Widgets
[dmeditor-digimaker](https://github.com/digimakergo/dmeditor-digimaker/):  - Content widgets(eg. content grid, Gallary) for digimaker CMF

Leave a messge [here](https://github.com/dmeditor/dmeditor/issues/1) if you want to promote your widgets.


### Templates CDN
See [https://github.com/dmeditor/templates](https://github.com/dmeditor/templates) to use template CDN. Welcome to send pull request to add your templates.

