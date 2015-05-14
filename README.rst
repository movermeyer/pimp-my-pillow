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

Currently Debian 7 and Ubuntu 14.10, 15.04 are supported (give support for other distros
is really easy, please keep reading). This library use yaml files
to know which package should install, please take a look at pmp/settings/debian.yml 
or pmp/settings/ubuntu.yml. It uses one yaml file per gnu/linux distribution. At
each yaml file, keys are distro versions.

Help me support more distros
----------------------------

If when installing your distro is still not supported, you will get a 
traceback like folows:

```
    (virtualenv) root@180121250ef0:/opt/pimp-my-pillow# pmp --help
    usage: pmp [-h] [--interactive] install

    Pimp My Pillow

    positional arguments:
      install        Install Pillow

    optional arguments:
      -h, --help     show this help message and exit
      --interactive  Non interactive
    (bombear) root@180121250ef0:/opt/pimp-my-pillow# pmp install
    Traceback (most recent call last):
      File "/opt/envs/bombear/bin/pmp", line 9, in <module>
        load_entry_point('pmp==0.1.0', 'console_scripts', 'pmp')()
      File "/opt/pimp-my-pillow/src/pmp/__init__.py", line 164, in main
        stderr, stdout = install_pillow(args_.interactive)
      File "/opt/pimp-my-pillow/src/pmp/__init__.py", line 97, in install_pillow
        install_pillow_dependencies(interactive)
      File "/opt/pimp-my-pillow/src/pmp/__init__.py", line 59, in install_pillow_dependencies
        conf = get_gnu_linux_distro_conf()
      File "/opt/pimp-my-pillow/src/pmp/__init__.py", line 50, in get_gnu_linux_distro_conf
        raise Exception("Unknown Gnu/Linux distribution.")
    Exception: Unknown Gnu/Linux distribution.
```

Its really easy to add support for your Gnu/Linux distro and version:

1- cat the content from /etc/issue, for ex: 
``` 
    [edvm@edvm-laptop pimp-my-pillow (master)]$ cat /etc/issue
    Ubuntu 15.04 \n \l

    [edvm@edvm-laptop pimp-my-pillow (master)]$
```

2- Copy and paste a sample setting file, for example:
    https://github.com/edvm/pimp-my-pillow/blob/master/src/pmp/settings/ubuntu.yml

3- The 'etc-issue' value must be the content from your /etc/issue (without the \n \l)

4- Put your setting file (it must end with .yml and must be a valid yaml file) with
the other settings and send the new file you created as a PR! :D 

Soon documentation at read the docs

https://pimp-my-pillow.readthedocs.org/

Be sure to have python-devel, python-pip and gcc installed
