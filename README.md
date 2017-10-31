# Using "for" directive in JSX

[![GitHub stars](https://img.shields.io/github/stars/HuQingyang/babel-plugin-jsx-for-directive.svg?style=social&label=Stars&style=plastic)](https://github.com/HuQingyang/babel-plugin-jsx-for-directive)
[![GitHub forks](https://img.shields.io/github/forks/HuQingyang/babel-plugin-jsx-for-directive.svg?style=social&label=Fork&style=plastic)](https://github.com/HuQingyang/babel-plugin-jsx-for-directive)
[![npm](https://img.shields.io/npm/dw/babel-plugin-jsx-for-directive.svg)](https://www.npmjs.com/package/babel-plugin-jsx-for-directive)
[![npm](https://img.shields.io/npm/v/babel-plugin-jsx-for-directive.svg)](https://www.npmjs.com/package/babel-plugin-jsx-for-directive)
[![npm](https://img.shields.io/npm/l/babel-plugin-jsx-for-directive.svg)](https://www.npmjs.com/package/babel-plugin-jsx-for-directive)

A easy-to-use "for" directive solution for front-end frameworks using JSX like React.


**See Also:**
* Using two-way data binding in JSX: [babel-plugin-jsx-two-way-binding](https://github.com/HuQingyang/babel-plugin-jsx-two-way-binding) 
* Using if-directive in JSX: [babel-plugin-jsx-if-directive](https://github.com/HuQingyang/babel-plugin-jsx-if-directive)


## 1. Install
`npm install --save-dev babel-plugin-jsx-for-directive`

## 2. Basic Usage
Edit your __.babelrc__ file:
```json
{
  "plugins": [
    "jsx-for-directive"
  ]
}
```
In your jsx file:
```jsx harmony
class App extends React.Component {
    constructor(props) {
        super(props);
        this.state = {
            languages: ['JavaScript', 'TypeScript', 'Python', 'Rust', 'Scala']
        }
    }

    render() { return (
        <div>
            <ul>
                <li for={"lan in this.state.languages"}>{lan}</li>
            </ul>
        </div>
    )}
}
```


## 3. Usage with "index"
In your jsx file:
```jsx harmony
class App extends React.Component {
    constructor(props) {
        super(props);
        this.state = {
            languages: ['JavaScript', 'TypeScript', 'Python', 'Rust', 'Scala']
        }
    }

    render() { return (
        <div>
            <ul>
                <li
                    for={"(lan, index) in this.state.languages"}
                    key={index}
                >{lan}</li>
            </ul>
        </div>
    )}
}
```

## 5. Usage with custom attribute name
Edit your __.babelrc__ file:
```json
{
  "plugins": [
    "jsx-for-directive", 
    { 
      "attrName": "r-for" 
    }
  ]
}
```

In your jsx file:
```jsx harmony
class App extends React.Component {
    constructor(props) {
        super(props);
        this.state = {
            languages: ['JavaScript', 'TypeScript', 'Python', 'Rust', 'Scala']
        }
    }

    render() { return (
        <div>
            <ul>
                <li r-for={"lan in this.state.languages"}>{lan}</li>
            </ul>
        </div>
    )}
}
```