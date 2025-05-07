<img src="https://github.com/ArrowOS/getting_started/blob/master/misc/logo.png?raw=true">

# ArrowOS

 Getting Started
---------------
To get started with the ArrowOS sources, you'll need to get
familiar with [Git and Repo](https://source.android.com/setup/build/downloading).

To initialize your local repository, use command:

```bash
repo init -u https://github.com/ArrowOS-Ext/android_manifest.git -b arrow-13.3
```

Use this if you want to save storage

```bash
repo init --depth=1 -u https://github.com/ArrowOS-Ext/android_manifest.git -b arrow-13.3
```
Then sync up:

```bash
repo sync
```

Use this for save storage

```bash
repo sync -c --force-sync --optimized-fetch --no-tags --no-clone-bundle --prune --retry-fetches=5 -j$(nproc --all)
```

Building the System
-------------------
 Initialize the ROM environment with the envsetup.sh script.

```bash
. build/envsetup.sh
```

Lunch your device after cloning all device sources if needed.

```bash
lunch arrow_<devicecodename>-<buildtype>
```

Start compilation

```bash
m otapackage -j$(nproc --all)
```

OR

```bash
m bacon -j$(nproc --all)
```

Setup flags
---------------------------------------------------------------------------------------------------------------------
```
# ArrowOS Flags
TARGET_FACE_UNLOCK_SUPPORTED := true # For supported face unlock
TARGET_SUPPORTS_BLUR := true # disable/enable blur support, default is false
TARGET_SUPPORTS_QUICK_TAP := true # Quick Tap support
TARGET_BOOT_ANIMATION_RES := 1080 # Set resolution for Boot Animation
ARROW_MAINTAINER := your_name # Set maintainer name (Don't use special characters or space)
TARGET_SUPPORT_BYPASS_CHARGE := true # Enable BypassCharge support by QS Tile, disable by default (Need kernel and sepolicy implementations)
```
---------------------------------------------------------------------------------------------------------------------
