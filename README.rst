===================================================================
pyproject2setuppy -- a cheap build for pyproject.toml-based systems
===================================================================

pyproject2setuppy is a tool to install ``pyproject.toml``-based packages
using plain setuptools_.  It maps the project metadata into ``setup()``
call arguments, making it possible to build them without installing
the dependency hell of the new build systems.


Supported features
------------------
Currently the following build systems are supported:

- flit_
- poetry_

Only minimal build/install functionality is supported.  Dependencies
and ``sdist``-related information are not propagated.

Scripts and entry points are not supported at the moment.  This is
subject to change in the future.


Dependencies
------------
The runtime (and build time, if using ``setup.py``) dependencies are:

- toml_ (to read ``pyproject.toml``)
- setuptools_ (to provide fully-featured ``setup.py`` commands)


Installation
------------
pyproject2setuppy is using a flit-compliant ``pyproject.toml``.
It includes ``setup.py`` that uses itself to maintain setuptools
compatibility.  Note that the latter does not install package's
dependencies.


Usage
-----
In order to use pyproject2setuppy to build a ``pyproject.toml``-based
project, either copy the included ``setup.py`` to the project's
directory or call the entry point directly, e.g.::

    $ python -m pyproject2setuppy.main build


Copyright
---------
pyproject2setuppy was written by Michał Górny.  It is distributed
under the terms of the 2-clause BSD license.  A copy of the license
is included in the ``COPYING`` file.


.. _setuptools: https://github.com/pypa/setuptools
.. _flit: https://flit.readthedocs.io
.. _poetry: https://python-poetry.org/