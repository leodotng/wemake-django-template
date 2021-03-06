Documentation
=============

`We <https://github.com/wemake-services/meta>`_ write a lot of documentation.
Since we believe, that documentation is a crucial factor
which defines project success or failure.

Here's how we write docs for ``django`` projects.


Dependencies
------------

We are using ``sphinx`` as a documentation builder.
We use ``sphinx.ext.napoleon`` to write
pretty docstrings inside the source code.
We also use ``sphinx_autodoc_typehints`` to inject type annotations into docs.

We also use two sources of truth for the dependencies here:

- ``docs/requirements.txt``
- ``pyproject.toml``

Why? Because we are using ReadTheDocs
for this template (only for original Github repo), and it
does only support traditional ``requirements.txt``.


Structure
---------

We use a clear structure for this documentation.

- ``pages/template`` contains docs
  from `wemake-django-template <https://github.com/wemake-services/wemake-django-template>`_.
  These files should not be modified locally.
  If you have any kind of question or problems,
  just open an issue `on github <https://github.com/wemake-services/wemake-django-template/issues>`_
- ``pages/project`` contains everything related to the project itself.
  Usage examples, an auto-generated documentation from your source code,
  configuration, business, and project goals
- ``documents`` contains different non-sphinx documents
  like ``doc`` files, spreadsheets, and mockups

Please, do not mix it up.

How to structure project docs
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

It is a good practice to write a single ``rst`` document
for every single ``py`` file.
Obviously, ``rst`` structure fully copies the structure of your source code.
This way it is very easy to navigate through the docs,
since you already know the structure.

For each ``django`` application we tend to create
a file called ``index.rst`` which is considered
the main fail for the application.

And ``pages/project/index.rst`` is the main file for the whole project.


How to contribute
-----------------

We enforce everyone to write clean and explaining documentation.
However, there are several rules about writing styling.

We are using `doc8 <https://pypi.python.org/pypi/doc8>`_ to validate our docs.
So, here's the command to do it:

.. code:: bash

  doc8 ./docs

This is also used in our CI process, so your build will fail
if there are violations.


Further reading
---------------

- `sphinx <http://www.sphinx-doc.org/en/stable/>`_
- `sphinx with django <https://docs.djangoproject.com/en/1.11/internals/contributing/writing-documentation/#getting-started-with-sphinx>`_
- `sphinx-autodoc-typehints <https://github.com/agronholm/sphinx-autodoc-typehints>`_
