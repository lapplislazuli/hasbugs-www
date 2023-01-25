
+++
author = "Ciselab / Leonhard Applis"
title = "pandoc-1"
date = "2023-01-25"

id = "pandoc-1"
categories = ['integration-test', 'missed case', 'default value']
tags = ['tasty', 'tasty-golden', 'tasty-hunit', 'tasty-quickcheck']

description = "Docbook Files support linked figures, which should be convertable to other formats. DocBooks xref elements can link to figures, but the text inserted for the title of the link would be 'figure_title'(default placeholder) rather than the title of the figure. The fix is to add the 'title' attribute and use the title if available."
+++
