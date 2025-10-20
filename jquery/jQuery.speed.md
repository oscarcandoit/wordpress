---
url: https://api.jquery.com/jQuery.speed/
scraped_at: 2025-10-20T03:08:17.343Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.speed( \[duration \] \[, settings \] )Returns: [PlainObject](http://api.jquery.com/Types/\#PlainObject)

**Description:** Creates an object containing a set of properties ready to be used in the definition of custom animations.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [jQuery.speed( \[duration \] \[, settings \] )](https://api.jquery.com/jQuery.speed/\#jQuery-speed-duration-settings)

  - **duration** (default: `400`)

    Type: [Number](http://api.jquery.com/Types/#Number) or [String](http://api.jquery.com/Types/#String)

    A string or number determining how long the animation will run.

  - **settings**

    Type: [PlainObject](http://api.jquery.com/Types/#PlainObject)


    - **easing** (default: `swing`)

      Type: [String](http://api.jquery.com/Types/#String)

      A string indicating which easing function to use for the transition.

    - **complete**

      Type: [Function](http://api.jquery.com/Types/#Function)()

      A function to call once the animation is complete.
- #### version added: [1.1](https://api.jquery.com/category/version/1.1/) [jQuery.speed( \[duration \] \[, easing \] \[, complete \] )](https://api.jquery.com/jQuery.speed/\#jQuery-speed-duration-easing-complete)

  - **duration** (default: `400`)

    Type: [Number](http://api.jquery.com/Types/#Number) or [String](http://api.jquery.com/Types/#String)

    A string or number determining how long the animation will run.

  - **easing** (default: `swing`)

    Type: [String](http://api.jquery.com/Types/#String)

    A string indicating which easing function to use for the transition.

  - **complete**

    Type: [Function](http://api.jquery.com/Types/#Function)()

    A function to call once the animation is complete, called once per matched element.
- #### version added: [1.1](https://api.jquery.com/category/version/1.1/) [jQuery.speed( settings )](https://api.jquery.com/jQuery.speed/\#jQuery-speed-settings)

  - **settings**

    Type: [PlainObject](http://api.jquery.com/Types/#PlainObject)


    - **duration** (default: `400`)

      Type: [Number](http://api.jquery.com/Types/#Number) or [String](http://api.jquery.com/Types/#String)

      A string or number determining how long the animation will run.

    - **easing** (default: `swing`)

      Type: [String](http://api.jquery.com/Types/#String)

      A string indicating which easing function to use for the transition.

    - **complete**

      Type: [Function](http://api.jquery.com/Types/#Function)()

      A function to call once the animation is complete.

The `$.speed()` method provides a way to define properties, such as `duration`, `easing`, and `queue`, to use in a custom animation. By using it, you don't have to implement the logic that deals with default values and optional parameters.

This method is meant for plugin developers who are creating new animation methods. Letting `$.speed()` do all the parameter hockey and normalization for you, rather than duplicating the logic yourself, makes your work simpler. An example of use can be found in the animated form of `.addClass()` of jQuery UI.