# wc-external-scripts-behavior

## Installation

Bower dependency:
```
    "wc-external-scripts-behavior": "https://github.com/seabourne/wc-external-scripts-behavior.git"
```


## Usage
```
<link rel="import" href="../../../bower_components/wc-external-scripts-behavior/external-scripts-behavior.html">
```

`ApplicationBehaviors.ExternalScriptsBehavior` adds a property `externalLoaded` and two setting properties `externalJS` and `externalCSS` for specifing third-party scripts your component needs to load before running. Define the settings and add an observer to initialize your component when scripts have loaded:

```

class YourComponent {
  beforeRegister() {
    this.properties = {
      ...
      externalJS: {
        value: ['http://path/to/js', ...]
      },
      externalCSS: {
        value: ['http://path/to/css', ...]
      }
    }
    this.behaviors = [
      "ApplicationBehaviors.ExternalScriptsBehavior"
    ]
    this.observers = [
      "_loaded(externalLoaded)"
    ]

  }
  _loaded(loaded) {
    ...
  }
}

```
