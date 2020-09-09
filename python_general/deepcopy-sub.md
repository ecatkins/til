Python's `copy.deepcopy` can be incredibly slow when applied to certain objects.

```
import copy
my_complex_object = MyObject()
my_copy = copy.deepcopy(my_complex_object)
```

I have found that saving a pickle of the object to disk & reloading it, can be many times faster
```
import pickle
my_complex_object = MyObject()
pickle.dump(my_complex_object, open('/tmp/loc.p', wb'))
my_copy = pickle.load(open('/tmp/loc.p', 'rb'))

```

It's pretty hacky, but effective!

