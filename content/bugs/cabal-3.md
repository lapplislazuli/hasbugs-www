
+++
author = "Ciselab / Leonhard Applis"
title = "cabal-3"
date = "2023-01-25"

id = "cabal-3"
categories = ['parsing', 'whitespace', 'system-test']
tags = ['QuickCheck', 'tasty', 'tasty-quickcheck', 'Cabal-QuickCheck', 'tasty-hunit', 'tasty-golden', 'tasty-expected-failure']

description = "Cabal provides and parses it's own configuration file. The used method 'cabal HEAD' is confused by trailing whitespaces in 'default-language' tags. The solution is to fix parsing by changing 'some anyChar' to 'munch1 isAlphaNum'. This way, only characters are parsed into a language."
+++
