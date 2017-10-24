* **Q**:
    android studio 启动 `emulator -avd` 报错 `libGL error: unable to load driver: i965_dri.so`

    * date: 2017-10-24  
    * system: ubuntu17.10

  **A**:
    指令后面加入 `-use-system-libs`。
    例如：
    `emulator -avd Nexus_5X_API_23 -use-system-libs`
    其他解决方案参见来源。
  >来源： https://bbs.archlinux.org/viewtopic.php?id=213192
  ---

* **Q**:
    从源码构建 watchman 报错 make fatal error: openssl/sha.h: No such file or directory

    * date: 2017-10-24  
    * system: ubuntu17.10

  **A**:
    `sudo apt install libssl-dev`

  >来源： https://github.com/facebook/watchman/issues/529
---

* **Q**:
    android studio 报错 `"Unable to run mksdcard SDK tool"`

    * date: 2017-10-23  
    * system: ubuntu17.10  
    * android studio version: 2.3.3

  **A**:
      To fixed it, add 32 bit architecture with the command:

      $ sudo dpkg --add-architecture i386
      $ sudo apt-get update
      $ sudo apt-get install libc6:i386 libncurses5:i386 libstdc++6:i386 lib32z1 libbz2-1.0:i386

  > 来源： http://android-er.blogspot.com/2017/05/fix-unable-to-run-mksdcard-sdk-tool.html
---

* **Q**:
    vscode 的 jest 插件报错: `jest watch Error， too many restart`。

    * date: 2017-10-19  
    * system: ubuntu16.04  
    * vscode version: 1.17.2  

  **A**:
    Without using watchman, this can be fixed by increasing the number of inotify watches using

    `echo fs.inotify.max_user_watches=524288 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p`
  > 来源:  https://github.com/fbsamples/f8app/issues/55
---
