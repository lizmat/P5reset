[![Actions Status](https://github.com/lizmat/P5reset/workflows/test/badge.svg)](https://github.com/lizmat/P5reset/actions)

NAME
====

Raku port of Perl's reset() built-in

SYNOPSIS
========

    use P5reset;

    reset("a");   # reset all "our" variables starting with "a"

    reset("a-z"); # reset all "our" variables starting with lowercase letter

    reset;        # does not reset any variables

DESCRIPTION
===========

This module tries to mimic the behaviour of Perl's `reset` built-in as closely as possible in the Raku Programming Language.

ORIGINAL PERL DOCUMENTATION
===========================

    reset EXPR
    reset   Generally used in a "continue" block at the end of a loop to clear
            variables and reset "??" searches so that they work again. The
            expression is interpreted as a list of single characters (hyphens
            allowed for ranges). All variables and arrays beginning with one
            of those letters are reset to their pristine state. If the
            expression is omitted, one-match searches ("?pattern?") are reset
            to match again. Only resets variables or searches in the current
            package. Always returns 1. Examples:

                reset 'X';      # reset all X variables
                reset 'a-z';    # reset lower case variables
                reset;          # just reset ?one-time? searches

            Resetting "A-Z" is not recommended because you'll wipe out your
            @ARGV and @INC arrays and your %ENV hash. Resets only package
            variables; lexical variables are unaffected, but they clean
            themselves up on scope exit anyway, so you'll probably want to use
            them instead. See "my".

PORTING CAVEATS
===============

Since Raku doesn't have the concept of `?one time searches?`, the no-argument form of `reset` will not reset any variables at all.

AUTHOR
======

Elizabeth Mattijsen <liz@raku.rocks>

If you like this module, or what I’m doing more generally, committing to a [small sponsorship](https://github.com/sponsors/lizmat/) would mean a great deal to me!

Source can be located at: https://github.com/lizmat/P5reset . Comments and Pull Requests are welcome.

COPYRIGHT AND LICENSE
=====================

Copyright 2018, 2019, 2020, 2021, 2023 Elizabeth Mattijsen

Re-imagined from Perl as part of the CPAN Butterfly Plan.

This library is free software; you can redistribute it and/or modify it under the Artistic License 2.0.

