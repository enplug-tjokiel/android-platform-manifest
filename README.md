# manifest-s905x

==========
HowTo Sync:
==========

First install git LFS with `--force` mode which will fetch large files during sync:
```
git lfs install --force
```
https://git-lfs.github.com/

Syncing this release requires git and the repo tool from Google:
http://source.android.com/source/downloading.html#installing-repo

```
mkdir s905x-android
cd s905x-android
repo init -u git@github.com:spectrio/android-platform-manifest.git -b main-s905x -m spectrio.xml --depth=1
repo sync -j5 -c
repo forall -c git lfs pull
```

==========
HowTo Build:
==========

Building this release requires a Linux build environment configured to
build Android: http://source.android.com/source/initializing.html

```
cd s905x-android
. build/envsetup.sh
lunch p212-userdebug-64
make otapackage -j8
```
