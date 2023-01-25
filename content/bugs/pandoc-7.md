
+++
author = "Ciselab / Leonhard Applis"
title = "pandoc-7"
date = "2023-01-25"

id = "pandoc-7"
categories = ['parsing', 'data-loss', 'unit-test']
tags = ['tasty', 'tasty-golden', 'tasty-hunit', 'tasty-quickcheck']

description = "Empty table cells were filtered out when reading LaTeX tables without handling multirows and multicols properly. By adding code for recognising multicols and rows correctly, empty cells can now be filtered without shifting other cells out of place."
+++
