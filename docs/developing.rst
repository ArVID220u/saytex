Development
=================


Deploying
---------

Build the package: ``python3 setup.py sdist bdist_wheel``.

Upload it to PyPI: ``twine upload dist/*``.


Documentation
-------------

Install sphinx: ``pip3 install sphinx``

Install theme: ``pip3 install sphinx_rtd_theme``

To update the docs, run ``sphinx-apidoc -o . ../saytex -f``, then ``rm -rf _build`` followed by ``make html``.