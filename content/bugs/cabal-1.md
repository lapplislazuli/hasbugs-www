
+++
author = "Ciselab / Leonhard Applis"
title = "cabal-1"
date = "2023-01-25"

id = "cabal-1"
categories = ['system-test', 'os', 'multi-threading', 'multi-processing']
tags = ['QuickCheck', 'tasty', 'tasty-quickcheck', 'Cabal-QuickCheck', 'tasty-hunit', 'tasty-golden', 'tasty-expected-failure']

description = "Cabal starts multiple processes to build a project. 'cabal run' termination does not terminate all child processes automatically as well. The solution is to use 'withCreateProcess' rather than 'createProcess' and throw an asynchronous exception from the main thread when a termination is wanted."
+++
