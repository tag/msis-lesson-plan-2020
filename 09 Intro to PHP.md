# Review recent HW

# Architecture review
(group exercise)


# Set up files

  ```
    # File structure should look something like this:

    [DocumentRoot]
      +- app   (php app specific files; will be private)
      +- public
      |  +- api   (php api endpoints files)
      |  +- css   (folder)
      |  +- js    (folder, holds js lib files)
      |  |  +- app (optional; could organize Vue js app files to go here)
      |  |  |  - my.app.js  (etc., etc.)
      |  |  +- lib  (optional; holds 3rd-party js, such as Vue)
      |- index.html
  ```



# Test PHP

- Create a `phpinfo()` page to make sure everything is working. Call it `info.php`.

```php
<?php

phpinfo();
```


# bugs I had to fix

* php.ini comments
* docker-compose env loading
* gitignore

# Intro to PHP

  * Show [php.net](http://php.net/docs.php) as a good source for documentation

  * PHP allows a mix between static and dynamic content in the same file. However, this is poor practice. PHP files begin with `<?php`. Some resources will tell you to close your PHP tags (`?>`). Don't. As we will never mix PHP with static content, we don't need to. Also, closing PHP tags can lead to hard to find errors in bigger applications.

  * Variable names start with `$`

  * PHP is an interpreted, curly-brace language

  * Discuss "associative arrays"
    - *very* similar to JSON objects

  * "Super-globals", `$_GET`, `$_POST`, `$_SERVER` (especially `$_SERVER['REQUEST_METHOD']`)
    - Can print an array with `print_r()` or `var_dump()`
    - Echo these, then practice by changing GET variables in the URL.
