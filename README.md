# Modified flag package from the Go stdlib

I needed to be able to get at the raw tokens, and also allow specifying a token that has an optional parameter, eg.

    $ mycommand -m "Some string"

or

    $ mycommand -m

Also allows for the argument terminator to be used:

    $ mycommand -s something --otherflag=something else -- --this-will-not-get-interpreted-as-a-flag

Adds two new fields to FlagSet:

    flagsTerminatorSeen bool
    Tokens              []string

and one to the Flag struct:

    WasProvided bool   // Was the flag provided on the command line, value or not

## Authors

Mostly the original authors of the flag package, the modifications by @wjessop (will@willj.net)

## License

Distributed under the same license as the flag package in stdlib:

    Copyright 2009 The Go Authors. All rights reserved.
    Use of this source code is governed by a BSD-style
    license that can be found in the LICENSE file.

## TODO

Get the test suite working. My modifications work in practice, but I've not updated the test suite.
