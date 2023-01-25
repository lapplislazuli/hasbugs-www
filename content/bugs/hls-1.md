
+++
author = "Ciselab / Leonhard Applis"
title = "hls-1"
date = "2023-01-25"

id = "hls-1"
categories = ['integration-test', 'data-model', 'refactoring', 'design decision']
tags = ['lsp-test', 'tasty', 'tasty-expected-failure', 'tasty-golden', 'tasty-hunit', 'tasty-rerun', 'tasty-hspec', 'hspec', 'QuickCheck', 'tasty-quickcheck', 'ghcide-test-utils']

description = "In Haskell you can pun-records, which means to access field variables in a breviated way. When records are punned, there is a reference from pun to field declaration and from pun-name-use to pun-declaration, but no transitive reference. Meaning refactoring did not propagate to the latter. Solution is a second pass to find indirect pun-references and rename those as well."
+++
