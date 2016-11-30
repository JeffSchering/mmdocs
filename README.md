# mmdocs

The purpose of this repo is to demonstrate two different styles of docset for the Mattermost documentation, using the Ubuntu 14.04 installation docs as a starting point. One of these styles, or perhaps a variation of them, will be chosen for the docs going forward, and then I'll redo the rest of the installations accordingly.

One docset is a monolithic style where the entire installation on Ubuntu 14.04 is in one document. The other is modular, with one topic per page.

+ [Monolithic version](https://jeffschering.github.io/mmdocs/monolith/install/install-ubuntu-1404-overview.html)
+ [Modular version](https://jeffschering.github.io/mmdocs/modular/install/install-ubuntu-1404-overview.html)

In addition to reworking the structure, I also edited the content to bring it in line with modern technical writing conventions and with the nascent Mattermost style guide.

I also made the source more modular by breaking longer multi-topic documents up into single-topic documents. This should make the docs easier to handle, easier to reuse, and easier to maintain.

The source for each style is identical, with the exception of one document: **install-ubuntu-1404-overview.rst**. The only difference between the two versions of this document is how the source files are referenced. The modular version uses the *.. toctree::* directive and the monolithic version uses a series of *.. include::* directives.

## Monolithic version of install-ubuntu-1404-overview.rst

```rst
.. _install-ubuntu-1404-overview:

=========================================
Installing Mattermost on Ubuntu 14.04 LTS
=========================================

Install a production-ready Mattermost system on 1 to 3 machines.

.. include:: install-common-intro.rst

.. contents:: Install the components in the following order:
  :backlinks: top
  :local:
  
.. include:: install-ubuntu-1404.rst
.. include:: install-ubuntu-1404-mysql.rst
.. include:: install-ubuntu-1404-postgresql.rst
.. include:: install-ubuntu-1404-mattermost.rst
.. include:: install-nginx.rst
```
## Modular version of install-ubuntu-1404-overview.rst

```rst
.. _install-ubuntu-1404-overview:

=========================================
Installing Mattermost on Ubuntu 14.04 LTS
=========================================

Install a production-ready Mattermost system on 1 to 3 machines.

.. include:: install-common-intro.rst

.. contents:: Install the components in the following order:
  :backlinks: top
  :local:

.. toctree::
  :maxdepth: 1
  
  install-ubuntu-1404.rst
  install-ubuntu-1404-mysql.rst
  install-ubuntu-1404-postgresql.rst
  install-ubuntu_1404-mattermost.rst
  install-nginx.rst
```
