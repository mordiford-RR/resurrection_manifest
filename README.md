# resurrection_manifest for mordiford-RR

日本語でおｋ→ [README_ja.md](https://github.com/mordiford/resurrection_manifest/blob/marshmallow/README_ja.md)

## about

- This Resository is `platform_manifest` for Modified Resurrection Remix(mordiford-RR)
    - Reduce download size
    - Removed: too old hardwares (like `omap`), unused devices (like `android emulator`), unused toolchains
- Changed toolchain to [UBER ToolChain](https://bitbucket.org/UBERTC/) 4.9
    - If your device has `arm64` chipset, you have to [set `KERNEL_TOOLCHAIN`]((https://github.com/mordiford/android_device_oneplus_oneplus2/commit/a65779f962056c02be4b8cd397ffd3c4458f12a1)) on `BoardConfig.mk`.
- Removed these packages:
    - packages/
        - apps/
            - AudioFX
            - Browser
            - Calendar
            - Eleven
            - FMRadio
            - TvSettings
            - TvProvider
        - screensavers/
            - PhotoTables
            - WebView
        - wallpapers/
            - Galaxy4
            - HoloSpiral
            - NoiseField
            - PhaseBeam
    - note: build for `hammerhead`, you should remove LiveWallpaper components from `vendor` [like this](https://github.com/obsidians/proprietary_vendor_lge_hammerhead/commit/212c2b91f4964570f77add2737f5a4a5ba21a8cb)
    - I removed AOSP Browser, but Cyanogen Browser aka `gello` is still alive. If you want to use gello, add this to `device.mk`:

```
# Gello
PRODUCT_PACKAGES += \
   Gello
```

## How to use

- Read [https://github.com/ResurrectionRemix/platform_manifest#old-way-to-set-up-and-build-resurrection-remix](https://github.com/ResurrectionRemix/platform_manifest#old-way-to-set-up-and-build-resurrection-remix)

```
repo init -u https://github.com/mordiford/resurrection_manifest.git -b trusty
```

```
repo sync -j8 -c -f --force-sync --no-clone-bundle
```

## Author

### lindwurm

- web: [maud.io](https://maud.io)
- twitter: [@lindwurm](https://twitter.com/lindwurm)
- github: [@lindwurm](https://github.com/lindwurm)
    - org for android: [@mordiford](https://github.com/mordiford)
- xda: [@1indwurm](http://forum.xda-developers.com/member.php?u=6024671)
