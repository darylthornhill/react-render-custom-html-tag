## React Render In Custom Html Tag

This is a package that helps you use custom html tags to render your react components. You can apply html attributes to these custom html tags and the attributes will get passed through to your React Component as props.


## Code Example

In Html set up your custom html tag.

```<custom-htmltag></custom-htmltag>```

In your react, import this package and use it when instantiating your class. 

```
import React from 'react';
import renderInCustomHtmlTag from '../../index.js';

class ExampleComponent extends React.Component {
    constructor(props){
        super(props);
    }
    

    render(){
        const props = this.props;

        return ()
            <React.Fragment>
                <h1>Hello World</h1>
            </React.Fragment>
        );
    }
}

renderInCustomHtmlTag(ExampleComponent, 'custom-htmltag')
```

And that should be it. Your React Component should be injected into the page.

### Attributes and Properties

On the custom html tag that you create you can also give it attributes that get passed through to the React component as properties, We also parse some of the values as json if possible.

```<custom-htmltag name='Jeff' data='{"someProp":"JSON parsed","value":2}'></custom-htmltag>```

In your React Component you can get access to these by calling your props.

``` const name = this.props.name; // string```

``` const data = this.prop.data; // object```


## Why?

We had a couple of project that we wanted to use react and sprinkle it through a normal html/php file. We found that our js started to fill up with a lot of **ReactDom.Renders**, with some vanilla js having to parse some of the properties that we wanted to pass into those components. So I build this, hopefully it helps some other people out.



## Installation

(when i get around to it NPM)
Currently just clone it and use the **index.js**  file in your project

## Examples

Download the project and change to that directory. Install components.

```npm install```

Run the compiler

```npm run build```

Open up the **example/index.html** file and see how it works.
