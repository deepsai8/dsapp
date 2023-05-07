```markmap
# Root

## Branch 1

* Branchlet 1a
* Branchlet 1b

## Branch 2

* Branchlet 2a
* Branchlet 2b
```

```markmap
---
markmap:
  colorFreezeLevel: 2
#   initialExpandLevel: 2
#   color: '#2980b9'
  maxWidth: 1000
  embedAssets: true
  extraJs:
    - katex/dist/contrib/mhchem.min.js
---

# markmap

## Links

- <https://markmap.js.org/>
- [GitHub](https://github.com/gera2ld/markmap)
- NYC Taxi and Limo Commission
- [Sentimeter](https://tinyurl.com/senti-meter)
- <https://tinyurl.com/senti-meter>

## Related Projects

- [coc-markmap](https://github.com/gera2ld/coc-markmap)
- [gatsby-remark-markmap](https://github.com/gera2ld/gatsby-remark-markmap)

## Features

- links
- **strong** ~~del~~ *italic* ==highlight==
- multiline
  text
- `inline code`
-
    ```js
    console.log('code block');
    ```
- 
    ```python
    import numpy as np
    import pandas as pd

    pd.read_csv('https://github.com/deepsai8/mindmap/data/basics.csv')

    ```
- Katex
  - $x = {-b \pm \sqrt{b^2-4ac} \over 2a}$
  - $\ce{N2 + 3H2 ->[Fe] 2NH3}$
  - [More Katex Examples](#?d=gist:af76a4c245b302206b16aec503dbe07b:katex.md)
- Now we can wrap very very very very long text based on `maxWidth` option
```