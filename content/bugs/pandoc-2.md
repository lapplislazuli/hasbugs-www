
+++
author = "Ciselab / Leonhard Applis"
title = "pandoc-2"
date = "2023-01-25"

id = "pandoc-2"
categories = ['integration-test', 'missed case', 'feature-collision']
tags = ['tasty', 'tasty-golden', 'tasty-hunit', 'tasty-quickcheck']

description = "When a file was rendered into DOCX with two tables in them, the space between them would be deleted when there was some comment block in-between.The comment should be ignored and a paragraph should be inserted for spacing."
+++
