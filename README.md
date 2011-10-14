I love Device APIs, even the non-standard ones. This is a web-based compass application for iOS5 devices.

It's been tested on iPhone 4 hardware. Should work fine on iPhone 4S. Layouts are probably slightly strange on the iPad.

Try it out directly on http://jamesgpearce.github.com/compios5/

This uses the browser's new webkitCompassHeading property of the device orientation event. http://lists.w3.org/Archives/Public/public-geolocation/2011Jul/0014.html

The compass itself is created entirely with CSS.

A couple of implementation notes:

 - There's easing on the rotation to make it a little less jerky, but this has to be turned off whenever the compass spins through north. CSS transitions do not wrap-around transforms.

 - window.orientation needs to be added to the heading so that a landscape view still points to physical north

 - Media queries detect orientation so that the compass stays in the center of the screen. It's not quite stationary on a portrait->landscape flip, but great the other way.

This won't work on any device apart from a real iPhone. There's no way to simulate heading changes in the iOS simulator that I can find.