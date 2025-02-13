MediaWiki
=========

.. image:: https://img.shields.io/badge/license-MIT-blue.svg
    :target: https://opensource.org/licenses/MIT/
    :alt: License
.. image:: https://img.shields.io/github/release/barrust/mediawiki.svg
    :target: https://github.com/barrust/mediawiki/releases
    :alt: GitHub release
.. image:: https://github.com/barrust/mediawiki/workflows/Python%20package/badge.svg
    :target: https://github.com/barrust/mediawiki/actions?query=workflow%3A%22Python+package%22
    :alt: Build Status
.. image:: https://codecov.io/gh/barrust/mediawiki/branch/master/graph/badge.svg?token=OdETiNgz9k
    :target: https://codecov.io/gh/barrust/mediawiki
    :alt: Test Coverage
.. image:: https://app.codacy.com/project/badge/Grade/34162198611f4aa0bde630d1dab72ce8    
    :target: https://www.codacy.com/gh/barrust/mediawiki/dashboard?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=barrust/mediawiki&amp;utm_campaign=Badge_Grade
    :alt: Codacy Review
.. image:: https://badge.fury.io/py/pymediawiki.svg
    :target: https://badge.fury.io/py/pymediawiki
    :alt: PyPi Release
.. image:: http://pepy.tech/badge/pymediawiki
    :target: https://pepy.tech/project/pymediawiki
    :alt: Downloads

***mediawiki*** is a python wrapper and parser for the MediaWiki API. The goal
is to allow users to quickly and efficiently pull data from the MediaWiki site
of their choice instead of worrying about dealing directly with the API. As
such, it does not force the use of a particular MediaWiki site. It defaults to
`Wikipedia <http://www.wikipedia.org>`__ but other MediaWiki sites can
also be used.

MediaWiki wraps the `MediaWiki API <https://www.mediawiki.org/wiki/API>`_
so you can focus on *leveraging* your favorite MediaWiki site's data,
not getting it. Please check out the code on
`github <https://www.github.com/barrust/mediawiki>`_!

**Note:** this library was designed for ease of use and simplicity. If you plan
on doing serious scraping, automated requests, or editing, please look into
`Pywikibot <https://www.mediawiki.org/wiki/Manual:Pywikibot>`__
which has a larger API, advanced rate limiting, and other features so we may
be considerate of the MediaWiki infrastructure. Pywikibot has also other extra
features such as support for Wikibase (that runs Wikidata).


Installation
------------------

Pip Installation:

::

    $ pip install pymediawiki

To install from source:

To install ``mediawiki``, simply clone the `repository on GitHub
<https://github.com/barrust/mediawiki>`__, then run from the folder:

::

    $ python setup.py install

``mediawiki`` supports python versions 3.7 - 3.12

For *python 2.7* support, install `release 0.6.7 <https://github.com/barrust/mediawiki/releases/tag/v0.6.7>`__

::

    $ pip install pymediawiki==0.6.7

Documentation
-------------

Documentation of the latest release is hosted on
`readthedocs.io <http://pymediawiki.readthedocs.io/en/latest/?>`__

To build the documentation yourself run:

::

    $ pip install sphinx
    $ cd docs/
    $ make html

Automated Tests
------------------

To run automated tests, one must simply run the following command from the
downloaded folder:

::

  $ python setup.py test


Quickstart
------------------

Import mediawiki and run a standard search against Wikipedia:

.. code:: python

    >>> from mediawiki import MediaWiki
    >>> wikipedia = MediaWiki()
    >>> wikipedia.search('washington')

Run more advanced searches:

.. code:: python

    >>> wikipedia.opensearch('washington')
    >>> wikipedia.allpages('a')
    >>> wikipedia.geosearch(title='washington, d.c.')
    >>> wikipedia.geosearch(latitude='0.0', longitude='0.0')
    >>> wikipedia.prefixsearch('arm')
    >>> wikipedia.random(pages=10)

Pull a MediaWiki page and some of the page properties:

.. code:: python

    >>> p = wikipedia.page('Chess')
    >>> p.title
    >>> p.summary
    >>> p.categories
    >>> p.images
    >>> p.links
    >>> p.langlinks

See the `documentation for more examples!
<http://pymediawiki.readthedocs.io/en/latest/quickstart.html#quickstart>`_



Changelog
------------------

Please see the `changelog
<https://github.com/barrust/mediawiki/blob/master/CHANGELOG.md>`__ for a list
of all changes.


License
-------

MIT licensed. See the `LICENSE file
<https://github.com/barrust/Wikipedia/blob/master/LICENSE>`__
for full details.
