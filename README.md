# actions-cache-installed-files

![actions-cache-installed-files](https://github.com/office-tecoli/actions-cache-installed-files/actions/workflows/test.yml/badge.svg)

This Github action execute given `command` for `target`, and cache
installed files for later use.  When executed next time with same
package list, and any other environment are not changed, updated files
are extracted from the cached archive.

Output is same as [`@actions/cache`](https://github.com/actions/cache).

## Usage

```yaml
# inputs:
#   command:   { required: true,  type: string }
#   target:    { required: true,  type: string }
#   directory: { required: true,  type: string }
#   cache:     { required: false, type: string, default: yes }
#   cache-gen: { required: false, type: string, default: v1 }

- uses: office-tecoli/actions-cache-installed-files@v0
  with:

    # install command
    command: ''

    # install target
    target: ''

    # install directory
    # multiple directories can be specified
    directory: ''

    # Cache strategey
    #
    # yes:      activate cache
    # no:       no cache
    # workflow: effective within same workflow (mainly for test)
    #
    cache: yes

    # Cache generation.
    # You can set any string to this parameter and different generation
    # number produces different cache key.
    #
    # Default: v1
    cache-gen: v1
```

## Example

```yaml
- uses: office-tecoli/actions-cache-installed-files@v0
  with:
    command: brew install
    target:  rcs cvs
    directory: /usr/local
```

## See Also

### [`@office-tecoli/actions-use-brew-tools`](https://github.com/office-tecoli/actions-use-brew-tools)

[`@actions-use-brew-tools`](https://github.com/office-tecoli/actions-use-brew-tools)
uses this action as a backend of its work.
