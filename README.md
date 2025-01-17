# Heading Tool

![Version of EditorJS that the plugin is compatible with](https://badgen.net/badge/Editor.js/v2.0/blue)
&#x2011;
![Version of TaleSmith that the plugin is compatible with](https://badgen.net/badge/TaleSmith/v0.0.1/B51F3E)

Provides Headings Blocks for the [Editor.js](https://ifmo.su/editor) used in the software TaleSmith by [The Tales Guild](https://thetalesguild.com).

## Installation

### Install via NPM

Get the package

```shell
npm i --save @thetalesguild/editorjs-header
```

Include module at your application

```javascript
const Header = require("@thetalesguild/editorjs-header");
```

### Download to your project's source dir

1. Upload folder `dist` from repository
2. Add `dist/bundle.js` file to your page.

## Usage

Add a new Tool to the `tools` property of the Editor.js initial config.

```javascript
var editor = EditorJS({
  ...

  tools: {
    ...
    header: Header,
  },

  ...
});
```

## Shortcut

You can insert this Block by a useful shortcut. Set it up with the `tools[].shortcut` property of the Editor's initial config.

```javascript
var editor = EditorJS({
  ...

  tools: {
    ...
    header: {
      class: Header,
      shortcut: 'CMD+SHIFT+H',
    },
  },

  ...
});
```

## Config Params

All properties are optional.

| Field        | Type       | Description                 |
| ------------ | ---------- | --------------------------- |
| placeholder  | `string`   | header's placeholder string |
| levels       | `number[]` | enabled heading levels      |
| defaultLevel | `number`   | default heading level       |

```javascript
var editor = EditorJS({
  ...

  tools: {
    ...
    header: {
      class: Header,
      config: {
        placeholder: 'Enter a header',
        levels: [2, 3, 4],
        defaultLevel: 3
      }
    }
  }

  ...
});
```

## Tool's settings

You can select one of six levels for heading.

## Output data

| Field | Type     | Description                                      |
| ----- | -------- | ------------------------------------------------ |
| text  | `string` | header's text                                    |
| level | `number` | level of header: 1 for H1, 2 for H2 ... 6 for H6 |

```json
{
  "type": "header",
  "data": {
    "text": "Welcome to TaleSmith !",
    "level": 2
  }
}
```
