
+++
author = "Ciselab / Leonhard Applis"
title = "cabal-4"
date = "2023-01-25"

id = "cabal-4"
categories = ['missing-cases', 'system-test']
tags = ['QuickCheck', 'tasty', 'tasty-quickcheck', 'Cabal-QuickCheck', 'tasty-hunit', 'tasty-golden', 'tasty-expected-failure']

description = "Cabal supports a dry-run-feature, which runs a subset of the specified commands.The '--dry-run' did not actually dry-run for commands 'v2-configure', 'v2-freeze', 'v2-run', and 'v2-exec'. Instead, the dry-run flag was ignored and the commands did perform a few actions. The fix is to add if-expressions where needed in the commands' code to perform the dry-run as expected."
+++
