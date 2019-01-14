---
layout: single
title: "VSCode Extensions Madness" # title shown in home page
excerpt: "A little bit of my personal experience with [vscode](https://code.visualstudio.com/) extensions, how to install them via `cmd`, how to know what extensions are installed." # excerpt shown in home page under title
permalink: # global permalink is set in_config.yml
tags:
    - vscode
    - extension
    - install
    - cmd
published: true
comments: true
author_profile: true
---

The other day was looking at my [vscode] extensions and was thinking on how to get a list of my extensions, and when started doing my research and realized I was late to the party (everybody already doing this)

Coincidentally today [Kent C Dodds][kentcdodds-website] in his [DevTips with Kent][kentcdodds-devtips] today [video][youtube-workflow-tips-kentcdodds], at the beginning he explained how he does it

{% include video id="IHMkIdmvD9c" provider="youtube" %}

[here][kentcdodds-github-ama] is the reference to the code in the video. One thing to be noted is if you try to run that code on **windows** will get the following error:

```shell
    Quokka 'Untitled-1.js' (node: v11.6.0)​​​​
    ​​​​
    ​​write EPIPE​​
        at ​​​afterWriteDispatched​​​ ​internal/stream_base_commons.js:125​
        at ​​​writeGeneric​​​ ​internal/stream_base_commons.js:117​
        at ​​​Socket._writeGeneric​​​ ​net.js:720​
        at ​​​Socket._write​​​ ​net.js:732​
        at ​​​doWrite​​​ ​_stream_writable.js:415​``
        at ​​​writeOrBuffer​​​ ​_stream_writable.js:399​
        at ​​​Socket.Writable.write​​​ ​_stream_writable.js:299​
        at ​​​Object.<anonymous>​​​ ​quokka.js:14:0​
    ​​​​
    ​​spawn pbcopy ENOENT​​
        at ​​​Process.ChildProcess._handle.onexit​​​ ​internal/child_process.js:246​
        at ​​​onErrorNT​​​ ​internal/child_process.js:421​
        at ​​​process.internalTickCallback​​​ ​internal/process/next_tick.js:72​
    ​​​​
    ​​<Buffer >
```

and it is because this `pbcopy` parameter in the `const proc = spawn('pbcopy')` line only works for **MAC OS**, just change it to `clip` if you are in **Windows** and problem solved.

That generates and unordered list with the direct link of each extension, great for documentation.

But maybe you need a little bit more than just documentation, maybe something like a file with some instructions to run it in another pc or share it with some friend and there a command line script could help. Of course [vscode] allows extension management via UI but also have  [command line][vscode-extension-cli] options to do that, and that could be handy if you want to install [vscode] via maybe `cmd` or `poweshell`, even via [chocolatey]
Found this script after a quick search on [google](www.google.com) and want to share it
<script src="https://gist.github.com/ddieppa/d1cce687081b726815f3404bd39e7be2.js"></script>

This is a **linux** command, so if you are in **windows** you can use [wsl]. This was the result in my case:

<script src="https://gist.github.com/ddieppa/1c531293b1bae22873baea494e60ee60.js"></script>

[youtube-workflow-tips-kentcdodds]: https://www.youtube.com/watch?v=IHMkIdmvD9c&t=859s
[vscode]: https://code.visualstudio.com/
[kentcdodds-github-ama]:https://github.com/kentcdodds/ama/issues/406
[kentcdodds-website]: https://kentcdodds.com/
[kentcdodds-youtube]: https://www.youtube.com/channel/UCz-BYvuntVRt_VpfR6FKXJw
[kentcdodds-devtips]: https://www.youtube.com/playlist?list=PLV5CVI1eNcJgCrPH_e6d57KRUTiDZgs0u
[vscode-extension-cli]: https://code.visualstudio.com/docs/editor/extension-gallery#_command-line-extension-management
[chocolatey]: https://www.chocolatey.org/
[wsl]: https://docs.microsoft.com/en-us/windows/wsl/about