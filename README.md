# be-named [TODO]

be-named allows for a dynamic tag name.  This is useful for allowing multiple versions of a custom element to be used in parallel (assuming they register with different names dynamically or via some other mechanism).

It is also useful for lists of tags where the tag name is not known until runtime.

## Syntax

```html
<template be-named=t-b-d>
    <light-children></light-children>
</template>
```

generates

```html
<t-b-d>
    <light-children></light-children>
</t-b-d>
```

This may work most effectively where the markup is not static, but is generated in a JS setting.

```JavaScript
import { myCustomElement } from './my-custom-element.js';

function render(){
    return html`
        <template be-named=${myCustomElement.isReally}>
            <light-children></light-children>
        </templated>
    `;
}
```