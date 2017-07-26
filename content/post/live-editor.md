+++
title = "Live Editor"
date = "2017-07-27T23:51:59-04:00"
tags = ["blender", "editor", "live", "view"]
featured_image = "images/screen.png"
description = "A new blender editor"
+++

A couple of days ago I decided to make another attempt to add a live view editor to blender. All previous attempts failed so far, but I found a nice [tutorial](https://wiki.blender.org/index.php/Dev:Source/UI/Tutorials/AddAnEditor) explaining how to add one to blender 2.65. Some things have changed in the mean time in the blender source code, but the tutorial still covers about 80%. I've been using the clip editor as inspiration and copied quite some code over to the live view editor. I'm glad I got blender to compile and create an empty editor. Unfortunately the header toolbar is still missing and all the operators need to be implemented. The code slowly starts to make more sense although it's still difficult to figure out what belongs where and how to debug everything.

## Why add a new editor
The new editor provides a way to interact with a live stream from any camera. Currently the development is targeted towards a proof of concept and therefore OpenCV will be added as a dependency, whereas in the future possibly a plugin system will be developed allowing different APIs to interact with the editor. This will possibly be done via python bindings, dropping all dependencies for the blender core application.

As interacting with live streams require specific functionality it was decided not to clutter other editors and create a new editor. Plugins will be able to target this new editor and add new functionality as needed, but the basic functionality is added statically to blender. The live view editor can be used in many different fields of animation such as;

* Augmented reality
* 3D scanning (laser / structured light / etc)
* Scene reconstruction / tracking (giving immediate feedback which can be helpful in some applications)
* Stop motion

For me the last item is of the most interest. Stop motion is one of the oldest animation arts. There is a number of commercial software available to assist in recording frames and pre- and post-production. However there is no open source alternative available that provides extended functionality. The open source domain mainly provides what can be called frame grabbers. By adding a live view editor to blender, I believe blender could immediately be a commercial grade stop motion alternative in the open source domain. When all this succeeds I hope that blender will create interest and stimulate new development in this beautiful art and craft.
