
+++
author = "Ciselab / Leonhard Applis"
title = "hls-2"
date = "2023-01-11"

id = "hls-2"
categories = ['off-by-one', 'path-trimming', 'integration-test']
tags = ['lsp-test', 'tasty', 'tasty-expected-failure', 'tasty-golden', 'tasty-hunit', 'tasty-rerun', 'tasty-hspec', 'hspec', 'QuickCheck', 'tasty-quickcheck', 'ghcide-test-utils']

description = "First character of a suggested module name is dropped when 'hs-source-dirs' is assigned simply as './' ('.' was expected). Fix is to canonicalise the path to always include the '/' and then trim it. (The PR also adds cleaner logging for debugging)"
+++
