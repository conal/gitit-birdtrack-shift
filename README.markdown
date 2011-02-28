# Purpose

This [Haskell](http://haskell.org)-based project is a simple [gitit](http://gitit.net/) plugin that adds a leading space to lines that start with '<' followed by a non-space character.
The result is that those lines can be treated as HTML instead of an inverse bird track.
I use inverse birdtracks a lot, e.g, for formal specifications, equational derivations & proofs, and quoting definitions imported from elsewhere.

I've learned to be careful about adding an initial blank space to lines that begin with HTML tags (e.g., `<!-- HTML comments -->` and `<div>...</div>` tags), so that they're not treated as Haskell code, but it's a bother, and sometimes I forget.

# How to use

Compile the project with `cabal install gitit-birdtrack-shift` (or just `cabal install` if you've already downloaded the source and are in its main directory).
Then add it to your gitit plugins list.
For instance, my wiki's `config` file contains the following line:

    plugins: Network.Gitit.Plugin.BirdtrackShift

You can list additional plugins.  Separate by commas.

Finally, restart your gitit wiki, e.g.,

    gitit -f config

If everything works, the start-up messages will include the following:

    Loading plugin 'Network.Gitit.Plugin.BirdtrackShift'...
    Finished loading plugins.

