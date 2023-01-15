# pystupid
Some notes on Python syntax and more.
These are on topics that are or were confusing to me, an R and Fortran user, while learning Python.

# Indexing objects
The 0 index for the first element is strange enough, but at least that matches C and probably more (some reasons for that here: <https://developerinsider.co/why-does-the-indexing-of-array-start-with-zero-in-c/>).
But this "slice" behavior with numpy arrays and apparently other structures seems even stranger.

```
>>> import numpy as np
>>> x = [1, 2, 3]
>>> x[0]
1
>>> x[2]
3
```

OK, so to extract all 3 elements, I would expect:

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

More on use of colon in Python here: <https://www.askpython.com/python/examples/colon-in-python>.

# Debugging
The `breakpoint()` function is available in v3.7 and up.
It seems to work well if the script is evaluated in the shell e.g., 

```
python3 somescript.py
```

Even if somescript.py loads the function that is to be debugged from another script (i.e., `breakpoint()` is in a separate function definition script) this works.
If the work is done directly in a Python console, `breakpoint()` seems to be completely ignored.
This differs from `browser()` behavior in R.

To step through a script without using `breakpoint()`, use this in the shell:

```
python3 -m pdb somescript.py 
```

(It seems `breakpoint()` uses the pdb package anyway.)
But this will only step through the lines in somescript.py--don't try to use it to debug a function that is defined in a separate script and loaded in somescript.py.

