
+++
author = "Ciselab / Leonhard Applis"
title = "hledger-2"
date = "2023-01-25"

id = "hledger-2"
categories = ['integration-test', 'div-by-0', 'restructuring']
tags = ['doctest', 'tasty', 'tasty-hunit', 'hspec', 'yesod-test']

description = "In HLegder, users can get accumulated information of their financial accounts. Specifically with ROI, when iterating over the elements of an account, the elements where not checked to be zero before division. The fix is to filter (heading) zeroes."
+++
