Ansible Role for SuperVisor
===========================

|Build Status| |GitHub issues| |GitHub license|

postgresql for ansible

:Version: 0.0.0
:Web: https://github.com/equipindustry/ansible-role-supervisor
:Download: http://github.com/equipindustry/ansible-role-supervisor
:Source: http://github.com/equipindustry/ansible-role-supervisor
:Keywords: ansible-role-supervisor

.. contents:: Table of Contents:
    :local:

A role for deploying and configuring
`Supervisord <http://supervisord.org/>`__ and extensions on unix hosts
using `Ansible <http://www.ansibleworks.com/>`__ It can additionally be
used as a playbook for quickly provisioning hosts. Vagrant machines are
provided to produce a boxed install of Supervisord or a VM for
integration testing.

Supports
--------


Requirements
------------

-  Linux
-  none
-  OSX
-  `Homebrew <http://brew.sh/>`__ must be installed.

Role Variables
--------------

The default role variables in ``defaults/main.yml`` are:

.. code-block:: yaml

    supervisor_user: {{user}}

    # defaults file for supervisor
    supervisor_apps:
      - program: name
        application_path: /home/user/project/src
        application_source_file: {{ deployment_file_load_virtualenvwrapper }}
        execution: celery -A {{ app_name }} worker --loglevel=info

    supervisor_programs:
      - program: name
        command: 'command'
        user: "user"
        directory: "directory"
        numprocs: 1
        instalautostart: true
        autorestart: true
        startsecs: 10
        priority: 990
        disabled_program: name program to disabled
        supervisor_environment_dict:
            ENVIRONMENT: 'VALUE1'


Dependencies
------------

None

Example Playbook
----------------

See the `examples <./examples/>`__ directory.

To run this playbook with default settings, create a basic playbook like
this:

.. code:: yaml

    - hosts: servers
        roles:
        - equipindustry.supervisor

License
-------

The code in this repository is licensed under the Apache unless
otherwise noted.

Please see LICENSE_ for details.

Changelog
---------

Please see `CHANGELOG`_ for more information what
has changed recently.

Contributing
------------

Contributions are welcome!

Review the `CONTRIBUTING`_ for details on how to:

Versioning
----------

Releases are managed using bitbucket release feature. We use [Semantic Versioning](http://semver.org) for all
the releases. Every change made to the code base will be referred to in the release notes (except for
cleanups and refactorings).


Contact Info
------------

Feel free to contact me to discuss any issues, questions, or comments.

* `Email`_
* `Twitter`_
* `GitHub`_
* `LinkedIn`_
* `Website`_
* `PGP`_

|linkedin| |beacon|

Made with :coffee: and :pizza: by `Luis Mayta`_ and `equipindustry`_.

.. Links
.. _`changelog`: CHANGELOG.rst
.. _`contributors`: docs/source/AUTHORS.rst
.. _`contributing`: docs/source/CONTRIBUTING.rst
.. _`LICENSE`: LICENSE

.. _`equipindustry`: https://github.com/equipindustry
.. _`Luis Mayta`: https://github.com/luismayta


.. _`Github`: https://github.com/luismayta
.. _`Linkedin`: https://pe.linkedin.com/in/luismayta
.. _`Email`: slovacus@gmail.com
    :target: mailto:slovacus@gmail.com
.. _`Twitter`: https://twitter.com/slovacus
.. _`Website`: https://luismayta.github.io
.. _`PGP`: https://keybase.io/luismayta/pgp_keys.asc

.. |Build Status| image:: https://travis-ci.org/equipindustry/ansible-role-supervisor.svg
   :target: https://travis-ci.org/equipindustry/ansible-role-supervisor
.. |GitHub issues| image:: https://img.shields.io/github/issues/equipindustry/ansible-role-supervisor.svg
   :target: https://github.com/equipindustry/ansible-role-supervisor/issues
.. |GitHub license| image:: https://img.shields.io/github/license/mashape/apistatus.svg?style=flat-square
   :target: LICENSE

.. Team:
.. |Luis Mayta| image:: https://github.com/luismayta.png?size=100
   :target: https://github.com/luismayta

.. Badges for images hub docker
.. |MicroBadger| image:: https://images.microbadger.com/badges/image/equipindustry/python.svg
   :target: http://microbadger.com/images/equipindustry/python
.. |Docker Stars| image:: https://img.shields.io/docker/stars/equipindustry/python.svg?style=flat-square
   :target: https://hub.docker.com/r/equipindustry/python
.. |Docker Pulls| image:: https://img.shields.io/docker/pulls/equipindustry/python.svg?style=flat-square
   :target: https://hub.docker.com/r/equipindustry/python

.. Footer:
.. |linkedin| image:: http://www.linkedin.com/img/webpromo/btn_liprofile_blue_80x15.png
   :target: https://pe.linkedin.com/in/luismayta
.. |beacon| image:: https://ga-beacon.appspot.com/UA-65019326-1/github.com/equipindustry/ansible-role-supervisor/readme
   :target: https://github.com/equipindustry/ansible-role-supervisor

.. Dependences:

.. _Pyenv: https://github.com/pyenv/pyenv
.. _Docker: https://www.docker.com/
