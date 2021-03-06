
Constance - Dynamic Django settings
===================================

This is adopted version of standard library for Leonardo CMS.

Additionaly features:

* support for Django 1.8 +
* basic grouping via ``CONSTANCE_CONFIG_GROUPS`` which makes tabs for django admin
* access to config keys from standard django settings
* really live settings, set every value to django settings and respect the default value from them

.. code-block:: python

    CONSTANCE_CONFIG_GROUPS = {'Group 1': {
                                MY_AWESOME_KEY: ('default', help text)
                                }
                            }

.. code-block:: python

    from django.conf import settings

    settings.MY_AWESOME_KEY

settings.py

.. code-block:: python

    DEBUG = True

    CONSTANCE_CONFIG_GROUPS = {'Group 1': {
                                DEBUG: (False, help text)
                                }
                            }

    from django.conf import settings
    settings.DEBUG
    -> True

after setting up value in the admin to False::

    from django.conf import settings
    settings.DEBUG
    -> False

.. image:: https://secure.travis-ci.org/jezdez/django-constance.png
    :alt: Build Status
    :target: http://travis-ci.org/jezdez/django-constance

A Django app for storing dynamic settings in pluggable backends (Redis and
Django model backend built in) with an integration with the Django admin app.

For more information see the documentation at:

http://django-constance.readthedocs.org/

If you have questions or have trouble using the app please file a bug report
at:

https://github.com/jezdez/django-constance/issues
