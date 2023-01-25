
+++
author = "Ciselab / Leonhard Applis"
title = "cabal-5"
date = "2023-01-25"

id = "cabal-5"
categories = ['logic', 'refactoring', 'golden-test', 'system-test']
tags = ['QuickCheck', 'tasty', 'tasty-quickcheck', 'Cabal-QuickCheck', 'tasty-hunit', 'tasty-golden', 'tasty-expected-failure']

description = "When initialising a project with the '--no-comments' flag, cabal fields that would normally be commented out still had comments in front of them. Expected behaviour is that comments are not present in front of any fields, commented out or not. Solution is to always remove comments when the '--no-comments' flag is set."
+++
