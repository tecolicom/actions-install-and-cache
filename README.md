# actions-install-and-cache

![actions-install-and-cache](https://github.com/tecoli-com/actions-install-and-cache/actions/workflows/test.yml/badge.svg)

This GitHub action execute given `command` for `target`, and cache
installd files for later use.  When executed next time with same
package list, and any other environment are not changed, updated files
are extracted from the cached archive.

This action uses actions/cache and produce different cache key for
different operating system environment.  If you need to use different
cache for other reason, provide a key by parameter.

Output is same as [`@actions/cache`](https://github.com/actions/cache).

## Usage

```yaml
# inputs:
#   command:   { required: true,  type: string }
#   target:    { required: true,  type: string }
#   directory: { required: true,  type: string }
#   cache:     { required: false, type: string, default: yes }
#   key:       { required: false, type: string }

- uses: tecoli-com/actions-install-and-cache@v0
  with:

    # install command
    command: ''

    # install target
    target: ''

    # install directory
    # multiple directories can be specified
    directory: ''

    # Cache strategy
    #
    # yes:      activate cache
    # no:       no cache
    # workflow: effective within same workflow (mainly for test)
    #
    cache: yes

    # Additional cache key
    key: ''
```

## Example

```yaml
- uses: tecoli-com/actions-install-and-cache@v0
  with:
    command: brew install
    target:  rcs cvs
    directory: /usr/local
```

## See Also

### [tecoli-com/actions](https://github.com/tecoli-com/actions)

### [tecoli-com/actions-use-homebrew-tools](https://github.com/tecoli-com/actions-use-homebrew-tools)

[`@actions-use-homebrew-tools`](https://github.com/tecoli-com/actions-use-homebrew-tools)
uses this action as a backend of its work.
