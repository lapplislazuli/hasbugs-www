+++
author = "Leonhard Applis"
title = "cabal-1"
date = "2023-01-03"
id = "cabal-1"

description = "'cabal run' termination does not terminate all child processes automatically as well. The solution is to use 'withCreateProcess' rather than 'createProcess' and throw an asynchronous exception from the main thread when a termination is wanted."
+++
