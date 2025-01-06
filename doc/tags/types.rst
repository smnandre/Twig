``types``
=========

.. versionadded:: 3.13

    The ``types`` tag was added in Twig 3.13. This tag is **experimental** and
    can change based on usage and feedback.

The ``types`` tag declares the types of template variables.

.. note::

    The types declared in a template are local to that template and must not be
    propagated to included templates. This is because a template can be
    included from multiple different places, each potentially having different
    variable types.

Here is how to declare that ``is_correct`` is a boolean, while ``score`` is a
number (see note below):

.. code-block:: twig

    {% types {
        is_correct: 'boolean',
        score: 'number',
    } %}

You can declare variables as optional by adding the ``?`` suffix:

.. code-block:: twig

    {% types {
        is_correct: 'boolean',
        score?: 'number',
    } %}

By default, this tag does not affect the template compilation or runtime behavior.

Its purpose is to enable designers and developers to document and specify the
context's available and/or required variables. While Twig itself does not
validate variables or their types, this tag enables extensions to do this.

Additionally, :ref:`Twig extensions <creating_extensions>` can analyze these
tags to perform compile-time and runtime analysis of templates.

.. note::

    The syntax for and contents of type strings are intentionally left out of
    scope.
