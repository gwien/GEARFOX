# GEARFOX

Test1
Test2

# Überschrift 2

Test 3
Test 4


Build Process
=============

Files: `tasks.py`_ - `doc_builder/`_

.. _tasks.py: https://github.com/rtfd/readthedocs.org/blob/master/readthedocs/projects/tasks.py
.. _doc_builder/: https://github.com/rtfd/readthedocs.org/tree/master/readthedocs/doc_builder

How we build documentation
--------------------------

When we import your documentation, we look at two things first: your *Repository URL* and the *Documentation Type*.
We will clone your repository,
and then build your documentation using the *Documentation Type* specified.

Sphinx
~~~~~~

When you choose *Sphinx* as your *Documentation Type*,
we will first look for a ``conf.py`` file in your repository.

The :doc:`api/doc_builder` API explains the higher level parts of the API that you need to implement. A basic run goes something like this::

    backend = get_backend(project.documentation_type)
    if force:
        backend.force(version)
    backend.clean(version)
    backend.build(version)
    if success:
        backend.move(version)

Deleting a stale or broken build environment
--------------------------------------------

RTD doesn't expose this in the UI, but it is possible to remove the build directory of your project. If you want to remove a 
