---
title: "Developer"
weight: 6
---

- [Slice source code contributions](#slice-source-code-contributions)
  - [Requirements](#requirements)
  - [Development Environment Setup by Platform](#development-environment-setup-by-platform)
    - [macOS and Linux](#macos-and-linux)
    - [Windows](#windows)
- [Slice documentation contributions](#slice-documentation-contributions)

Source contributions are welcomed!  

These docs describe how to get involved in the development of the Slice project.

{{< tip >}}
Looking for information on how to report an issue?  Check out the [Issues docs](issues)!
{{< /tip >}}



## Slice source code contributions

The [Slice application source repository](https://github.com/source-foundry/Slice) is hosted on GitHub.

### Requirements

- Python 3.6+ interpreter
- Build dependencies defined in our `dev-requirements.txt` file installed in a Python virtual environment

### Development Environment Setup by Platform

The following instructions define how to build a Python virtual environment, install the appropriate Python dependencies, and launch the application so that you can test your source edits.

#### macOS and Linux

Clone the repository with:

```shell
git clone https://github.com/source-foundry/Slice.git
```

Create a Python 3.6+ virtual environment with:

```shell
cd Slice
python3 -m venv .venv
```

Install the required build dependencies with:

```shell
source .venv/bin/activate
pip install -r dev-requirements.txt
```

Make edits to the project source files locally and test your changes by launching the application with:

```shell
make run
```

Add tests for your new source run the test pytest- and tox-based test suite with:

```shell
tox
```

#### Windows

The following instructions are validated in Powershell 7 on Windows 10.

Clone the repository with:

```shell
git clone https://github.com/source-foundry/Slice.git
```

Create a Python 3.6+ virtual environment with:

```shell
cd Slice
python3 -m venv venv
```

Install the required build dependencies with:

```shell
.\venv\Scripts\activate
pip install -r dev-requirements.txt
```

Make edits to the project source files locally and test your changes by launching the application with:

```shell
python src\run.py
```

Add tests for your new source run the test pytest- and tox-based test suite with:

```shell
tox
```

## Slice documentation contributions

The [Slice documentation source repository](https://github.com/source-foundry/Slice-docs) is hosted on GitHub.