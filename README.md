# msc-collages
[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/msc-collages)

People love collages. With collages we could combined several images together and make them more vivid and interesting. Developers could apply &lt;msc-collages /> instead of annoying HTML code &amp; CSS setting. All we need to do is just make a few setting and everything will be all set. 

## Basic Usage

- Required Script
```
<script 
  type="module"
  src="https://your-domain/wc-msc-collages.js"
</script>
```

- Structure
Put <msc-collages /> into HTML document. It will have different functions and looks with attribute mutation.
```html
<msc-collages>
  <script type="application/json">
    {
      "theme": 8, // 1 ~ 8
      "object-fit": "cover", // cover || contain
      "collages": [
        {
          "link": "?",
          "src": "https://picsum.photos/300/300?grayscale&random=1",
          "alt": "grayscale 1",
          "target": "_blank"
        },
        {
          "link": "?",
          "src": "https://picsum.photos/300/300?grayscale&random=2",
          "alt": "grayscale 2",
          "target": "_blank"
        },
        {
          "link": "?",
          "src": "https://picsum.photos/300/300?grayscale&random=3",
          "alt": "grayscale 3",
          "target": "_blank"
        },
        {
          "link": "?",
          "src": "https://picsum.photos/300/300?grayscale&random=4",
          "alt": "grayscale 4",
          "target": "_blank"
        }
      ]
    }
  </script>
</msc-collages>
```

## JavaScript Instantiation
&lt;msc-collages /&gt; could also use JavaScript to create DOM element. Here comes some examples.
```html
<script type="module">
import { MscCollages } from 'https://your-domain/wc-msc-collages.js';

//use DOM api
const nodeA = document.createElement('msc-collages');
document.body.appendChild(nodeA);
nodeA.theme = 1;
nodeA.collages = [ {...} ];

// new instance with Class
const nodeB = new MscCollages();
document.body.appendChild(nodeB);
nodeB.theme = 2;
nodeB.collages = [ {...}, {...} ];

// new instance with Class & default config
const config = {
  theme: 3,
  collages: [
    {...},
    {...},
    ...
  ]
};
const nodeC = new MscCollages(config);
document.body.appendChild(nodeC);
</script>
```

## Style Customization
&lt;msc-collages /&gt; uses CSS variables to hook uploader trigger theme & drop zone. That means developer could easy change it into the looks you like.
```html
<style>
msc-collages {
  --msc-collages-gap: 1px;
  --msc-collages-overlay: #1d2228;
  --msc-collages-border-radius: 8px;
}
</style>
```

## Attributes
&lt;msc-collages /&gt; supports some attributes to let it become more convenience & useful.

- theme

Set theme id for different usage. Developers could set `1` ~ `8` theme. Default is "`1`".

```html
<msc-collages
  theme="1"
  ...
></msc-collages>
```

- object-fit

Set image render property. This attribute only accept `cover` or `contain`. Default is "`cover`".

```html
<msc-collages
  object-fit="cover"
  ...
></msc-collages>
```

- collages

Set collages data. This should be JSON string and each element needs contains "`link`"、"`src`"、"`alt`"、"`target`" for rendering. Max count is 4.

```html
<msc-collages
  collages='[{"link":"?","src":"https://picsum.photos/300/300?grayscale&random=1","alt":"grayscale 1","target":"_blank"}]'
  ...
></msc-collages>
```

## Properties

| Property Name | Type | Description |
| ----------- | ----------- | ----------- |
| theme | String | Getter / Setter for theme id. |
| object-fit | String | Getter / Setter for image render property. Only accept "`cover`" or "`contain`" |
| collages | Object | Getter / Setter for collages data. |

## Event

| Event Signature | Description |
| ----------- | ----------- |
| msc-collages-click | Fired when <msc-collages /> clicked. Developers could get original click event from `event.detail.baseEvent` to do preventDefault behavior. |

## Reference
- [&lt;msc-collages /&gt;](https://blog.lalacube.com/mei/webComponent_msc-collages.html)
