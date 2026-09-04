---
title: "BASH SCRIPTING"
date: 2026-09-04
draft: false
categories: 
  - linux
  - scripting
tags: 
  - linux
  - bash
  - scripting
  - automation
---

## Introduction

Bash scripting can, in simple terms, be explained as the process of writing commands and programmatic logic into a script file (typically using the `.sh` extension), allowing commands that would normally be executed individually in a shell to be combined and automated. This can be useful for many simple and complex tasks, depending on the scope of the system.

## Syntax

A `.sh` script usually starts with one line of code, often referred to as a **shebang**. The shebang specifies which interpreter should be used to execute the script when it is run directly.

```sh
#!/bin/bash
```

In this case, it tells the system to use the Bash interpreter located at `/bin/bash`.

After this first line, we can start adding the desired commands.

```sh
#!/bin/bash

echo "Hi"

pwd
```

In order to add comments, like with many other programming languages, we can use the `#` symbol, and the interpreter will not consider that line as an instruction.

```sh
#!/bin/bash

# this is a comment

echo "Hi"

pwd
```

Bash scripts do not need to make use of semicolons, so a command followed by a newline might be enough to let the interpreter know that the command has ended, as the previous example demonstrates. However, it is also possible to use semicolons to separate multiple commands on the same line.

```sh
#!/bin/bash

echo "Hi"; pwd
```

{{< callout type="warning" text="This does not necessarily apply to all Bash constructs. As we will see further down, some constructs can span multiple lines." >}}

The previous examples show a script written with basic Linux commands, but Bash scripts benefit greatly from the ability to use variables, conditionals, loops, and many other concepts that are present in general-purpose programming languages.

In order to run our script, it's important to give appropriate permissions to the file.

```sh
chmod +x first-script.sh
```

Where `first-script.sh` is the name of your script file.

Then, we run the following command:

```sh
./first-script.sh
```

Or alternatively:

```sh
bash first-script.sh
```

Or also:

```sh
sh first-script.sh
```

This is confusing at first, so lets clarify it.

When we run a command using `./`, we are telling the system to execute the script, and the system will use the interpreter specified by the shebang, running the script in a new process. On the other hand, using `bash` or `sh` will tell our system to use that specific interpreter to run the script, regardless of which interpreter the shebang points to.

There is a final method:

```sh
source first-script.sh
```

The `source` command will run the script in the current shell environment rather than in a new process, so changes the script makes to variables, functions, aliases, and the working directory can affect your current shell session.

## Variables, Parameters and Arrays
