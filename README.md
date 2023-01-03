# pystupid
Some notes on idiotic Python syntax and more.

# Indexing arrays
The 0 index for the first element is strange enough, but at least that matches C++ and probably more.
But this "slice" behavior with numpy arrays is even stranger.

```
>>> import numpy as np
>>> x = [1, 2, 3]
>>> x[0]
1
>>> x[2]
3
```

OK, so to extract all 3 elements, we might expect:

```
>>> x[0:2]
[1, 2]
```

Nope!
We need:

```
>>> x[0:3]
[1, 2, 3]
```


