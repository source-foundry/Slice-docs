---
title: "Developer"
weight: 6
---

- [Slice source code contributions](#slice-source-code-contributions)
  - [Requirements](#requirements)
  - [Development Environment Setup by Platform](#development-environment-setup-by-platform)
    - [macOS and Linux](#macos-and-linux)
    - [Windows](#windows)
  - [Compile App Distributions by Platform](#compile-app-distributions-by-platform)
    - [Linux](#linux)
    - [macOS](#macos)
    - [Windows](#windows-1)
- [Slice documentation contributions](#slice-documentation-contributions)
  - [Requirements](#requirements-1)
  - [Review local edits](#review-local-edits)

Source contributions are welcome!  Use the GitHub pull request workflow to submit a change proposal.

These docs describe how to get involved in the development of the Slice project.

{{< tip >}}
Are you looking for a way to report issues?  Check out the [Issues docs](issues)!
{{< /tip >}}

## Slice source code contributions

The [Slice application source repository](https://github.com/source-foundry/Slice) is hosted on GitHub.

### Requirements

- Python 3.6+ interpreter
- Build dependencies defined in our `dev-requirements.txt` file installed in a Python virtual environment

### Development Environment Setup by Platform

The following instructions define how to build a Python virtual environment, install the appropriate Python dependencies, and launch the application to test your source edits.

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

Add tests for your new source and run the test pytest- and tox-based test suite with:

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

Add tests for your new source and run the pytest- and tox-based test suite with:

```shell
tox
```

### Compile App Distributions by Platform

The following instructions demonstrate how to compile single file PyInstaller builds for platform-specific distribution.  

{{< tip "warning" >}}
Please note that there are undocumented app code signing / notarization steps.  These steps are not required for local development builds.  Your application package is likely to be *different* than an application package compiled at a given commit for release in this project but the approach to launch the application and the function of the source do not differ.  Please reach out on the repository if you are building a derivative with the intent to distribute to others and need more information about release preparation.
{{< /tip >}}

#### Linux

We do not currently provide application package distributions for Linux distros.

#### macOS

Set up your macOS development environment as described in the section above, activate your Python virtual environment, and build the `Slice.app` package bundle with the following command from the root of the source repository:

```shell
make build-macos
```

Slice.app is found on the path `dist/Slice.app`.

#### Windows

The following instructions work on Win 10.

Set up your Windows development environment as described in the section above, activate your Python virtual environment, and build the `Slice.exe` application executable with the following command from the root of the source repository:

```shell
pyinstaller --noconfirm .\target\PyInstaller-Windows\Slice-Windows.spec
```

<span style="margin-top: 30px"> </span>

## Slice documentation contributions

The [Slice documentation source repository](https://github.com/source-foundry/Slice-docs) is hosted on GitHub.  

The Slice documentation is authored in Markdown files and automatically compiled to production HTML docs when the Markdown sources are merged to the main branch of the documentation repository.  The Markdown files are located in the [`content` directory of the repository](https://github.com/source-foundry/Slice-docs/tree/main/content) and follow the URL directory/file path structure that you see on the documentation site.

{{< tip "warning" >}}
Please do not commit or push updated HTML, CS, or JS files with your pull request!  You should only submit Markdown file changes if you are editing site content.
{{< /tip >}}

### Requirements

- [Go compiler](https://golang.org/dl/)
- [hugo](https://gohugo.io/) static site generator package

Install the Go compiler and hugo package on your system to test local changes before pushing a pull request.

### Review local edits

Edit the Markdown files locally and examine your edits by running the following command from the root of the documentation repository:

```shell
hugo serve
```

hugo compiles the static website and runs a local web server so that you can view changes.  View your local edits by opening `http://localhost:1313/` in your web browser.  The site will automatically update each iteration of revisions if you allow the `hugo serve` command to run while editing and saving content in the Markdown files.
