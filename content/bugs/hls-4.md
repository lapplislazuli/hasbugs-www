
+++
author = "Ciselab / Leonhard Applis"
title = "hls-4"
date = "2023-01-25"

id = "hls-4"
categories = ['integration-test', 'rewrite', 'ordering issue']
tags = ['lsp-test', 'tasty', 'tasty-expected-failure', 'tasty-golden', 'tasty-hunit', 'tasty-rerun', 'tasty-hspec', 'hspec', 'QuickCheck', 'tasty-quickcheck', 'ghcide-test-utils']

description = "HLS can suggest import of modules for the user. These generated imports can be placed incorrect, as it may be inserted before the 'where' of a module declaration, resulting in an invalid file. This has been addressed by rewriting the import-placement. "
+++
