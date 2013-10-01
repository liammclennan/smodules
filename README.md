smodules
========

A tiny implementation of the basic AMD JavaScript modules format. Adds `define` and `require` functions to the window object.

Usage
-----

Call define to define a new module. Give the module a name and specify its dependencies.

    define('a', ['b'], function (b) {
    
        // return module a
        return {
            val: 2
        };

    });

    define('b', [], function () {

        return {
            double: function (i) {
                return i * 2;
            }
        };

    });

    var a = require('a'),
        b = require('b');

    b.double(a.val);
    // => 4
