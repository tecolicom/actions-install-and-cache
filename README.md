# actions-install-and-cache

![actions-install-and-cache](https://github.com/tecolicom/actions-install-and-cache/actions/workflows/test.yml/badge.svg)

This GitHub action execute given script, and cache installed files for
later use.  When executed next time with same package list, and any
other environment are not changed, updated files are extracted from
the cached archive.

This action uses actions/cache and produce different cache key for
different operating system environment.  If you need to use different
cache for other reason, provide a key by parameter.

Output is same as [`@actions/cache`](https://github.com/actions/cache).

## Usage

```yaml
# inputs:
#   run:     { required: true,  type: string }
#   path:    { required: true,  type: string }
#   cache:   { required: false, type: string, default: yes }
#   key:     { required: false, type: string }
#   sudo:    { required: false, type: boolean }
#   verbose: { required: false, type: boolean, default: false }

- uses: tecolicom/actions-install-and-cache@v1
  with:

    # install script
    run: ''

    # install path
    # multiple directories can be specified
    path: ''

    # Cache strategy
    #
    # yes:      activate cache
    # no:       no cache
    # workflow: effective within same workflow (mainly for test)
    #
    cache: yes

    # Additional cache key
    key: ''

    # sudo: sudo or not
    sudo: false

    # verbose: show verbose output
    verbose: false
```

## Example

```yaml
- uses: tecolicom/actions-install-and-cache@v1
  with:
    run:  brew install rcs cvs
    path: /usr/local
```

## See Also

### [tecolicom/actions](https://github.com/tecolicom/actions)

### [tecolicom/actions-install-and-archive](https://github.com/tecolicom/actions-install-and-archive)

### [tecolicom/actions-use-homebrew-tools](https://github.com/tecolicom/actions-use-homebrew-tools)

[`@actions-use-homebrew-tools`](https://github.com/tecolicom/actions-use-homebrew-tools)
uses this action as a backend of its work.
