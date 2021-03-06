# 0.51.0 - April 2019

* ***(FEATURE)*** `router.hqOriginalSteps` - Support for highest quality optimized originals for smaller images (400x400 by default). Will only impact newly generated OO's.
* ***(FEATURE)*** `lossless` - Option to enable lossless WebP via `/ll` path.


# 0.50.0 - March 2019

* ***(BREAKING)*** `embed` - Removal of deprecated function.
* ***(ENHANCEMENT)*** Sharp - Upgrade to latest Sharp (`0.22.0`).


# 0.49.0 - March 2019

* ***(BREAKING)*** `background` is no longer a standalone image operation, which is not in a useful state anyway.
* ***(FEATURE)*** `extend` - New operation allows extending the image.
* ***(ENHANCEMENT)*** `resize.fit` - Resize now allows `fit` to be overridden.
* ***(ENHANCEMENT)*** `resize.position` - Resize now allows `position` to be overridden.
* ***(ENHANCEMENT)*** `resize.background` - Permits background to be applied to resize operation when applicable.
* ***(FIX)*** `+/-` on percentage dimensions is now working. Was only working on fixed (px) dimensions prior.
* ***(FIX)*** Various test fixes.


# 0.48.0 - October 2018

* ***(ENHANCEMENT)*** HTTP Agent - Utilize a more optimized HTTP(S) agent by default, including connection reuse.


# 0.47.0 - October 2018

* ***(ENHANCEMENT)*** Sharp - Upgrade to latest Sharp (`0.21.0`) for greater platform support.


# 0.46.0 - June 2018

* ***(ENHANCEMENT)*** Crop auto-focus - Greatly improved accuracy/consistency after being trained with hundreds of
  thousands of data points, which also allowed for the switch to a far more efficient (~10x) saliency mode (spectral).


# 0.45.0 - May 2018

* ***(CONFIGURATION)*** `router.supportWebP` - WebP may not be explicitly disabled, but remains enabled by default
  to avoid breakages. If performance is critical, disabling this option has been known to speed up image operations
  by 2 to 4 times.
* ***(FIX)*** Saliency - Minor fixes to enabling/disabling this feature.


# 0.44.0 - May 2018

* ***(FEATURE)*** `$info` command - Returns all known information about the image, including saliency (new) if available.
* ***(FEATURE)*** Crop auto-focus - An experimental new feature to permit saliency-based auto-focus. Exposed by crop anchor=`auto`.
* ***(FEATURE)*** `$saliency` command - An experimental new feature to permit retrieving of saliency meta data.
* ***(FEATURE)*** `$saliencyMap` command - An experimental new feature to permit retrieving of saliency map.
* ***(DEPENDENCIES)*** `salient-autofocus` - Required by the new saliency auto-focus feature. 


# 0.43.0 - March 2018

* ***(DEPENDENCIES)*** `sharp` - Updated to `v0.20` which requires `libvips` `v8.6.1` or later. 


# 0.42.0 - March 2018

* ***(CONFIGURATION)*** `storage.cacheArtifacts` - Caching of image artifacts may now be disabled. 


# 0.41.0 - March 2018

* ***(BREAKING)*** Default StorageOptions - Root of `storage` options may no longer include `StorageOptions` (options supplied to storage driver), and instead must supply to `storage.defaults` instead. This is a necessary change to avoid polluting the options supplied to storage drivers.
* ***(BREAKING)*** S3 Storage - Client moved to its own repo: https://github.com/asilvas/image-steam-s3
* ***(BREAKING)*** Node - Version 6 and later required.
* ***(PERFORMANCE)*** `storage.cacheTTS` & `storage.cacheOptimizedTTS` - Added to support "refreshing" of stale objects in cache to avoid needless reprocessing of images in caches with time-to-live set.
* ***(CONFIGURATION)*** `storage.cacheOptimized` - Added a new caching option to allow discrete `StorageOptions` supplied only for optimized original caching. This permits splitting of cache for sake of replication or eviction policies.
* ***(CONFIGURATION)*** `isDefaults` - Commandline argument `isDefaults` was added to allow merging of your own defaults.
* ***(GEO)*** `storage.replicas` - Tunable cache replication beyond what you'd get from storage-native replication settings. Allows for more flexible architectures that span multiple regions.
