# Slackpack

Simple package building for Slackware. Designed for unRAID.

## The problem

More often than not, source code is not what the final build should be. You've got config files, tests, hidden files, and possibly directories that need to be mapped to a new location.

Slackpack is a config file in your project's directory that lets you create a Slackware-compatible package by specifying excludes and prefixes.

## What about make?

Historically, Slackware's `makepkg` works great with make when you need to compile binaries and build "real" Linux packages. Slackpack is designed for use with unRAID addons, most of which are partially web-based and don't include compiled binaries.

## Install

Probably clone the repo and run `bin/slackpack` directly. No installer/distribution system exists at this time. Requires Python 2.7.

## Usage

1. Add a `.slackpack` file to your project
2. Run `slackpack DIRECTORY` where DIRECTORY is the directory you want to package.

Run `slackpack -h` to view all options. Check [trolley](https://github.com/nicinabox/trolley/blob/master/.slackpack) for a working slackpack example.

## .slackpack example

.slackpack is a json configuration.

    {
      "name": "trolley",  // required
      "version": "1.0.0", // required
      "arch": "noarch",   // optional, defaults to 'noarch'
      "build": "unraid",  // optional, defaults to 'unraid'

      // required, ignored files will be excluded from the final package
      "ignore": ["install.sh", ".gitignore", "packages.json"],

      // optional, define directory mappings
      "prefix": {
        "usr/local": ["bin"],
        "usr/docs/trolley": ["README.md", "LICENSE.txt"]
      }
    }

## Platform Support

Currently targeting OSX and Linux. Windows probably works.

## Known Issues

* makepkg uses tar-1.13 to archive directories. Newer tar versions don't create quite the same output, leading installpkg to believe it wasn't made with makepkg, even though the same tar command is used.

## License

MIT. See LICENSE.txt for details.
