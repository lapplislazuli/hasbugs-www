
+++
author = "Ciselab / Leonhard Applis"
title = "cabal-6"
date = "2023-01-25"

id = "cabal-6"
categories = ['concurrency', 'file-management', 'system-test']
tags = ['QuickCheck', 'tasty', 'tasty-quickcheck', 'Cabal-QuickCheck', 'tasty-hunit', 'tasty-golden', 'tasty-expected-failure']

description = "Multiple concurrent builds would sometimes give an error similar to 'ghc-pkg: cannot create: /home/edsko/path/to/main-package/dist-newstyle/packagedb/ghc-7.10.3 already exists' because packagedbs would be made at the same time. The solution is to initialise packagedbs at the start of the build process rather than when needed."
+++
