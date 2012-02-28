NSURL+ResourceUtils
================================

Adds a new constructor to NSURL:

    + (NSURL*) URLWithResourceName:(NSString *)key

It allows you to separate URL resources for debug and release.
This is useful when you have a test environment and a production
environment with different URLs, and it also avoids the need to
hard-code URLs.

Usage
================================

Drag NSURL+ResourceUtils.h, NSURL+ResourceUtils.m into your project.

Create plist files (File>New>Resource>Property List) named Debug.plist
and Release.plist.

Add URLs to the property lists, one string entry for every URL you need.

Then;

    NSURL *url = [NSURL URLWithResourceName:@"login"];

Note
================================

The method relies on the DEBUG flag to be set for debug builds. If
DEBUG is not set, it will use "Release.plist" instead. Of course,
you can modify this to your own needs.

Copyright
--------------------------------
Copyright (c) 2012 Ulf Urdén. See source files for license details.
