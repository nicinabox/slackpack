# Slackpack

A simple tool for creating Slackware packages. Designed for unRAID.

## The problem

More often than not, source code is not what the final build should be. You've got config files, tests, hidden files, and possibly directories that need to be mapped to a new location.

Slackpack is a config file in your project's directory that lets you create a Slackware-compatible package by specifying excludes and prefixes.

## What about make?

Historically, Slackware's `makepkg` works great with make when you need to compile binaries and build "real" Linux packages. Slackpack is designed for use with unRAID addons, most of which are partially web-based and don't include compiled binaries.

## Usage

1. Add a `.slackpack` file to your project
2. Run `slackpack DIRECTORY` against the target directory.

## Platform Support

Currently targeting OSX and Linux.
