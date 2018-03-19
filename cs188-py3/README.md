### Berkeley cs188 - Introduction to AI
#### Python 3

This python 3 compatible version of Berkeley's cs188 course came from\
 https://github.com/lbarasti/Intro-to-AI-Python-3. Some files were missing,\
 however, so I am converting and moving them into the main repo as I come across\
 them.

Relevant resources for converting files:



#### Error 1:
-----

For error where:

```
from game import GameStateData
  File "./cs188/cs188-py3/src/game.py", line 582
    print("Agent %d failed to load" % i, file=sys.stderr)
                                             ^
SyntaxError: invalid syntax
```

[solution](https://stackoverflow.com/a/14981125/3450793)
```
from __future__ import print_function
import sys

def eprint(*args, **kwargs):
    print(*args, file=sys.stderr, **kwargs)
```


#### Error 2:

For errors pertaining to `tkinter`:

[solution](https://stackoverflow.com/questions/7714229/tkinter-woes-when-porting-2-x-code-to-3-x-tkinter-module-attribute-doesnt-ex)


#### Error 3:

For `raise` errors where:

```
RefactoringTool: Line 333: could not convert: raise  'incomprehensible coordinates'
RefactoringTool: Python 3 does not support string exceptions
```

Search using regex:

```
raise  (\'.*\')
```

Replace:

```
raise EnvironmentError($1)
```
