# NAME

exact::me - Original program path locations extension for exact

# VERSION

version 1.04

[![test](https://github.com/gryphonshafer/exact-me/workflows/test/badge.svg)](https://github.com/gryphonshafer/exact-me/actions?query=workflow%3Atest)
[![codecov](https://codecov.io/gh/gryphonshafer/exact-me/graph/badge.svg)](https://codecov.io/gh/gryphonshafer/exact-me)

# SYNOPSIS

    use exact -me;

    say me();              # full path to $0
    say me('../dir/file'); # full path based on relative dir from $0 dir
    say me('dir/file');    # full path found from $0 dir or in a parent of it

# DESCRIPTION

[exact::me](https://metacpan.org/pod/exact%3A%3Ame) is an extension for [exact](https://metacpan.org/pod/exact) that imports a `me()` function into
the calling namespace.

    use exact -me;

# IMPORTED FUNCTION

The following function is imported:

## me

This function when called without any input will return the path to the current
program (`$0`):

    say me(); # full path to $0

When provided with a relative path, it will generate a full path by combining
the input with a full path to the current program (`$0`):

    say me('../dir/file'); # full path based on relative dir from $0 dir

For input that is a relative path that does not begin with ".", a relative
path will be searched for at or above the directory of the program (`$0`). If
found, that path will be returned; otherwise, `undef`.

    say me('dir/file'); # full path found from $0 dir or in a parent of it

See the [exact](https://metacpan.org/pod/exact) documentation for additional information about
extensions. The intended use of [exact::me](https://metacpan.org/pod/exact%3A%3Ame) is via the extension interface
of [exact](https://metacpan.org/pod/exact).

    use exact -me, -conf, -noutf8;

However, you can also use it directly, which will also use [exact](https://metacpan.org/pod/exact) with
default options:

    use exact::me;

# SEE ALSO

You can look for additional information at:

- [GitHub](https://github.com/gryphonshafer/exact-me)
- [MetaCPAN](https://metacpan.org/pod/exact::me)
- [GitHub Actions](https://github.com/gryphonshafer/exact-me/actions)
- [Codecov](https://codecov.io/gh/gryphonshafer/exact-me)
- [CPANTS](http://cpants.cpanauthors.org/dist/exact-me)
- [CPAN Testers](http://www.cpantesters.org/distro/D/exact-me.html)

# AUTHOR

Gryphon Shafer <gryphon@cpan.org>

# COPYRIGHT AND LICENSE

This software is Copyright (c) 2020-2050 by Gryphon Shafer.

This is free software, licensed under:

    The Artistic License 2.0 (GPL Compatible)
