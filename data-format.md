
[Home](/) | [Create a widget](/create-widget) | [API](/api) | [Data format](/data-format) | [github project](https://github.com/digimakergo/dmeditor)

## Data format

Here is an example:

```javascript
[
    { type:'image',
      data:'http://test.com/svg.png'
     },
     { 
      type:'heading', 
      data:'News', 
      common:{marginTop: 10},
      settings:{level: 2}
    }
]
```

| Key | Type | Required | Description | Example  |
|-----|--|---|----|---|
|  `type` | string | true  | Block type's identifier, unique   |  `'text'` |
|  `id`  | string |true | Unique id ( just needs to be unique under a parent)  |  `'sdddxffxdd'` |
|  `data`  | object | false | It differs depends on block type. In principle it means the 'value'   |  `'http://test.com/svg.png'` in `image` block type |
| `children`| array | false  | Children widgets. Useful for componsite widgets(widet inside a widget). | Widget including a image and heading:  `type:'my_image_heading', children:[{type:'image', data {url:'http://example.com/image.png'} },{type:'heading', data:'News',settings:{level: 2} }]`|
|  `common`| object | false  | Common settings, eg. margin to top, padding.   |  `{marginTop: 10}` - margin to top is 10 pixel |
|  `settings` | object | false   |  It differs depends on block type. In principle it means the settings.  | In heading `{level: 2}` means using h2 |
|  `source`  | object  | false |  It differs depends on block type. In principle it means the data source configuration (fixed or dyanmic).  | In image: `source:{sourceType: 'input'}`|
