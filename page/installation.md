---
layout: default
title: Installation
nav_order: 3
permalink: /page/installation.html
summary: "This guide contains detailed step-by-step instructions for the installation of xtb software. Make sure to read it carefully."
---

# {{page.title}}
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}
---
## General Considerations

The xtb software is open-source and available under the LGPL 3.0 license on the GitHub platform. This guide provides a brief summary of the existing [guideline](https://xtb-docs.readthedocs.io/en/latest/setup.html). Some features are available only for the newer version of xtb (`=>6.6.1`) In case of any issues, you can always refer to the full documentation for further details.
Even though xtb is cross-platform, for simplicity and stability reasons, we assume a **Linux** distribution for the rest of the workshop.

{% include warning.html content="Primary operating system (OS) for the development and application of **xtb** is Linux. While it is possible to install **xtb** on Windows and macOS, support for these platforms may be more limited." %}


## Straighforward Installation
The most straightforward way of installing xtb is to download [precompiled binaries](https://github.com/grimme-lab/xtb/releases). One can also download vlled-edge version of the program subject to less testing.
After downloading the appropriate version, please extract, make it executable, and add to your `PATH` variable:

```bash
tar -xvf xtb*.tar.xz
chmod +x ./xtb-dist/bin/xtb
export PATH=$PWD/xtb-dist/bin:$PATH
```

Please also check if the executable is correctly linked via:

```bash
which xtb
```
and the corresponding version

```bash
xtb --version
```



## Compilation 
The more advanced way is to compile xtb from the codebase. 


## Utility Tools
In order to be able to v

