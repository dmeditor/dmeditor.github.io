
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

| Key | Required | Description | Example  |
|------|---|----|---|
|  `type`  | true  | Block type's identifier, unique   |  `'text'` |
|  `data`  | false | It differs depends on block type. In principle it means the 'value'   |  `'http://test.com/svg.png'` in `image` block type |
| `children` | false  | Children widgets. Useful for componsite widgets(widet inside a widget). |
|  `common`  | false  | Common settings, eg. margin to top, padding.   |  `{marginTop: 10}` - margin to top is 10 pixel |
|  `settings` | false   |  It differs depends on block type. In principle it means the settings.  | In heading `{level: 2}` means using h2 |
|  `source`   | false |  It differs depends on block type. In principle it means the data source configuration (fixed or dyanmic).  | In image: `source:{sourceType: 'input'}`|
