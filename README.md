smodules
========

A tiny implementation of the basic AMD JavaScript modules format. Adds `define` and `require` functions to the window object.

Usage
-----

Call define to define a new module. Give the module a name and specify its dependencies.

    define('a', [], function () {
    
        // return module a
        return {
            val: 2
        };

    });

    define('b', ['a'], function (a) {

        return {
            doubleA: function () {
                return a.val * 2;
            }
        };

    });

    var b = require('b');

    b.doubleA();
    // => 4
