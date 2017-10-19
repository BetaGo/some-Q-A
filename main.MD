* **Q**:
    vscode 的 jest 插件报错: jest watch Error， too many restart。

    * date: 2017-10-19  
    * system: ubuntu16.04  
    * vscode version: 1.17.2  

  **A**:
    Without using watchman, this can be fixed by increasing the number of inotify watches using

    `echo fs.inotify.max_user_watches=524288 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p`
  > 来源:  https://github.com/fbsamples/f8app/issues/55