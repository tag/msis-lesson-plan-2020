# Schema?

  * Two groups should present their proposed schema.
    - Make sure at least one NoSQL and one RDMS
    - Which is better?
    - What will we use?
    
  * For now, access the JSON stubs available via Canvas modules page

# HW review

### File paths
(Note: lessons have been edited to cover this earlier in the future)

As used in CSS, `<img>`, `<a>` links, and scripts.
    * Relative
        - `../` back up a level
    * Relative from root
        - Leading `/`
    * Common protocol
        - `://`
    * Fully qualified
        -`[protocol]://[domain]/[path]/[file]`

Also:
- emails
- form types

# Intro to VueJS

  * Demo [the VueJS website]()

  * Load VueJS via CDN
    
    ```html
    <!-- development version, includes helpful console warnings -->
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
  
  * We need two things for a VueJS app: the app declaration and the linked element (using the `el` key in the app declaration)
    - Add these now
  
  * With the app active use the "double mustache".  `{{ 2+2 }}
    - Try to add the same `{{2+2}}` snip elsewhere on the page. What happens?
    - **TIP:** Don't make the parent of your app `<body>` as Vue changes the refreshes the element's DOM regularly, and using body is not recommended.
  
  * [SKIP for now] Use a [IIFE function](https://en.wikipedia.org/wiki/Immediately-invoked_function_expression), an "Immediately Invoked Function Expression"
    
  * Test to see whether the app is active!
  
  * Explain the `data` element. There are others, like `methods` and `computed`
  
  * Elements within `data` can be accessed directly as if HTML were simply a template. For example, `<span>{{name}}</span>` becomes `<span>Tom</span>`.
  
  * ACTIVITY: Take a moment and (using the provided JSON stub) fill in project name, and start date.

## Dates suck

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


