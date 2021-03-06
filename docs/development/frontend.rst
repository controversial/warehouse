Frontend
========

The Warehouse frontend is (as you might suspect) written in javascript with the
CSS handled by SCSS. It uses gulp to process these files and prepare them for
serving.

All of the static files are located in ``warehouse/static/`` and external
libraries are found in ``bower.json``.


Building
--------

Static files should be automatically built when ``make serve`` is running,
however you can trigger a manual build of them by installing all of the
dependencies using ``npm install`` and then running ``gulp dist``.


Browser Support
---------------

========= ====================
 Browser  Supported Versions
========= ====================
 Chrome   Current, Current - 1
 Firefox  Current, Current - 1
 Edge     Current, Current - 1
 Opera    Current, Current - 1
 Safari   9.0+
 IE       11+
========= ====================


HTML Code Style
---------------

Warehouse follows the
`Google HTML style guide <https://google.github.io/styleguide/htmlcssguide.xml>`_,
which is enforced via linting with
`HTML Linter <https://github.com/deezer/html-linter>`_.

Exceptions:

- Protocols can be included in links - with ``https`` preferred.
- All HTML tags should be closed.

One exception is that we allow both dashes and underscores in our class names,
as we follow the
`Nicholas Gallagher variation <http://nicolasgallagher.com/about-html-semantics-front-end-architecture/>`_
of the `BEM naming methodology <https://en.bem.info/>`_.

More information on how BEM works can be found in
`this article from CSS Wizardry <http://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/>`_.


SCSS Style and Structure
------------------------

Warehouse follows the `Airbnb CSS / Sass Styleguide <https://github.com/airbnb/css>`_,
with the exception that js hooks should be prefixed with ``-js`` rather than ``js``.

Our CSS codebase is structured according to the
`ITCSS system <http://www.creativebloq.com/web-design/manage-large-scale-web-projects-new-css-architecture-itcss-41514731>`_.
The principle of this system is to break CSS code into layers and import them
into a main stylesheet in and order moving from generic to specific.
This tightly controls the cascade of styles.

The majority of the SCSS styles are found within the 'blocks' layer,
with each BEM block in its own file. All blocks are documented at the top of
the file to provide guidelines for use and modification.
