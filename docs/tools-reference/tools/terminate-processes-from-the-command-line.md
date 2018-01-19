---
author:
  name: Sam Foo
  email: docs@linode.com
description: Learn how to find a running process and terminate it from the command line.
keywords: ["kill", "terminate", "PID", "command line"]
license: '[CC BY-ND 4.0](https://creativecommons.org/licenses/by-nd/4.0)'
modified: 2018-01-16
modified_by:
  name: Sam Foo
published: 2018-01-16
title: Terminate Processes From the Command Line
---


While there are graphical utilities such as Activity Monitor on Mac OS or Task Manager on Windows, such programs exchange control over processes in exchange for convenience. The command line offers many options for closing a process. This guide will explore some of the different ways to locate and terminate a process from the command line..

### Find Process ID

A common pattern for ending a process is though the process ID (PID). There are a variety of ways to find out the PID.

If the process name is known, `pgrep` will search currently running processes for the name.

    pgrep firefox

{{< note >}}
`pgrep` is not installed by default on MacOS. This can be installed along with `pkill` and `pfind` with Homebrew via:

    brew install proctools

{{< /note >}}

Another way to list running processes for all users is through `ps aux`. The output can be piped to grep in order to search for a process.

    ps aux | grep firefox

### Terminate the Process

Once the PID is found, send the kill signal by:

    kill [PID]

There maybe cases where there are multiple instances of the same program running or processes being continuously spawned. In such cases, `killall` is an option.

    killall [process name]

For a more indepth discussion about `kill` and `killall`, see [our guide on how to use kill and killall to stop processes.](/docs/tools-reference/tools/use-killall-and-kill-to-stop-processes/)

<!-- Windows instructions via taskkill someday -->