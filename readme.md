# DOM Observer

Fast and reliable DOM observer.


## Install

```
npm install @wide/dom-observer --save
```


## Usage

### Observe selector

```
observe(selector, { bind[, unbind] })
```
- `selector` query selector to observe
- `bind(el)` hook called when an element matching the selector appears in the DOM
- `unbind(el)` hook called when this same element is removed from the DOM (optional)

Exemple:
```js
import observe from '@wide/dom-observer'

observe('[data-foobar]', {
  bind: el => console.log(`I'm in the DOM !`),
  unbind: el => console.log(`I'm no longer in the DOM...`)
})
```

### Unobserve selector

Delete observer for a specific selector, all related elements will be unbinded

```
unobserve(selector)
```

Exemple:
```js
import { unobserve } from '@wide/dom-observer'

unobserve('[data-foobar]')
```

## Unbind element

Unbind all selectors for a specific element.

```
unbind(el)
```

Exemple:
```js
import { unbind } from '@wide/dom-observer'

unbind(document.querySelector('#id'))
```

## Get selector's binded elements

Retrieve the list of binded elements by selector.

```
seek(selector)
```

Exemple:
```js
import { seek } from '@wide/dom-observer'

seek('[data-foobar]') // Array<HTMLElement>
```


## Authors

- **Aymeric Assier** - [github.com/myeti](https://github.com/myeti)
- **Julien Martins Da Costa** - [github.com/jdacosta](https://github.com/jdacosta)


## License

This project is licensed under the MIT License - see the [licence](licence) file for details