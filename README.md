# ISARIC Clinical Epidemiology Platform Documentation

This is an integrated documentation repository for the ISARIC Clinical Epidemiology Platform, containing all source content and assets required to build and deploy platform documentation, principally to a Read the Docs (RTD) site (community edition).

## Project TOML & Dependencies

No build system metadata is required in this TOML as no packages or other artifacts will be produced. The TOML only serves as a place to define docs dependencies for the repo package manager, which is Astral UV. The project version attribute is simply a placeholder to allow the TOML to be processes as valid - it is not used to define the documentation versioning, which will instead be done via the `conf.py`.

The dependencies listed in the TOML are all related to documentation, and the principal dependency is Sphinx. There is no pinning required for the moment, but this may change dependending on the situation. There are no separate development or optional dependencies, as this is not a code repository, so all d

The recommended package manager is [Astral `uv`](https://docs.astral.sh/uv), but other tools may also be used if preferred.

There is a hash-free `requirements.txt` which can be generated using:
```shell
uv export -v --format requirements.txt --no-hashes -o requirements.txt
```
This command takes the source list of dependencies from the dependencies defined in the TOML. The `--no-hashes` flag ensures that the file does not contain file hashes, which would otherwise prevent a `pip` installation. Another way of generating the `requirements.txt` is via `pip-compile` (from [`pip-tools`](https://pip-tools.readthedocs.io/en/latest/)):
```shell
pip-compile -o requirements.txt pyproject.toml
```
There is also a [`pylock.toml`](https://packaging.python.org/en/latest/specifications/pylock-toml/), with full dependency file hashes, which can be generated (with `uv`) using:
```shell
uv export -v --format pylock.toml -o pylock.toml
```
The `requirements.txt` and `pylock.toml` can be used individually to install all project dependencies, either using`uv` itself, for example:
```shell
uv pip install -r pylock.toml
```
or
```shell
uv pip install -r requirements.txt
```
or just the `requirements.txt` using `pip` as long as it does not contain hashes.

## Documentation Sources & Assets

TODO