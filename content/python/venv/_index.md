+++
title = "Virtual Environment"
date = 2020-06-06T18:47:11+02:00
weight = 10
+++

Virtual environments, or **venv**, create a containerized environment of running your Python applications. You install all the Python packages you use for a specific program in one virtual environment.

## System Installation

When you simply run `python --version` in your terminal, you get the version that is installed on your computer. That is mostly likely sourced from your `/usr/local/bin` directory.

Check where `pip3` is sourced from and check which version are you running.

```bash
which pip3
pip3 --version
```

List installed packages on your system.

```bash
pip3 list
```

Create virtual environment with the name of `<venv_name>` in your current directory.

```bash
python3 -m venv <venv_name>
```

Activate that virtual environment.

```bash
source <venv_name>/bin/activate
```

Print on the screen a list of installed in a specific format for import and export.

```bash
pip freeze
```

Create `requirements.txt`.

```bash
pip freeze > requirements.txt
```

Deactivate virtual environment and delete it.

```bash
deactivate
rm -rf <venv_name>
```

Install packages into virtual environment from `requirements.txt`.

```bash
pip install -r requirements.txt
```

