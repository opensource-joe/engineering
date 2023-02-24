# Python Virtual Environments: A Primer

Notes for the written tutorial

[Written tutorial](https://realpython.com/python-virtual-environments-a-primer/)
[Video tutorial](https://realpython.com/courses/working-python-virtual-environments/)
[venv project](https://virtualenv.pypa.io/en/latest/)

## Working with Python Virtual Environment

- mkdir [name] - create a folder in directory where you want virtual env
- python3 -m venv venv - create the environment within the newly created mkdir folder
- source venv/bin/activate - activate the env created in previous step
- python -m pip install <package-name> - install packages to the env
- Because you first created and activated the virtual environment, pip will install the packages in an isolated location.
- Once you’re done working with this virtual environment, you can deactivate it.
- deactivate - command will deactivate python env

- rm -r [folder_name]
- python3 -m venv [fancy_name] - to create new folder w/ custom name for venv
- source [fancy_name]/bin/activate - to activate venv in custom folder
- deactivate the custom folder/venv

## Need for Virtual Environment

- Nearly everyone in the Python community suggests that you use virtual environments for all your projects.
- The short answer is that Python isn’t great at dependency management.
- If you install packages to your operating system’s global Python, these packages will mix with the system-relevant packages. This mix-up could have unexpected side effects on tasks crucial to your operating system’s normal behavior.
- Additionally, if you update your operating system, then the packages you installed might get overwritten and lost.
- One of your projects might require a different version of an external library than another one. If you have only one place to install packages, then you can’t work with two different versions of the same library. This is one of the most common reasons for the recommendation to use a Python virtual environment.
- Corporate lockout - If you use virtual environments, then you create a new installation location within the scope of your user privileges, which allows you to install and work with external packages.

## The Python Virtual Environment

- The short answer is that a Python virtual environment is a folder structure that gives you everything you need to run a lightweight yet isolated Python environment.
- When you create a new virtual environment using the venv module, Python creates a self-contained folder structure and copies or symlinks the Python executable files into that folder structure.
- Python virtual environments aim to provide a lightweight, isolated Python environment that you can quickly create and then discard when you don’t need it anymore.
- You want to achieve an isolated environment so that any external packages you install won’t conflict with global site-packages. What venv does to make this possible is to reproduce the folder structure that a standard Python installation creates.


## Virtual Environment Works

- When you create a virtual environment using venv, the module re-creates the file and folder structure of a standard Python installation on your operating system. Python also copies or symlinks into that folder structure the Python executable with which you’ve called venv.
- With the standard folder structure in place, the Python interpreter in your virtual environment can understand where all relevant files are located. It does this with only minor adaptations to its prefix-finding process according to the venv specification.
- Python virtual environments aim to be a lightweight way to provide you with an isolated Python environment that you can quickly create and then delete when you don’t need it anymore. To make this possible, venv copies only the minimally necessary files.
- To assure that the scripts you want to run use the Python interpreter within your virtual environment, venv modifies the PYTHONPATH environment variable that you can access using sys.path.