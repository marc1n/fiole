Overview
========

.. currentmodule:: fiole

``fiole.py`` is a WSGI micro-framework with the following development
constraints:

* Single file, **no external dependency**
* Provide enough features to build a web application with minimal effort
* Embed **a compact template engine**
* Keep the module reasonably small


Main features:

* :doc:`Routing <routing>`
* :doc:`Methods GET/HEAD/POST/PUT/DELETE <routing>`
* :ref:`Error handlers <helpers>`
* File uploads (:func:`Request.POST`)
* :ref:`Static files <helpers>`
* :doc:`Fast template engine <template>`
* Secure cookies (:func:`Request.get_cookie`, :func:`Response.set_cookie`, ...)


**Disclaimer:** this framework is intentionally limited.  If you need a robust
and scalable solution, look elsewhere.


Quickstart
----------

Either download the single file :download:`fiole.py<../fiole.py>` and save it in your
project directory, or ``pip install fiole``, preferably in a ``virtualenv``.

Then create the first example and save it with name ``hello.py``:

::

  from fiole import get, run_fiole


  @get('/')
  def index(request):
      return 'Hello World!'

  run_fiole()


Then run this example (default port 8080) with:

::

  python hello.py


or (on port 4000 for example):

::

  python fiole.py -p 4000 hello


Next steps
----------

Have a look at the ``examples/`` for more use cases.  Run them::

  python fiole.py examples

Read the documentation about :doc:`routing` and :doc:`template`.

Some features are not yet covered in the documentation:

* sending and receiving cookies
* adding custom HTTP headers
* stacking multiple applications
* serving through a third-party WSGI server (gevent, ...)


Look at the :doc:`api` for crispy details.

Read the documentation of `Flask <http://flask.pocoo.org/docs/>`__ and
`Bottle <http://bottlepy.org/docs/dev/>`__ for more information about
web development in general.