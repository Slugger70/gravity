=========
 History
=========

0.13.5
======

- If virtualenv is set in the Gravity config, automatically add its bin dir to $PATH if the gx-it-proxy is enabled by @natefoo in https://github.com/galaxyproject/gravity/pull/71
- Support converting settings to command line arguments in a generalized way by @natefoo in https://github.com/galaxyproject/gravity/pull/73

0.13.4
======

- Fixes for startup test by @natefoo in https://github.com/galaxyproject/gravity/pull/68
- Fix setting environment vars on handlers by @natefoo in https://github.com/galaxyproject/gravity/pull/70

0.13.3
======

- Don't use gunicorn logging options with unicornherder by @natefoo in https://github.com/galaxyproject/gravity/pull/65

0.13.2
======

- Don't override PATH in subprocess call by @jdavcs in https://github.com/galaxyproject/gravity/pull/62
- Only send pre create hook by @mvdbeek in https://github.com/galaxyproject/gravity/pull/64

0.13.1
======

- Set correct default for environment settings by @natefoo in https://github.com/galaxyproject/gravity/pull/58
- Don't catch exceptions in the deregister, register, and rename subcommands by @natefoo in https://github.com/galaxyproject/gravity/pull/59
- ``processes`` in the ``handling`` dict in the job conf dict is a dict, not a list by @natefoo in https://github.com/galaxyproject/gravity/pull/60

0.13.0
======

- Add options to enable/disable gunicorn, celery, and celery-beat services by @natefoo in https://github.com/galaxyproject/gravity/pull/47
- Add ability to include gravity config from a separate file and document by @natefoo in https://github.com/galaxyproject/gravity/pull/48
- Only default to preload = true for gunicorn if not using unicornherder by @natefoo in https://github.com/galaxyproject/gravity/pull/49
- Add option to specify tusd path by @natefoo in https://github.com/galaxyproject/gravity/pull/50
- Support setting per-service environment variables by @natefoo in https://github.com/galaxyproject/gravity/pull/56

0.12.0
======

- Fix typo in ``log_dir`` description by @nsoranzo in https://github.com/galaxyproject/gravity/pull/44
- Shortcut individual services fix by @natefoo in https://github.com/galaxyproject/gravity/pull/45
- Add additional options to celery beat / celery workers by @mvdbeek in https://github.com/galaxyproject/gravity/pull/46

0.11.0
======

- Allow setting supervisor socket path via environment variable by @mvdbeek in https://github.com/galaxyproject/gravity/pull/36
- Automatically switch to non-sample galaxy.yml if it exists by @mvdbeek in https://github.com/galaxyproject/gravity/pull/39
- Add pydantic config schema by @mvdbeek in https://github.com/galaxyproject/gravity/pull/42
- Add --quiet option to galaxy and galaxyctl start by @mvdbeek in https://github.com/galaxyproject/gravity/pull/40
- Add support for yaml job config by @mvdbeek in https://github.com/galaxyproject/gravity/pull/37
- Add --preload support for gunicorn by @mvdbeek in https://github.com/galaxyproject/gravity/pull/41
- Support running tusd by @natefoo in https://github.com/galaxyproject/gravity/pull/23

0.10.0
======

- Fix for the case where a job_conf.xml exists but no handlers are defined by @natefoo in https://github.com/galaxyproject/gravity/pull/24
- Do not raise error if config file section is empty by @nsoranzo in https://github.com/galaxyproject/gravity/pull/25
- Add tests for static handlers and a defined job_conf.xml with no handlers by @natefoo in https://github.com/galaxyproject/gravity/pull/26
- Fix minor typos in readme by @ic4f in https://github.com/galaxyproject/gravity/pull/27
- Move configuration to gravity key of galaxy.yml file by @mvdbeek in https://github.com/galaxyproject/gravity/pull/28
- Fix for resolved galaxy.yml.sample symlink by @mvdbeek in https://github.com/galaxyproject/gravity/pull/31
- Support managing gx-it-proxy via gravity by @mvdbeek in https://github.com/galaxyproject/gravity/pull/32

0.9
===

- Gunicorn/fastAPI support, click support, tests by @mvdbeek in https://github.com/galaxyproject/gravity/pull/14
- Don't test on Python 3.6, which is unsupported by @natefoo in https://github.com/galaxyproject/gravity/pull/17
- Update README. Also some various small bugfixes and fixes for other stuff mentioned in the README by @natefoo in https://github.com/galaxyproject/gravity/pull/18
- Add unicornherder support by @natefoo in https://github.com/galaxyproject/gravity/pull/15
- Expose the log following used by `start -f` as its own subcommand. by @natefoo in https://github.com/galaxyproject/gravity/pull/16
- Better integration with Galaxy's run.sh by @natefoo in https://github.com/galaxyproject/gravity/pull/19
- Use relative paths in supervisord by @natefoo in https://github.com/galaxyproject/gravity/pull/21
- Converted CLI from `argparse`_ to `click`_.
- Stole ideas and code from `planemo`_ in general.
- Improve the AttributeDict so that it can have "hidden" items (anything that
  starts with a ``_``) that won't be serialized. Also, it serializes itself and
  can be created via deserialization from a classmethod. This simplifies using
  it to persist state data in the new GravityState subclass.

.. _argparse: https://docs.python.org/3/library/argparse.html
.. _click: http://click.pocoo.org/
.. _planemo: https://github.com/galaxyproject/planemo

0.8.3
=====

- Merge ``galaxycfg`` and ``galaxyadm`` commands to ``galaxy``.

0.8.2
=====

- Allow for passing names of individual services directly to ``supervisorctl``
  via the ``start``, ``stop``, and ``restart`` methods.
- Fix a bug where uWSGI would not start when using the automatic virtualenv
  install method.

0.8.1
=====

- Version bump because I deleted the 0.8 files from PyPI, and despite the fact
  that it lets you delete them, it doesn't let you upload once they have been
  uploaded once...

0.8
===

- Add auto-register to ``galaxy start`` if it's called from the root (or
  subdirectory) of a Galaxy root directory.
- Make ``galaxycfg remove`` accept instance names as params in addition to
  config file paths.
- Use the same hash generated for an instance name as the hash for a generated
  virtualenv name, so virtualenvs are more easily identified as belonging to a
  config.
- Renamed from ``galaxyadmin`` to ``gravity`` (thanks John Chilton).

0.7
===

- Added the ``galaxyadm`` subcommand ``graceful`` on a suggestion from Nicola
  Soranzo.
- Install uWSGI into the config's virtualenv if requested.
- Removed any dependence on Galaxy and eggs.
- Moved project to its own repository from the Galaxy clone I'd been working
  from.

Older
=====

- Works in progress as part of the Galaxy code.
