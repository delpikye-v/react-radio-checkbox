<div align="center">
    <h1>react-radio-checkbox-z</h1>
    <strong>
        <a href="https://github.com/delpikye-v/react-radio-checkbox">react-radio-checkbox-z</a>
    </strong>
    <br />
    <br />
    <a href="https://codesandbox.io/s/react-radio-checkbox-z-51sg3">LIVE EXAMPLE</a>
</div>

---
<span>You can customize <b>icon</b>, <b>theme</b> or <b>color</b> for <b>Checkbox/Radio</b></span>

<b><small>React / <a href="https://www.npmjs.com/package/vue-radio-checkbox-z">Vue</a> / <a href="https://www.npmjs.com/package/svelte-radio-checkbox-z">Svelte</a></small></b>

### Usage
Install the package 
```js
npm install --save react-radio-checkbox-z
```

Import the module in the place you want to use:
```js
import RadioCheckBox from "react-radio-checkbox-z";
```

#### Snippet
```js
    const [value, setValue] = useState('label1') // radio
    // const [value, setValue] = useState(['label1']) // radio || checkbox
    const [options, setOptions] = useState([
        { label: 'label1', value:'label1' },
        'label2',
        'label3',
        // ...more,
        // { label, value, disabled, className: 'itemClass', labelClassName: 'labelClass' },
    ])

    // don't check duplicate value in options, so please pass unique value
    <RadioCheckBox
        options={options}
        value={value} // array or string
        onChange={setValue} // event
        theme="tick"  // see props
        // more =>
        // groupName="item-group-template" // default random unique
        // height="30"          // min-height option
        // boxSize="16"         // box-size 16 x 16
        // className={className}
        // disabled={true}      // disabled all
        // checkBox={true}      // input="checkbox"
        // displayBox={true}    // display like checkbox
        // vertical={true}      // display vertical
        // selectColor="any"    // color when selected
        // unSelectColor="any"  // color when no selected
        // hoverColor=any       // color when hover (default like selectColor)
        // tickColor="any"      // only theme (type `tick/x`)
        // tabFocusColor        // keypress tab (shawdow box: #000)
        // checkedIcon          // custom icon

        // (Box size is affected by: `box-sizing: border-box`)
      />
```

### Props

The following props are accepted:

#### value (`Array` || `String`)

Selected value.

#### onChange (`Function`)
Update value

#### groupName (`String`)
<p>groupName of radio/checkbox. Default (random) unique of RadioCheckBox</p>

<small>if you want to use multiple RadioCheckBox(same name), you can set the group name</small>
```js
    <RadioCheckBox groupName="groupabc" theme="in" ... />
    <RadioCheckBox groupName="groupabc" theme="fill" ... />
```

#### options (`Array`)
list data like. `[Object, String, ...]`
```js
[
    {
        label: 'Display', value: 'value', disabled: false,  // disabled option
        className: 'itemClass', labelClassName: 'labelClass'
        jsx // in case you want to change the label to a complex element,
        checkedIcon // it is url or exact icon (SEE LIVE EXAMPLE)
    },
    ...,
    'value' // => make option { label: value, value: value }

    // ex: [ { value: '1', disabled: true, jsx: <span>xyzmrer....</span> }... ]
]
```

#### disabled (`boolean`)
Disabled all options. Default `false`

#### checkBox (`boolean`)
Type is checkbox. Default `false` (radio)


#### displayBox (`boolean`)
Show check mark icon like a checkbox. Default `false` (radio)


#### vertical (`boolean`)
Display vertical `true`. Defaut `false`


#### theme (`String`)
```js
    // default (nothing) of html
    in: [
        'fill', 'in', 'out',
        'tick', 'tick-fill', 'tick-fill-in',
        'x', 'x-fill', 'x-fill-in'
    ]
```


#### selectColor (`String`)

color when checked. Default <span style="color: #4169E1">[#4169E1]</span>


#### unSelectColor (`String`)

color when unchecked. Default <span style="color: #cbd1d8;">[#cbd1d8]</span>

#### hoverColor (`String`)

color when hover. Default using (selectColor)


#### tickColor (`String`)
Use when `theme` type = `tick..` || `x..`

`Color of tick when check.`


#### tabFocusColor (`String`)
box shadow color when focus by tab. (`#000`)             

#### height (`number` or `number_px`)
min-height of line-options. (default: `24px`)

#### boxSize (`number` or `number_px`)
size of check. (default: `16px`)

#### className
The className added to group.

#### checkedIcon

customize checked icon (see live example)


<br />

###### customize icon check (another solution)
`You should refrain from using this method.`

<small>
With theme: `x...` || `tick...` <br />You can override css to see custom tick.
</small>

```css
/* set your className(.itemClass) for selector unique */
.itemClass.ldk-rc-radio-checkbox .rc-option-checked .rc-option-icon {
    background: url('./cal-blue.png') no-repeat center;
}
.itemClass.ldk-rc-radio-checkbox .rc-option-checked .rc-option-icon::before {
    content: '' !important;
}
```

#### style
The style added to group.

### Example
<a href="https://codesandbox.io/s/react-radio-checkbox-z-51sg3">LIVE EXAMPLE</a>

A working example can be found in the `example` directory.

```js
npm install
```
```js
npm run dev
npm run start
```

### License
MIT
