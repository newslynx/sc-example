[![Build status](https://travis-ci.org/newslynx/sc-example.svg)](https://travis-ci.org/newslynx/sc-example) [![Documentation Status](https://readthedocs.org/projects/sc-example/badge/?version=latest)](https://readthedocs.org/projects/sc-example/?badge=latest)

sc-example
==========================================================================================

An example Sous Chef module generated by `newslynx sc-create`

## Installation

### Production

To install `sc-example` for an active installation of `newslynx-core`, clone it and copy into `~/.newslynx/sous-chefs`

```bash
$ git clone https://github.com/newslynx/sc-example.git
$ mv sc-example/ ~/.newslynx/sous-chefs/
```

Now install it within the same virtual environment as `newslynx`:

```bash
$ cd ~/.newslynx/sous-chefs/sc-example/
$ pip install .
```

... and if you're running `newslynx` as `sudo`


```bash
$ cd ~/.newslynx/sous-chefs/sc-example/ 
$ sudo pip install .
```

Finally, run `newslynx sc-sync` to `sc-example`'s Sous Chefs for all organizations.

```bash
$ newslynx sc-sync
```

### Development 

If you want to modify / add Sous Chefs to `sc-example`, instal it in it's own virtual environment.

**NOTE** Will install a fresh version of `newslynx` via `pip`.

```bash
$ mkvirtualenv sc-example
$ git clone https://github.com/newslynx/sc-example.git
$ cd sc-example
$ pip install --editable .
```

You should now be able to run `sc-example`'s Sous Chefs in development mode

```bash 
% newslynx sc sc_example/say_my_name.yaml --myname='Brian Abelson'
```

## Tests

Requires `nose`

```bash
$ make all_tests
```

## Documentation

Documentation for `sc-example` is hosted on [Read The Docs](http://sc-example.readthedocs.org/).

It's generated via the following steps

* converts this file (`README.md`) into a ReStructured Text file, saving it to [docs/index.rst](https://github.com/newslynx/sc-example/blob/master/docs/index.rst)
* runs `newslynx sc-docs sc_example -f rst` to generate documentation for all the Sous Chefs in `sc-example` and saves the output to [docs/sous-chefs.rst](https://github.com/newslynx/sc-example/blob/master/docs/sous-chefs.rst)
* Builds Sphinx Documentation from these files.


## Continuous Integration

Builds for `sc-example` can be found on [Travis](https://travis-ci.org/newslynx/sc-example)

## Contributing

See the [contributing guidelines](https://github.com/newslynx/sc-example/blob/master/CONTRIBUTING.md).


## What's in this module ?

- [README.md](https://github.com/newslynx/sc-example/blob/master/README.md)
	* This file 

- [VERSION](https://github.com/newslynx/sc-example/blob/master/VERSION)
	* `sc-example`'s source-of-truth version.

- [requirements.txt](https://github.com/newslynx/sc-example/blob/master/requirements.txt)
	* `sc-example`'s python dependencies.

- [MANIFEST.in](https://github.com/newslynx/sc-example/blob/master/MANIFEST.in)
	* Specifications for which files to include in the PyPI distribution.
	* See the docs on this [here](https://docs.python.org/2/distutils/sourcedist.html#specifying-the-files-to-distribute).

- [setup.py](https://github.com/newslynx/sc-example/blob/master/setup.py)
	* Specification's for building `sc-example`'s PyPI distribution.

- [.travis.yml](https://github.com/newslynx/sc-example/blob/master/.travis.yml)
	* Configurations for Travis Continuous Integration
	* You must activate this project on [travis-ci.org](https://github.com/newslynx/sc-example/blob/master/http://travis-ci.org/) for this to run on subsequent updates.

- [Makefile](https://github.com/newslynx/sc-example/blob/master/Makefile)
	* Helpers for managing `sc-example`.
	* Includes:
		- `make clean`: 
			* Cleans out cruft from this directory.
		- `make install`: 
			* Installs `sc-example`. Assumes that you're in a virtual environment.
		- `make all_tests`: 
			* Runs the tests.
		- `make readme`
			* Converts this file to `.rst`, including a table of contents, and saves it to [docs/index.rst](https://github.com/newslynx/sc-example/blob/master/docs/index.rst)
		- `make sous_chef_docs`
			* Programmtically generates [Sous Chef documentation](https://github.com/newslynx/sc-example/blob/master/docs/sous-chefs.rst) by running `newslynx sc-docs sc_example/ --format=rst > docs/sous-chefs.rst`.
		- `make all_docs`: 
			* Builds the sphinx docs for `sc-example` by running the above two commands.
		- `make view_docs`
			* Serves documentation at [localhost:8000](http://localhost:8000)
		- `make register`: 
			* Registers `sc-example` on [PyPI](https://pypi.python.org/pypi).
		- `make distribute`: 
			* Publishes a new version of `sc-example` to PyPI.

- [CONTRIBUTING.md](https://github.com/newslynx/sc-example/blob/master/CONTRIBUTING.md)

- [sc_example](https://github.com/newslynx/sc-example/blob/master/sc_example/)
	* `sc-example`'s source code and Sous Chef configuration files.

- [docs](https://github.com/newslynx/sc-example/blob/master/docs/)
	* Sphnix documentation for `sc-example`

- [tests](https://github.com/newslynx/sc-example/blob/master/tests/)
	* `nose` tests for `sc-example`

