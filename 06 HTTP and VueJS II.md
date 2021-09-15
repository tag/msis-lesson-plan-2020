
# Mental Health Check
  - Stages of team development
    - Forming, Storming, Norming, Performing
  - Using Teams (general channel, private chat)


# HW Review:

* Bootstrap 5
* 404 on favicon.ico
  - Go get a new favicon? (Search free favicons)
* Review the `Dockerfile` from the HW
  - Copy `Dockerfile` and `docer-compose.yml` from the HW; explain each step.
  - When being built, every line in the Dockerfile actually creates a new image.
* Also review Apache config (and copy to our project repo)


# Review readings

## StackOverflow DEveloper Survey
https://insights.stackoverflow.com/survey/2019#technology

Vue? JS? Python? Docker?

## Hierarchical databases

  * Precursor to relational databases; included these in the readings, as they still exist
  * Common ones include LDAP, Microsoft Active Directory, your file system
  * What are some issues with hierarchical databases?
    - Can't easily model many:many relationships
    - Can't easily model complex relationships (now we use aliases/shortcuts/soft links, etc.)

## Denormalization

  * What is it? Why would we do it?

  * One of the readings gives an incorrect example of denormalization (https://www.vertabelo.com/blog/denormalization-when-why-and-how/)
    - He confuses historical data (`product_sold.price`) with current data (`product_offered.price`). These are **not** the same attribute! It only seems like it because of the similar name. One can be updated without changing the other.

  * What did Jeff Atwood say about normalization?

# HTTP
(Nearly all of this is in the slide deck)

## Request

## Response


# More VueJs

## Review: Last time?

* `v-bind`
* Loops, `v-for`

  ```javascript
  <ul id="example-1">
    <li v-for="item in items">
      {{ item.message }}
    </li>
  </ul>
  ```

## Promise API

Every `fetch()` returns a [`Promise` object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

A `Promise` has three states:
 * pending
 * fulfilled / complete (`then()`)
 * rejected / error (`catch()`)

Both `then()` and `catch()` return promise objects, so these may be chained.

```js
async mounted() {

        //Method 1:
        fetch('https://randomuser.me/api/', {
            // headers: { 'Content-type': 'application/json' },
        })
        .then(response => response.json())
        .then((responseJson) => {
            console.log(responseJson);
            this.result = responseJson.results[0];
            this.message = this.result.name;
        })
        .catch( (error) => {
            this.message = error;
            console.error(error);
        });


        //Method 2:
        // const response = await fetch("https://randomuser.me/api/");
        // const responseJson = await response.json();

        // console.log("Two:", responseJson);
        // this.message = responseJson.results[0].name;
        // this.result = responseJson.results[0];

    }

```

## Common events & Vue life cycle

  * Common events include
    - click
    - DOMContentLoaded
    - load
    - Vue has special handlers for others, expecially keyup events on particular keys

  * The `DOMContentLoaded` and `load` events won't work like you expect in Vue. (They won't be processed until after those events have occurred) Instead, hook into the [Vue lifecycle](https://vuejs.org/v2/api/#Options-Lifecycle-Hooks) and the [lifecycle diagram](https://vuejs.org/v2/guide/instance.html#Lifecycle-Diagram)
    - Based on that lifecycle diagram, where would be a good place to asynchronously fetch data?
    - `beforeCreate` would be a good option ...


## Event Handlers
Explain events,
    - event capture, bubbling

There are multiple ways of handling events with vanilla Javascript, but since we're diving in to VueJS, let's do it the Vue way:

This doesn't work
  ```html
  <div class="row">
    <button onclick="yell('foo')">Click Me</button>
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

## Next time
### v-model
