# resurrection_manifest for mordiford-RR

以下はmordiford-RRをビルドする人向け。ROMを使いたいだけのひとは [resurrection_manifest/wiki](https://github.com/mordiford/resurrection_manifest/wiki) へ。

## これなん

- 個人的にもはや不要であると判断されたリポジトリを根こそぎ削ったResurrection Remix向けmanifestです
    - 転送量の削減に貢献します
    - 具体的には古い `omap` 向けのハードウェア周り、android emulator等の関係ないdevice、 Linux-x86 以外のホスト向けのToolchain群が無慈悲にコメントアウトされました
- Toolchainを[UBERTC](https://bitbucket.org/UBERTC/)に変更しています
    - `arm64`の場合は `BoardConfig.mk` で `KERNEL_TOOLCHAIN` を[適切に指定](https://github.com/mordiford/android_device_oneplus_oneplus2/commit/a65779f962056c02be4b8cd397ffd3c4458f12a1)しないと確実にビルドがコケるので注意してください
- 独断で必要無さそうな以下のパッケージを削りました
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
    - 手元で `hammerhead` 向けにビルドしようとしたらライブ壁紙周りでコケるので[適当に削ってください](https://github.com/obsidians/proprietary_vendor_lge_hammerhead/commit/212c2b91f4964570f77add2737f5a4a5ba21a8cb)
    - ブラウザ排除してますがCyanogen Browserこと `gello` は残してるので良さげなブラウザが最初から欲しい人はデバイスツリー側で `device.mk` にいい感じに以下追加してください

```
# Gello
PRODUCT_PACKAGES += \
   Gello
```

## 使い方

[Resurrection Remix のビルド方法 - dev:mordiford](http://dev.maud.io/entry/2016/03/18/how-to-build-rr) で `2-b-3` を適当に `mordiford` に読み替えてください。

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
