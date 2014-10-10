Aospa
================

Local Manifest to build AOSPA ROM for the Huawei Y300

Build Instructions for AOSPA Y300 (U8833)
-----------------------------------------------------------------------------

1. Initialize repo using the following commands

```bash
mkdir ~/bin
PATH=~/bin:$PATH
curl http://commondatastorage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
chmod a+x ~/bin/repo
mkdir liquid
cd liquid
repo init -u https://android.googlesource.com/platform/manifest
repo init -u git://github.com/AOSPA-legacy/manifest.git -b kitkat
mkdir .repo/local_manifests
```

2. Add my local manifest

```bash
curl https://raw.githubusercontent.com/AospaKKY300/android/master/u8833.xml > .repo/local_manifests/roomservice.xml
```

3. Download sources
```bash
repo sync -f -j8 && repo sync -f -j8
```

4. Build AOSPA for Y300

```bash
./rom_build.sh u8833 false
```
