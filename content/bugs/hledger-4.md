
+++
author = "Ciselab / Leonhard Applis"
title = "hledger-4"
date = "2023-01-25"

id = "hledger-4"
categories = ['integration-test', 'feature-collision', 'data-inconsistency']
tags = ['doctest', 'tasty', 'tasty-hunit', 'hspec', 'yesod-test']

description = "Hledger supports transactions with up to 1 'empty posting' (= no monetary amount). The option 'auto' can add another empty posting, which can result in faulty 2-empty-posting transactions. As a fix, 'auto' generated postings are non-empty by default."
+++
