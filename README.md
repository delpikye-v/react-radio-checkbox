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


### Usage
Install the package 
```js
npm install --save react-radio-checkbox-z

```

Import the module in the place you want to use:
```js
import RadioCheckBox from "react-radio-checkbox-z";
```

Wrap you content in this component:

#### Snippet
```js
    const [value, setValue] = useState('label1') // radio
    // const [value, setValue] = useState(['label1']) // radio || checkbox
    const [options, setOptions] = useState([
        { label: 'label1', value:'label1' },
        'label2',
        'label3',
        ...
        //   { label, value, disabled, className: 'itemClass', labelClassName: 'labelClass' },
    ])

    // don't check duplicate value in options, so please pass unique value
    <RadioCheckBox options={options}
        value={value} // array or string
        onChange={setValue} // event
        theme="tick"  // default || tick || tickFill || fill || in

        // more
        // groupName="item-group-template" // default random unique
        // height="30px"
        // className={className}
        // disabled={true} // disabled all
        // checkBox={true} // input="checkbox"
        // displayBox={true} // display like checkbox
        // vertical={true} // display vertical
        // selectColor="red"  
        // unSelectColor="yellow"
        // tickColor="black"
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
    },
    ...,
    'value' // => make option { label: value, value: value }
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
`default` || `tick` || `tickFill` || `fill` || `in`


#### selectColor (`String`)
color when checked. Default <span style="color: #4169E1">#4169E1</span>


#### unSelectColor (`String`)
color when unchecked. Default <span style="color: #cbd1d8;">[#cbd1d8]</span>


#### tickColor (`String`)
Use when `theme` = `tickFill` || `tick`

`Color of tick when check.`
<small>see demo</small>


#### height
min-height of line-options. `px, %, vh`. (default: `24px`)

#### className
The className added to group.

#### style
The style added to group.

### Example
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
