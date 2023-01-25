
+++
author = "Ciselab / Leonhard Applis"
title = "hls-2"
date = "2023-01-25"

id = "hls-2"
categories = ['string-manipulation', 'off-by-one', 'path-handling', 'integration-test']
tags = ['lsp-test', 'tasty', 'tasty-expected-failure', 'tasty-golden', 'tasty-hunit', 'tasty-rerun', 'tasty-hspec', 'hspec', 'QuickCheck', 'tasty-quickcheck', 'ghcide-test-utils']

description = "HLS utilizes cabal features, in this case the definition of addition source directories. These directories must be specified as strings where the first character of a suggested module name is dropped if 'hs-source-dirs' is assigned simply as './' ('.' was expected). Fix is to canonicalise the path to always include the '/' and then trim it."
+++
