.. _installation:

Installation
============

Prerequisites
-------------

* Traditionally, xlwings requires an **installation of Excel** and therefore only works on **Windows** and **macOS**. Note that macOS currently does not support UDFs.
* Since v0.26.0, xlwings can be installed on Linux servers in connection with Google Sheets or Excel on the web, see :ref:`Remote Interpreter <remote_interpreter>`.
* xlwings requires at least Python 3.7.

Here are previous versions of xlwings that support older versions of Python:

* Python 3.6: 0.25.3
* Python 3.5: 0.19.5
* Python 2.7: 0.16.6

Installation
------------

xlwings comes pre-installed with

* `Anaconda <https://www.anaconda.com/products/individual>`_ (Windows and macOS)
* `WinPython <https://winpython.github.io>`_ (Windows only) Make sure **not** to take the ``dot`` version as this only contains Python.

If you are new to Python or have trouble installing xlwings, one of these distributions is highly recommended. Otherwise, you can also install it with pip::

    pip install xlwings

or conda::

    conda install xlwings

Note that the official conda package might be a few releases behind. You can, however,
use the ``conda-forge`` channel (replace ``install`` with ``upgrade`` if xlwings is already installed)::

  conda install -c conda-forge xlwings

Add-in
------

To install the add-in, run the following command::

    xlwings addin install

To call Excel from Python, you don't need an add-in. Also, you can use a single file VBA module (*standalone workbook*) instead of the add-in. For more details, see :ref:`xlwings_addin`.

.. note::
   The add-in needs to be the same version as the Python package. Make sure to re-install the add-in after upgrading the xlwings package. Make sure to close Ecxel before installing/upgrading the add-in.

.. note::
  When you are on macOS and are using the VBA standalone module instead of the add-in, you need to run ``$ xlwings runpython install`` once.

Dependencies
------------

* **Windows**: ``pywin32``

* **Mac**: ``psutil``, ``appscript``

The dependencies are automatically installed via ``conda`` or ``pip``.
If you would like to install xlwings without dependencies, you can run ``pip install xlwings --no-deps`` or set the environment variable ``XLWINGS_NO_DEPS=1`` before running ``pip install xlwings``.

How to activate xlwings PRO
---------------------------

See :ref:`xlwings PRO <pro>`.

Optional Dependencies
---------------------

* NumPy
* pandas
* Matplotlib
* Pillow
* cryptography (for xlwings.pro)
* Jinja2 (for xlwings.pro.reports)
* requests (for permissioning)

These packages are not required but highly recommended as they play very nicely with xlwings. They are all pre-installed with Anaconda. With pip, you can install xlwings with all optional dependencies as follows::

    pip install "xlwings[all]"

Update
------

To update to the latest xlwings version, run the following in a command prompt::

    pip install --upgrade xlwings

or::

    conda update -c conda-forge xlwings

Make sure to keep your version of the Excel add-in in sync with your Python package by running the following (make sure to close Excel first)::

    xlwings addin install

Uninstall
---------

To uninstall xlwings completely, first uninstall the add-in, then uninstall the xlwings package using the same method (pip or conda) that you used for installing it::

    xlwings addin remove

Then ::

    pip uninstall xlwings

or::

    conda remove xlwings

Finally, manually remove the ``.xlwings`` directory in your home folder if it exists.