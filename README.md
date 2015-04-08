dark-overlay-sliding-menu-animator
==================================

A sliding menu animator for [OnsenUI](http://onsen.io) which provides a darker overlay.

Installation
------------

Install with [bower](http://bower.io):

	bower install dark-overlay-sliding-menu-animator


Usage
-----

Use the [ons-sliding-menu](http://onsen.io/reference/ons-sliding-menu.html) component and set the `type` attribute to something like 'dark-overlay':

```html
<ons-sliding-menu
  menu-page="menu.html" main-page="main.html"
  type="dark-overlay" max-slide-distance="260px" swipeable="true" />
```

Register the animator in the `controller` responsible for interacting with the `ons-sliding-menu`:

```javascript
(function(){
  'use strict';

  var module = angular.module('AppController', []);

  module.controller('AppController', [
    '$scope',
    'SlidingMenuView',
    'DarkOverlaySlidingMenuAnimator',
    function($scope, SlidingMenuView, DarkOverlaySlidingMenuAnimator) {

    SlidingMenuView.registerSlidingMenuAnimator('dark-overlay',
        new DarkOverlaySlidingMenuAnimator());
  }]);
})();
```

The `type` attribute in your markup must match the `name` argument passed to `SlidingMenuView.registerSlidingMenuAnimator()`.


License: [Apache 2.0](http://www.apache.org/licenses/LICENSE-2.0)
