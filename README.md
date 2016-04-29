## Overview

*pdfgrep* is a tool to search text in PDF files. It works similarly to *grep*.

## Features

  - Grep compatible: pdfgrep tries to be compatible with GNU grep,
    where it makes sense. Many of your favorite grep options are
    supported (such as `-r`, `-i`, `-n` or `-c`).
  - Search many PDFs at once, even recursively in directories
  - Regular expressions: Posix or PCRE
  - Colored output
  - Support for password protected PDFs

For a complete documentation, please consult the [manpage].

## Example

    $ pdfgrep --max-count 1 --context 1 --with-filename --page-number pattern rabin-karp.pdf
	rabin-karp.pdf-1-randomized
	rabin-karp.pdf:1:pattern-matching
	rabin-karp.pdf-1-algorithms

## Dependencies

 - poppler-cpp (poppler >= 0.14) (http://poppler.freedesktop.org/)
 - optionally libpcre (http://www.pcre.org/)

## Building

... is easy. Just use the standard procedure:

    ./configure
    make
    sudo make install

The `./configure` script can take lots of options to customize the
build process, the most important of which are:

 - `--with-unac`: Build with experimental libunac support and add
   the `--unac` flag to pdfgrep that strips all accents from
   characters, making it possible to find the character 'ä' by
   searching 'a'.
 - `--with-{zsh,bash}-completion`: Configure installation directory
   for shell completion files.
 - `--without-libpcre`: Disable support for perl compatible regular
   expressions.
 - `--disable-doc`: Disable manpage generation.

See `configure --help` for more info or read the (very extensive)
`INSTALL` file in the source.

If you're using the git version, you will also have to run
`./autogen.sh` in advance.

## Download

Tarballs for releases are available at https://pdfgrep.org/download.html

The development version is available as a git repository at
https://gitlab.com/pdfgrep/pdfgrep

## Contact

General questions, suggestions, bug reports, patches or anything else
can be sent to the [mailinglist](mailto:pdfgrep-users@pdfgrep.org).

You can also use the [issue tracker] for bug reports or create a
[merge request] on GitLab, if you prefer that over mailinglists.


[manpage]: https://pdfgrep.org/doc.html
[issue tracker]: https://gitlab.com/pdfgrep/pdfgrep/issues
[merge request]: https://gitlab.com/pdfgrep/pdfgrep/merge_requests