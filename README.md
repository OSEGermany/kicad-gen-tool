# KiCad output generation tool

<!--
SPDX-FileCopyrightText: 2021-2025 Robin Vobruba <hoijui.quaero@gmail.com>

SPDX-License-Identifier: CC0-1.0
-->

[![License: GPL-3.0-or-later](
    https://img.shields.io/badge/License-GPL_3-blue.svg)](
    https://www.gnu.org/licenses/gpl-3.0.html)
[![REUSE status](
    https://api.reuse.software/badge/github.com/osegermany/kicad-pcb-generate-doc-tool)](
    https://api.reuse.software/info/github.com/osegermany/kicad-pcb-generate-doc-tool)

status: **WIP**

This tool runs your output generation (Gerbder&Drill files, renders, ...)
on (potentially post-processed) sources.

See For example these tools for possible post-processing:

* [KiCad image/QRCode injector](https://github.com/hoijui/kicad-image-injector)
* [KiCad text injector](https://github.com/hoijui/kicad-text-injector)

## Dependencies

* BASH

## Misc

We very warmly recommend you to use
**the [KiBot](https://github.com/INTI-CMNB/KiBot) tool**
for the actual generation of the final output
from the post-processed KiCad sources.
It can generate much more then just Gerbers
and 2D renders of the PCBs.

## How it works

### Install Prerequisites

* BASH
* git

On a regular Debian based Linux,
you can install all of this with:

```bash
sudo apt-get install bash git
```

### Get the tool

In the repo of your project in which you want to use this tool,
which would be one that supports *\*.kicad_pcb* files,
you would do this to install this tool (in the project root dir):

```bash
mkdir -p doc-tools
git submodule add https://github.com/osegermany/kicad-pcb-generate-doc-tool.git doc-tools/kicad-gen-tool
```

> **NOTE**\
> There might be a tool to automate this in a more user friendly way,
> comparable to a package manager like `Oh-My-ZSH` or `apt`.

### Run

This will generate the PCB derived artifacts for all KiCad PCBs in the repo:

```bash
doc-tools/kicad-gen-tool/generate_output
```

Now, output can be found under the *build* directory.
