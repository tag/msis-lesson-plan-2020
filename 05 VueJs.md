# Open time
  - Docker text questions?

# Mental Health Check
  - Stages of team development
    - Forming, Storming, Norming, Performing
  - Using Teams (general channel, private chat)

<!-- # Schema?
  * Two groups should present their proposed schema.
    - Make sure at least one NoSQL and one RDMS
    - Which is better?
    - What will we use?

  * For now, access the JSON stubs available via Canvas modules page -->

# History of Vue, ... Vue3

## Vue3

From https://stackoverflow.com/questions/66625010/how-to-fetch-data-in-vue-3

```
<div id="beer">
  {{ message }}
</div>

const Breweries = {
    data() {
        return {
            message: ""
        }
    },
    mounted() {
        fetch('https://api.openbrewerydb.org/breweries/', {
            headers: { 'Content-type': 'application/json' },
        }).then(res=>res.json()).then((response) => {
            this.message = response;
        }).catch( (error) => {
            this.message = error;
        });
    }
}
Vue.createApp(Breweries).mount('#beer')
```

# HW review

  - JSON schemas?
  - CSV schemas?

### File paths review

As used in CSS, `<img>`, `<a>` links, and scripts.
    * Relative
        - `../` back up a level
        - `./` current folder
    * Relative from root
        - Leading `/`
    * Common protocol
        - `://`
    * Fully qualified
        -`[protocol]://[domain]/[path]/[file]`

Hints about getting the file path in Windows (copy/paste from Windows Explorer)

# Review Data presentation
  "04 Thoughts on data.pptx"

# NoSQL

  * Which is better, and why? (Group breakouts)
  * Relate back to CAP theorem
    - https://blog.nahurst.com/visual-guide-to-nosql-systems


# Intro to VueJS

  * Demo [the VueJS website]()

  * Load VueJS via CDN

    ```html
    <!-- development version, includes helpful console warnings -->
    <!-- WARNING: Vue.js v2; in 2021 we use Vue3 -->
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
    ```

  * Create a new JS file and include it as well
    ```js
    var myApp = new Vue({
      el: '#someId',
      data: {
        name: 'Tom'
      }
    }
    ```

  * We need two things in our js for a VueJS app: the app declaration and the linked element (using the `el` key in the app declaration)
    - Add these now

  * With the app active use the "double mustache".  `{{ 2+2 }}
    - Try to add the same `{{2+2}}` snip elsewhere on the page. What happens?
    - **TIP:** Don't make the parent of your app `<body>` as Vue changes/refreshes the element's DOM regularly, and using body is not recommended.

  // * SKIP for now Use a [IIFE function](https://en.wikipedia.org/wiki/Immediately-invoked_function_expression), an "Immediately Invoked Function Expression"

  * Test to see whether the app is active!

  * Explain the `data` element. There are others, like `methods` and `computed`

  * Elements within `data` can be accessed directly as if HTML were simply a template. For example, `<span>{{name}}</span>` becomes `<span>Tom</span>`.

  * ACTIVITY: Take a moment and (using the provided JSON stub) fill in project name, and start date.
  * https://github.com/tag/msis-triage-2020/blob/master/app/public/dummy/pt-one.php

## Dates suck

###

### Old Stuff (for historical interst)
_This section is retained, but we won't be using moment.js in 2021._ It's been retired, and is no longer recommended for new projects.

#### Alternatives to moment.js

* https://day.js.org/docs/en/parse/string

#### Previous content:

Let's use moments.js to make dates suck less.

Load the moments.js file (from CDN?)

  ```html
  <script src="https://cdnjs.cloudflare.com/ajax/libs/moment.js/2.22.2/moment.min.js"></script>
  ```

* Then use the `methods` key of our Vue declaration:

  ```js
  {
    // ...
    methods: {
      prettyDate: function (d) {
        return moment(d).format('l')
      }
    }
  }
  ````

* Try wrapping the dates in `prettyDate()`

* Even better would be to use computed values. Do that.

* EXERCISE: Figure out how to do the days left math using moments.js, and implement as a computed method.
