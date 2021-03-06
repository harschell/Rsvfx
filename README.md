Rsvfx
-----

**Rsvfx** is an example that shows how to connect an Intel [RealSense] depth
camera to a Unity [Visual Effect Graph].

![gif](https://i.imgur.com/K0C80Lf.gif)
![gif](https://i.imgur.com/jBxII0t.gif)

[RealSense]: https://realsense.intel.com/
[Visual Effect Graph]: https://unity.com/visual-effect-graph

System requirements
-------------------

- Unity 2018.3 or later
- Intel RealSense D400 series
- [Git] (required for importing external packages)

This repository only contains Windows and Linux versions of the RealSense
plugin binaries. For macOS, the plugin binary must be installed separately.

This project uses [Git support on Package Manager] to import external
packages. To use the functionality, [Git] must be installed to the system.
See [the forum thread][Git support on Package Manager] for futher details.

[Git]: https://git-scm.com/
[Git support on Package Manager]:
    https://forum.unity.com/threads/git-support-on-package-manager.573673/

How it works
------------

![inspector](https://i.imgur.com/JWEUhXh.png)

The [PointCloudBaker] component converts a point cloud stream sent from a
RealSense device into two dynamically animated attribute maps: position map and
color map. These maps can be used in the "Set Position/Color from Map" blocks
in a VFX graph, in the same way as attribute maps imported from a point cache
file.

![blocks](https://i.imgur.com/mEY3I2d.png)

[PointCloudBaker]: /Assets/Rsvfx/PointCloudBaker.cs

Frequently asked questions
--------------------------

**Is it possible with Kinect v2?**

It's technically possible but requires a lot of changes to the PointCloudBaker
component. I personally am not very motivated to support it because it's a
discontinued product, and a successor product (Azure Kinect) is coming.
Instead, I'd recommend following [Depthkit]. The developer seems to be trying
[VFX Graph support with Depthkit][Depthkit VFX Graph].

**Which RealSense model fits best?**

I personally recommend D415 because it gives the best sample density in the
current models. Please see [this thread][D415 thread] for further information.

[Depthkit]: https://www.depthkit.tv/
[Depthkit VFX Graph]: https://twitter.com/Depthkit/status/1099411381751816193
[D415 thread]: https://twitter.com/_kzr/status/1096282551352619008
