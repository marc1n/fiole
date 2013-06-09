Changelog
=========

.. currentmodule:: fiole

0.x (unreleased)
~~~~~~~~~~~~~~~~

* Improve the documentation.

* Add the Fiole application to the WSGI environment:
  ``environ['fiole.app']``.  (Issue #1)

* Implement parsing of the ``Accept`` headers, and add them as dynamic
  properties of ``Request``: ``accept``, ``accept_charset``,
  ``accept_encoding`` and ``accept_language``.  (Issue #2)

* Replace the global ``SECRET_KEY`` with a new attribute of
  the Fiole application ``app.secret_key``.

* Replace the helpers ``_create_signed_value`` and ``_decode_signed_value``
  with methods: :meth:`Fiole.encode_signed` and :meth:`Fiole.decode_signed`.
  The method :meth:`Response.create_signed_value` is removed too.

* Remove argument ``secret`` from the ``run_fiole`` function: use
  ``get_app().secret_key = 's3c4e7k3y...'`` instead.

* The ``send_file`` helper recognizes the ``If-Modified-Since`` header and
  returns *"304 Not Modified"* appropriately.

* Patch the ``wsgiref.simple_server.ServerHandler`` to stop sending
  ``Content-Length`` for status *"304 Not Modified"*.  `Issue 18099
  <http://bugs.python.org/issue18099>`__

* Add ``Fiole.debug`` boolean flag to let unhandled exceptions propagate.

* Rename helper ``html_escape`` to ``escape_html``.

* Add ``default_filters`` for the template engine configuration.

* Automatically cast Python objects to Unicode for template rendering.
  This can be disabled with ``engine.default_filters = None``.

* Refactor the internals of the template engine.  New method
  ``Engine.clear()`` to reset the cache of byte-compiled templates.


0.2 (2013-05-22)
~~~~~~~~~~~~~~~~

* Initial release.