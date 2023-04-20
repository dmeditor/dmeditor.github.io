
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

| Key | Description | Example  |
|------|----|---|
|  `type`    | Block type's identifier, unique   |  `'text'` |
|  `data`    | Variant types depends on block type. In principle reflect the 'value'   |  `'http://test.com/svg.png'` in `image` block type |
|  `common`    | General settings   |  `{marginTop: 10}` - margin to top is 10 pixel |
|  `settings`    |  Variant types depends on block type  | In heading `{level: 2}` means using h2 |
|  `source`    |  Variant types depends on block type. In principle reflect fixed or dyanmic data source  | In image: `source:{sourceType: 'input'}`|
