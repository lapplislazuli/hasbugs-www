
+++
author = "Ciselab / Leonhard Applis"
title = "pandoc-3"
date = "2023-01-11"

id = "pandoc-3"
categories = ['integration-test', 'golden-test']
tags = ['tasty', 'tasty-golden', 'tasty-hunit', 'tasty-quickcheck']

description = "When multiple paragraphs were present under a single list item, DOCXs would annotate each paragraph with the list item number, but should instead only annotate the first. Fix is to add a marker that is set when the first annotation is done and checked on every subsequent annotation."
+++
