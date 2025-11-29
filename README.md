<div align="center">

<a href="https://github.com/bklynali/BKPatch/releases/latest"><img src="https://images.weserv.nl/?url=https://raw.githubusercontent.com/bklynali/BKPatch/refs/heads/main/ic.png&mask=circle" style="width: 128px;" alt="logo"></a>

<h1 align="center">BKPatch</h1>

[![GitHub License](https://img.shields.io/github/license/bmax121/APatch?logo=gnu)](/LICENSE)

</div>

The patching of Android kernel and Android system.

- A new kernel-based root solution for Android devices.
- APM: Support for modules similar to Magisk.
- KPM: Support for modules that allow you to inject any code into the kernel (Provides kernel function `inline-hook` and `syscall-table-hook`).
- BKPatch relies on [KernelPatch](https://github.com/bklynali/KernelPatch/).
- The BKPatch UI and the APModule source code have been derived and modified from [KernelSU](https://github.com/tiann/KernelSU).


## BKPatch Improvements

- Build in Zygisk

- kpm module to hide all paths

- Auto reset props, boot hash and other stuff to hide root


## Build in Zygisk support for modules

- For Tricky-Store, TEESimulator and TrickyAddonModule you do not need to add anything it will work without modifying the zip.

- Edit customize.sh and add the following line, this line must be add in order for it to work with build in zygisk.

- local BKPATCH\_ZYGISK\_ENABLED="/data/adb/.zygisk\_enabled"  


## The following code is optional

- Check if BKPatch Zygisk is enabled


  if [ -f "$BKPATCH_ZYGISK_ENABLED" ]; then
  local enabled_content
  enabled_content=$(cat "$BKPATCH_ZYGISK_ENABLED" 2>/dev/null | tr -d '[:space:]')
  if [ "$enabled_content" = "1" ]; then
  return 0
  fi
  fi

## Supported Versions

- Only supports the ARM64 architecture.
- Only supports Android kernel versions 3.18 - 6.12

Support for Samsung devices with security protection: Planned

## Requirement

Kernel configs:

- `CONFIG_KALLSYMS=y` and `CONFIG_KALLSYMS_ALL=y`

- `CONFIG_KALLSYMS=y` and `CONFIG_KALLSYMS_ALL=n`: Initial support

## Security Alert

The **SuperKey** has higher privileges than root access.  
Weak or compromised keys can lead to unauthorized control of your device.  
It is critical to use robust keys and safeguard them from exposure to maintain the security of your device.

## Get Help

- [Telegram](https://t.me/bklynrom/): Support


## Usage

For usage, please refer to [our official documentation](https://apatch.dev).  
It's worth noting that the documentation is currently not quite complete, and the content may change at any time.  

## Credits

- [KernelPatch](https://github.com/bmax121/KernelPatch/): The core.
- [APatch](https://github.com/bmax121/APatch/) The core.
- [YAPatch](https://github.com/Yervant7/YAPatch/) YAPatch
- [Magisk](https://github.com/topjohnwu/Magisk): magiskboot and magiskpolicy.
- [KernelSU](https://github.com/tiann/KernelSU): App UI, and Magisk module like support.

## License

BKPatch is licensed under the GNU General Public License v3 [GPL-3](http://www.gnu.org/copyleft/gpl.html).
