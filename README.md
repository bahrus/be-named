# be-named [TODO]

be-named is a template element decorator that allows for a dynamic tag name.  This is useful for allowing multiple versions of a custom element to be used in parallel (assuming they register with different names dynamically or via some other mechanism).

It is also useful for lists of tags where the tag name is not known until runtime.

## Syntax

```html
<template be-named=t-b-d be-named-idrefs="light-child-1 light-child-2"></template>
<input be-named-slot=slot1 id=light-child-1>
<details be-named-slot=slot2 id=light-child-2>
</details>
```

generates

```html
<t-b-d>
    <light-children></light-children>
</t-b-d>
```

This may work most effectively where the [markup is not static](https://caniuse.com/mdn-api_customelementregistry_getname), but is generated in a JS setting.


