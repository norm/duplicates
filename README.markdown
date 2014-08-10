duplicates
==========

Yet another duplicated file finder. You probably don't want to use it, as
it requires redis, various perl libraries, isn't documented, and isn't
particularly featureful.

Usage
-----

* `duplicates scan [-v] [<dir> ...]`

Looks for duplicate files in `dir`s. Defaults to current directory.

* `duplicates list [<dir> ...]`

Lists files in `dir`s that have duplicates elsewhere. Defaults to
current directory.

* `duplicates list [-v] -a`

List all registered matches. Use "-v" to verbosely list the SHA1 and
group matches rather than just listing filenames.

* `duplicates matches [-v] <file> [...]`

Lists the duplicates of `file`s. Use "-v" to verbosely list the SHA1
and group matches rather than just listing filenames.

* `duplicates delete [-v] <dir> [...]`

Deletes any files within `dir`s that have duplicates elsewhere. Will
re-read the content of duplicate files before deleting to confirm
they are still duplicates.

* `duplicates delete-others [-v] <dir> [...]`

Deletes any files that are duplicates of those within `dir`s. Will
re-read the content of duplicate files before deleting to confirm
they are still duplicates.

* `duplicates rescan [-v] [<dir> ...]`

Re-reads all registered duplicate files (optionally only within
`dir`s) to confirm they are still duplicates. Defaults to re-reading
all registered files.

* `duplicates stats [-v]`

Print some information about the duplicate files. Use "-v" to list
the top 10 duplicates (in terms of file size).

* `duplicates wipe`

Removes all information stored in redis.

