Mobile Detect
=============

This is a lightweight mobile detection based on the [Mobile_Detect.php](http://mobiledetect.net/) library,
which can be obtained from the [GitHub repository](https://github.com/serbanghita/Mobile-Detect).

This module is intended to aid developers utilizing mobile-first and responsive design techniques who also have a need 
for slight changes for mobile and tablet users. An example would be showing (or hiding) a block or content pane to a particular device.

This module is not intended (and never will be enhanced) to provide theme switching or redirection; other modules already provide this functionality.

Requirements
------------

As noted, this module does not include the actual Mobile_Detect library.  This should be downloaded or cloned from
one of the links above and placed in

 - sites/all/libraries/Mobile_Detect

or somewhere  the [Libraries API](http://drupal.org/project/libraries) (if present) can find it, eg

 - sites/default/libraries/Mobile_Detect
 - sites/example.com/libraries/Mobile_Detect
 
Once the module is installed and enabled, browse to the Status Report page (admin/reports/status) and confirm that
the library is found.  The PHP file should have a pathname that is similar to

 - sites/all/libraries/Mobile_Detect/Mobile_Detect.php
 
If you think everything is installed correctly, you may need to clear the Drupal caches (admin/config/development/performance).
 
For testing purposes, the demo.php and unit tests included with the library can be deployed, but these should not exist
on a live production server.

Usage
-----

The base module just provides a factory method for creating a singleton of the mobile detection class,
for use in themes and other modules:

<code>$detect = mobile_detect_get_object();
$is_mobile = $detect->isMobile();</code>

See the documentation for the Mobile_Detect library for more information.

ctools Support
--------------

A sub-module is included for integration with ctools.  Once enabled, a "Mobile Detect: device type" will show up
in the list of selection and access rules.  When this is used, the list of device types is dynamically built from
the rules present in the Mobile_Detect library, and you can use any combination of AND/OR/NOT logic that you need.

Note that the Mobile_Detect considers tablet devices as also being mobile devices.  When you have both tablet and
mobile device selection in use, it is best to place the tablet rules first.  For example, when using with for Panel page
selection rules, place the Table variant before the Mobile variant.

Problems, Bugs, Suggestions, Etc.
---------------------------------

Problems with the actual Mobile_Detect library should be directed to the GitHub issue queue.

Problems with this module and sub-modules should be directed to the Drupal issue queue for this project.

Future
------

A sub-module for creating Context conditions is also planned.

