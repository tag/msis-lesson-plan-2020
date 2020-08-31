# !!! QUIZ !!!

## Loops

<ul id="example-1">
  <li v-for="item in items">
    {{ item.message }}
  </li>
</ul>

* Exercise: Implement the task table?

## Event Handlers
Explain events,
    - event capture, bubbling

There are multiple ways of handling events with vanilla Javascript, but since we're diving in to VueJS, let's do it the Vue way:

This doesn't work
  ```html
  <div class="row">
        
  </div>
  ```
  ... because methods inside a Vue declaration are bound to the app's context. We would need to create a wrapper method inside the app to handle this
  
  ```html
  <div class="row">
    <button v-on:click="yell('foo')">Click Me</button>
  </div>
  ```
  ```js
  methods: {
    yell: function (msg) {
      alert(msg)
    }
  }
  ```
  
### Exercise: Build a click counter
  
## Common events & Vue life cycle

  * Common events include
    - click
    - DOMContentLoaded
    - load
    - Vue has special handlers for others, expecially keyup events on particular keys
    
  * The `DOMContentLoaded` and `load` events won't work like you expect in Vue. (They won't be processed until after those events have occurred) Instead, hook into the [Vue lifecycle](https://vuejs.org/v2/api/#Options-Lifecycle-Hooks) and the [lifecycle diagram](https://vuejs.org/v2/guide/instance.html#Lifecycle-Diagram)
    - Based on that lifecycle diagram, where would be a good place to asynchronously fetch data?
    - `beforeCreate` would be a good option ...


## Promise API

```js
  created () {
    fetch("https://raw.githubusercontent.com/tag/iu-msis/dev/public/project1.json")
      .then( response => response.json() )
      .then( json => {
        //this.project = json;
        console.log(json)}
      );
    }
```

## Next time
### v-model