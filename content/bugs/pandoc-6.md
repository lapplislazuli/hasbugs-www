
+++
author = "Ciselab / Leonhard Applis"
title = "pandoc-6"
date = "2023-01-25"

id = "pandoc-6"
categories = ['parsing', 'unit-test']
tags = ['tasty', 'tasty-golden', 'tasty-hunit', 'tasty-quickcheck']

description = "Inline Markdown code-blocks had a slight parsing/priority problem. Code blocks with '(1)' in them would be wrongly delimited. The fix is to reorder parsing steps to account for lists inner-nested."
+++
