# AndKittyInjector

Shared library injector based on ptrace with help of [KittyMemoryEx](https://github.com/MJx0/KittyMemoryEx).

Requires C++11 or above.</br>
Inject from /data for Android

<h2> Support: </h2>

- [x] Tested on Android 5.0  ~ 13
- [x] ABI arm, arm64, x86, x86_64
- [x] Houdini support for emulators 32 & 64 bit
- [x] Inject emulated arm64 & arm32
- [x] Bypass android linker namespace restrictions
- [x] memfd dlopen support
- [x] App launch monitor

<h2> How to use: </h2>
Make sure to chmod +x or 755

```
Usage: ./path/to/AndKittyInjector [-h] [-pkg] [-pid] [-lib] [ options ]

Required arguments:
   -pkg                Target app package.
   
   -lib                Library path to inject.

Optional arguments:
   -h, --help          show available arguments.
   
   -pid                Target app pid.
   
   -dl_memfd           Use memfd_create & dlopen_ext to inject library, useful to bypass path restrictions.
   
   -watch              Monitor app launch by watching app's apk access then inject, useful if you want to inject as fast as possible.
   
   -delay              Set a delay in microseconds before injecting.
   ```
<h2>Notes: </h2>

- When using -watch to inject as soon as the target app launches, it is recomended to use -delay as well, especially for emulators.


- When using -dl_memfd and it fails then legacy dlopen will be called.


<h2>Credits: </h2>

[arminject](https://github.com/evilsocket/arminject)

[injectvm-binderjack](https://github.com/Chainfire/injectvm-binderjack)

[TinyInjector](https://github.com/shunix/TinyInjector)
