# Welcome to ksu-susfs branch
This branch is for building in KernelSU-Next and susfs. KernelSU-Next is already added, no extra steps required. Susfs is a different story. Here's a guide:
Run these commands:
```
cd KernelSU-Next
curl -o 0001-Kernel-Implement-SUSFS-v1.5.3.patch https://github.com/sidex15/KernelSU-Next/commit/1e750de25930e875612bbec0410de0088474c00b.patch
patch -p1 < 0001-Kernel-Implement-SUSFS-v1.5.3.patch
```
After this, take a look into logs, not all patches have been applied due to conflicts. In "susfsksufolder" there are patched files which couldn't be patched using .patch file, using logs from previous command, figure out where to put these files.

After overriding previous files with new ones, you can build the kernel and susfs will be present.
# There is no KernelSU-Next
In some cases github cannot clone folder containing it. In this case, run this command:
```
curl -LSs "https://raw.githubusercontent.com/KernelSU-Next/KernelSU-Next/next/kernel/setup.sh" | bash -
```
# What even is this?
This is an attempt to resurrect ProtonPlus kernel for Samsung Galaxy A52 and A72.
## What is the point if there's original version?
It's dead, developer officially announced that he's discontinuing any support for it.
## Does this kernel support APatch?
[This commit](https://github.com/notfleshka/ProtonPlus-Resurrected/commit/e3932ea6d0e1aae3bfbf70faf4e0f6b4478d34a4) added experimental support for APatch, it is expected to encounter errors. Please keep in mind that it's **not recommended** to use APatch on Samsung kernels because it requires disabling Samsung kernel protection.
## Can I contribute?
Sure. You can open [pull requests](https://github.com/notfleshka/ProtonPlus-Resurrected/pulls) to merge your code(and most likely it will be merged, if it's useful and working) or report bugs on [Issues page](https://github.com/notfleshka/ProtonPlus-Resurrected/issues).
## Why do pre-releases have builds only for a72q?
I physically have only a72q, while being easy to port it to a52q, I don't want to publish something that most likely won't work. Usual releases will have builds for a52q.
## Why do I write non-sense in commits descriptions?
Because I can. Don't complain about it.
## Credits
Original ProtonPlus kernel: https://github.com/ProtonKernel/ProtonForA572Q

AnyKernel3: https://github.com/osm0sis/AnyKernel3

KernelSU Next: https://kernelsu-next.github.io/webpage/

Susfs4ksu: https://gitlab.com/simonpunk/susfs4ksu/-/tree/kernel-4.14

APatch: https://github.com/bmax121/APatch