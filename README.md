
[Home](/) | [Development](/development) | [API](/api) | [Data format](/data-format) | [github project](https://github.com/dmeditor/dmeditor)

DM Editor is a block-based visual editor, written in React.

[Online Demo](https://demo.dmeditor.io/editor)

### Highlights
- Block based, real WYSIWYG(What you see is what you get)
- See immediate change while slding padding, width, color, margin, etc
- Intractive widgets like tab, accordion
- Get benefits of React ecosystem for creating widget.
- Style a widget (widget template)

### Screenshots

<a href="https://www.digimaker.com/var/images/w/wzz/upload-2038061186-screen1.png"><img width="500px" src="https://www.digimaker.com/var/images/w/wzz/upload-2038061186-screen1.png" /></a>

<a href="https://www.digimaker.com/var/images/l/loe/upload-103887251-screen2.png"><img width="500px" src="https://www.digimaker.com/var/images/l/loe/upload-103887251-screen2.png" /></a>

### Installation

```
npm install dmeditor
```
*Note: to develop widgets, suggest to install `@mui/material` and `@emotion/css` so you get all benefits of mui and emotion css. See sample project for detail.*
## Usage
Easy way is to clone [Sample project](https://github.com/dmeditor/dmeditor-sample)

### For edit
```typescript
import {DMEditor} from 'dmeditor';

//...
<DMEditor data={[]} />
```

### For view
```typescript
import {DMEditorView} from 'dmeditor';

//...
<DMEditorView data={data} />
```

### Templates
Put below in your html to use our open source templates:

```html
<script src="https://cdn.jsdelivr.net/gh/dmeditor/templates@main/templates.js"></script>
```

### Widgets
[dmeditor-digimaker](https://github.com/digimakergo/dmeditor-digimaker/):  - Content widgets(eg. content grid, Gallary) for digimaker CMF

Leave a messge [here](https://github.com/dmeditor/dmeditor/issues/1) if you want to promote your widgets.


### Templates CDN
See [https://github.com/dmeditor/templates](https://github.com/dmeditor/templates) to use template CDN. Welcome to send pull request to add your templates.


## SSR (Server side rendering)

DM Editor can be used directly in server side rendering via eg. NextJs. For non-nodejs environment(eg. .NET), you can run [dmeditor-server](https://github.com/dmeditor/dmeditor-server) to output html&js&css.
