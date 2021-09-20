# Mental Health Check
  - Stages of team development
    - Forming, Storming, Norming, Performing
  - Using Teams (general channel, private chat)

# Readings review

* 2021: (from last time): Normalization!
* Data Warehousing
* Emil's article: What is w rong with his example?

# More Vue:

```js
{
  data() { /*...*/ },
  computed: {}, // <-- NEW
  methods: {}, // <-- NEW
  created() { /*...*/ }
}
```
# Date & Time

## 2021: We'll use Day.js rather than Moment.js
https://day.js.org/docs/en/installation/browser

```js
dayjs('2021-09-20').format('D MMM YYYY');
```

# Browser & Vue events

## EXERCISE: [3 minutes in group, make a list as long as you can]
  * Google the list of Javascript events
  * Especially review form events
  *   - Difference between `onclick` and `onsubmit`

## Common events & Vue life cycle

  * Common DOM events include
    - click
    - DOMContentLoaded
    - load
    - Vue has special handlers for others, especially keyup events on particular keys

  * The `DOMContentLoaded` and `load` events won't work like you expect in Vue. (They won't be processed until after those events have occurred) Instead, hook into the [Vue lifecycle](https://vuejs.org/v2/api/#Options-Lifecycle-Hooks) and the [lifecycle diagram](https://vuejs.org/v2/guide/instance.html#Lifecycle-Diagram)
    - Based on that lifecycle diagram, where would be a good place to asynchronously fetch data?
    - `beforeCreate` (Vue2)would be a good option ...


## Event Handlers
Explain events,
    - [event capture, bubbling](https://www.quirksmode.org/js/events_order.html)
    - TODO: Add to readings

## <form> and how it works
  * MAYBE: (Review) labels

  * `action` attribute
    - `preventDefault` on events
    - Vue Event handling:
        * (v2) https://vuejs.org/v2/guide/events.html
        * (v3) https://v3.vuejs.org/guide/events.html#event-modifiers
  * method

## Events the Vue3 way
There are multiple ways of handling events with vanilla Javascript, but since we're diving in to VueJS, let's do it the Vue way:

This doesn't work
```html
<div class="row">
  <button onclick="yell">Click Me</button>
</div>
```
... because methods inside a Vue declaration are bound to the app's context. We would need to create a wrapper method inside the app to handle this

```html
<div class="row">
  <button v-on:click="yell">Click Me</button>
</div>
```
```js
methods: {
  yell: function (event) {
    alert("Foo")
  }
}
```

## MUST mention `Event.preventDefault()`

```html
  <form @submit.prevent="onRefresh">
    <button type="submit">Refresh</button>
  </form>
```

** Show effects of `preventDefault()` in the Console, in the Network tab

### Exercise: Build a click counter


# Readings:
  - Difference between data and metadata
  - Three states of data: at rest, in use, in motion
  - Serialization (URL-encode vs JSON)



# Project introduction
(Push another day)

# VueJS: Two-way binding
(Push another day)
## v-model


# Implement Triage:
  - click on left side to send to middle
  - form submit to send to right side

# HTTP: Review
## Review GET and POST

  * parameters
  * URL encoding
  * Key value pairs (Easter eggs in headers)


# Two-way data binding with VueJS
Review Vue's `.prevent` on event handler
  * Notice how the page is reloading without it?
Practice by making an "Add New Patient" form


# Introduce the group case!
