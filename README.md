# hbctool 

[![Python 3.x](https://img.shields.io/badge/python-3.x-yellow.svg)](https://python.org) [![PyPI version](https://badge.fury.io/py/hbctool.svg)](https://badge.fury.io/py/hbctool) [![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg)](/LICENSE)

A command-line interface for disassembling and assembling the Hermes Bytecode. 

Since the React Native team created their own JavaScript engine (named Hermes) for running the React Native application, the JavaScript source code is often compiled to the Hermes bytecode. In the penetration test project, I found that some React Native applications have already been migrated to the Hermes engine. It is really head for me to analyze or patch those applications. Therefore, I created hbctool for helping any pentester to test the Hermes bytecode.

> [Hermes](https://hermesengine.dev/) is an open-source JavaScript engine optimized for running React Native apps on Android. For many apps, enabling Hermes will result in improved start-up time, decreased memory usage, and smaller app size. At this time Hermes is an opt-in React Native feature, and this guide explains how to enable it.

Special thanks to [ErbaZZ](https://github.com/ErbaZZ) and [Jusmistic](https://github.com/Jusmistic) for helping me research and develop this tool.

## Screenshot

![hbctool Example](/image/hbctool_example.gif)

This video with MP4 format can be found at [/image/hbctool_example.mp4](/image/hbctool_example.mp4).

## Installation

To install hbctool, simply use pip:

```
pip install hbctool
```

## Usage

Please execute `hbctool --help` for showing the usage.

```
hbctool --help   
A command-line interface for disassembling and assembling
the Hermes Bytecode.

Usage:
    hbctool disasm <HBC_FILE> <HASM_PATH>
    hbctool asm <HASM_PATH> <HBC_FILE>
    hbctool --help
    hbctool --version

Operation:
    disasm              Disassemble Hermes Bytecode
    asm                 Assemble Hermes Bytecode

Args:
    HBC_FILE            Target HBC file
    HASM_PATH           Target HASM directory path

Options:
    --version           Show hbctool version
    --help              Show hbctool help manual

Examples:
    hbctool disasm index.android.bundle test_hasm
    hbctool asm test_hasm index.android.bundle
```

> For Android, the HBC file normally locates at `assets` directory with `index.android.bundle` filename.

## Contribution

Feel free to create an issue or submit the merge request. Anyway you want to contribute this project. I'm very happy about it.

However, please run the unittest before submit the pull request.

```
cd hbctool
python test.py
```

I use poetry to build this tool, For building tool, simply execute:

```
poetry install
```

## Next Step

- Add the other Hermes bytecode versions
- Create a class abstraction
- Support overflow patching
- Do all TODO, NOTE, FIXME in source code