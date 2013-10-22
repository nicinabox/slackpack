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
2. Run `slackpack DIRECTORY -v VERSION` where DIRECTORY is the directory you want to package and VERSION is the target version number.

Run `slackpack -h` to view all options.

## Platform Support

Currently targeting OSX and Linux. Windows probably works.

## License

MIT. See LICENSE.txt for details.
