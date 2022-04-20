# Some snippets for saving/restoring sessions

Here's the table of contents:

1. TOC
{:toc}

## Using pickle

```
import pickle
def is_picklable(obj):
    try:
        pickle.dumps(obj)
    except Exception:
        return False
    return True

import pickle

bk = {}
for k in dir():
    i = k;
    if(i[0] != "_" and "var_" in i):
        obj = globals()[k]
        if is_picklable(obj):
            try:
                bk.update({k: obj})
            except TypeError:
                pass
                
# to save session
with open('./session/your_bk.pkl', 'wb') as f:
    pickle.dump(bk, f)  
    
# to load your session

with open('./session/your_bk.pkl', 'rb') as f:
    bk_restore = pickle.load(f)
    
for k in bk_restore:
    globals()[k] = bk_restore[k]
```

## Using dill

```
import dill

dill.dump_session('./your_bk_dill.pkl')
#to restore session:
dill.load_session('./your_bk_dill.pkl')
```

[See!](https://medium.com/swlh/python-for-datascientist-quick-backup-for-everything-6d201a7e935d)







