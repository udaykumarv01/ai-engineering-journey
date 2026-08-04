Python Environments, Packages, Interactive Python & Jupyter — Beginner Notes

1. What is a Python Environment?

A Python environment is a setup where Python and its required packages are available for a project.

Different projects may require different versions of Python packages. To avoid conflicts, we can create a separate environment for each project.

Simple example

Suppose:

Project A → needs requests version 2.28
Project B → needs requests version 2.32

If both use the same global Python environment, they may cause conflicts.

Instead:

Project A → Environment A → its own packages
Project B → Environment B → its own packages

So:

«Python environment = Separate workspace for a Python project.»

---

2. Virtual Environment ("venv")

Python has a built-in tool called venv for creating virtual environments.

Create one:

python -m venv venv

This creates:

project/
│
├── venv/
├── app.py
└── ...

The "venv" folder contains the separate environment.

Activate on Windows

venv\Scripts\activate

After activation, you may see:

(venv) C:\MyProject>

Now packages installed using "pip" belong to this environment.

Deactivate

deactivate

Why use "venv"?

- Keeps projects separate
- Prevents package conflicts
- Makes projects easier to manage
- Useful for web development and normal Python projects

---

3. What is a Python Package?

A package is reusable Python code created to provide useful functionality.

Instead of writing everything yourself, you can install packages.

Examples:

requests → HTTP requests
numpy → Numerical calculations
pandas → Data analysis
matplotlib → Graphs
fastapi → Building APIs

For example:

import requests

Here, "requests" is an external package.

---

4. What is pip?

pip is Python's package installer.

It is used to install and manage Python packages.

Install a package

pip install requests

Install multiple packages

pip install numpy pandas matplotlib

Check installed packages

pip list

Show information about a package

pip show requests

Uninstall a package

pip uninstall requests

Upgrade a package

pip install --upgrade requests

Important

If you have activated a virtual environment:

venv\Scripts\activate

then:

pip install requests

installs the package inside that environment.

---

5. "requirements.txt"

A Python project can have many packages.

Instead of telling someone to install them one by one, we can create:

requirements.txt

Example:

requests
numpy
pandas
fastapi

Install everything with:

pip install -r requirements.txt

This is very useful when uploading projects to GitHub.

---

6. What is Conda?

Conda is another tool for managing:

- Python environments
- Packages
- Dependencies

It can create separate environments just like "venv".

Example:

conda create --name myproject python=3.12

Activate:

conda activate myproject

Deactivate:

conda deactivate

"venv" vs Conda

venv
↓
Mainly creates Python virtual environments

Conda
↓
Creates environments + manages packages and dependencies

For normal Python/web development, "venv" is often enough.

For data science and scientific computing, Conda can be very useful.

---

7. What is Anaconda?

Anaconda is a Python distribution mainly designed for:

- Data Science
- Machine Learning
- Scientific Computing
- Data Analysis

It comes with many commonly used packages and tools.

For example, Anaconda commonly works with tools such as:

Python
Jupyter
NumPy
Pandas
Matplotlib

Conda vs Anaconda

These are related but not exactly the same.

Conda:

«Environment and package management tool.»

Anaconda:

«A large Python/data-science distribution that includes Conda and many packages/tools.»

---

8. Interactive Python

Normally, you may write a complete Python file:

a = 10
b = 20
print(a + b)

and then run the file.

Interactive Python allows you to execute Python one instruction at a time and immediately see the result.

Example:

>>> a = 10
>>> b = 20
>>> a + b
30

The ">>>" means Python is waiting for your next command.

So:

«Interactive Python = Give Python a command →
