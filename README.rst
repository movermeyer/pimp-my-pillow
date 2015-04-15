===============================
Pimp My Pillow
===============================

| |docs| 
| |version| |downloads| |wheel| |supported-versions| 

.. |docs| image:: https://readthedocs.org/projects/pimp-my-pillow/badge/?style=flat
    :target: https://readthedocs.org/projects/pimp-my-pillow
    :alt: Documentation Status

.. |version| image:: http://img.shields.io/pypi/v/pmp.png?style=flat
    :alt: PyPI Package latest release
    :target: https://pypi.python.org/pypi/pmp

.. |downloads| image:: http://img.shields.io/pypi/dm/pmp.png?style=flat
    :alt: PyPI Package monthly downloads
    :target: https://pypi.python.org/pypi/pmp

.. |wheel| image:: https://pypip.in/wheel/pmp/badge.png?style=flat
    :alt: PyPI Wheel
    :target: https://pypi.python.org/pypi/pmp

.. |supported-versions| image:: https://pypip.in/py_versions/pmp/badge.png?style=flat
    :alt: Supported versions
    :target: https://pypi.python.org/pypi/pmp


Pimp My Pillow will install a fully working Pillow distribution. No more 'decoder * is not supported' messages!"

* Free software: GPL V3 license

Installation
============

::

   [foo@host]$ git clone https://github.com/edvm/pimp-my-pillow.git
   [foo@host]$ cd pmp; python setup.py install 

   
Usage
=====

::

   [foo@host]$ pmp --help 
   [foo@host]$ pmp install 


To have openjpeg support, please install pmp/scripts/install-openjpeg.sh by hand, like:

::

   [foo@host]$ cd pmp/scripts/ 
   [foo@host]$ chmod +x ./install-openjpeg.sh; ./install-openjpeg.sh 


Then re-install/re-compile Pillow (ex: pip uninstall Pillow; pip install Pillow)

You should end with a full powered pillow installation like:

::

    *** TKINTER support not available
    --- JPEG support available
    --- OPENJPEG (JPEG2000) support available (2.1)
    --- ZLIB (PNG/ZIP) support available
    --- LIBTIFF support available
    --- FREETYPE2 support available
    --- LITTLECMS2 support available
    --- WEBP support available
    --- WEBPMUX support available

Now pray the gods so someone invite me a beer.


Documentation
=============

Currently Debian 7 and Ubuntu 14.10 are supported. This library use yaml files
to know which package should install, please take a look at pmp/settings/debian.yml 
or pmp/settings/ubuntu.yml. It uses one yaml file per gnu/linux distribution. At
each yaml file, keys are distro versions.

Soon documentation at read the docs

https://pimp-my-pillow.readthedocs.org/

Be sure to have python-devel, python-pip and gcc installed
