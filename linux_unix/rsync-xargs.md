Speed up rsync with parallelization using xargs

```
SOURCE_DIR=/my/dir/
REMOTE_DIR=remote@my-remote:/my/dir/
ls $SOURCE_DIR | xargs -n1 -P4 -I% rsync -Pa $SOURCE_DIR% $REMOTE_DIR

```

Adapted from this [StackOverflow answer](https://stackoverflow.com/a/25532027/5125275)
