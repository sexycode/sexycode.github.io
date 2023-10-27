---
title : "Android Source Version check"
#excerpt : ""

categories:
   - Blog
tags:
   - Blog
---


- android version check   
   1. 12/maincore/build/core/version_defaults.mk
     PLATFORM_SDK_VERSION := 31  , PLATFORM_VERSION_LAST_STABLE := 12
   2. 13/maincore/build/core/version_defaults.mk
```
# This is the user-visible version.  In a final release build it should
# be empty to use PLATFORM_VERSION as the user-visible version.  For
# a preview release it can be set to a user-friendly value like `12 Preview 1`
PLATFORM_DISPLAY_VERSION := 13

ifndef PLATFORM_SDK_VERSION
  # This is the canonical definition of the SDK version, which defines
  # the set of APIs and functionality available in the platform.  It
  # is a single integer that increases monotonically as updates to
  # the SDK are released.  It should only be incremented when the APIs for
  # the new release are frozen (so that developers don't write apps against
  # intermediate builds).  During development, this number remains at the
  # SDK version the branch is based on and PLATFORM_VERSION_CODENAME holds
  # the code-name of the new development work.

  # When you increment the PLATFORM_SDK_VERSION please ensure you also
  # clear out the following text file of all older PLATFORM_VERSION's:
  # cts/tests/tests/os/assets/platform_versions.txt
  PLATFORM_SDK_VERSION := 33
endif
```
- aosp 최신버전
```
shkim@shkim-desktop(1254433.aosp:0):~/work/aosp/.repo/manifests$ pwd
/home/shkim/work/aosp/.repo/manifests
shkim@shkim-desktop(1254433.aosp:0):~/work/aosp/.repo/manifests$ git branch -v
* default 695764ec1 Merge Android 14.
```

```
PLATFORM_VERSION_LAST_STABLE := 14
.KATI_READONLY := PLATFORM_VERSION_LAST_STABLE

# These are the current development codenames, if the build is not a final
# release build.  If this is a final release build, it is simply "REL".
# Note that this may be overridden by RELEASE_VERSION_CODENAME_REL in
# version_util.mk.
PLATFORM_VERSION_CODENAME.UP1A := UpsideDownCake
PLATFORM_VERSION_CODENAME.VP1A := VanillaIceCream

# This is the user-visible version.  In a final release build it should
# be empty to use PLATFORM_VERSION as the user-visible version.  For
# a preview release it can be set to a user-friendly value like `12 Preview 1`
PLATFORM_DISPLAY_VERSION :=

ifndef PLATFORM_SDK_VERSION
  # This is the canonical definition of the SDK version, which defines
  # the set of APIs and functionality available in the platform.  It
  # is a single integer that increases monotonically as updates to
  # the SDK are released.  It should only be incremented when the APIs for
  # the new release are frozen (so that developers don't write apps against
  # intermediate builds).  During development, this number remains at the
  # SDK version the branch is based on and PLATFORM_VERSION_CODENAME holds
  # the code-name of the new development work.

  # When you increment the PLATFORM_SDK_VERSION please ensure you also
  # clear out the following text file of all older PLATFORM_VERSION's:
  # cts/tests/tests/os/assets/platform_versions.txt
  PLATFORM_SDK_VERSION := 34
endif
```
