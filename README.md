# Notes

## Bash / Linux ##

### SCP ###

Copies files from one place to another. Consider using rsync instead which has support for resuming partial uploads, but not available (easily) on Windows.

From local to remote:

```
scp -l 4200 /c/Users/eliot/path/to/file username@ip-or-host:/path/on/remote
```

The `-l` flag limits the rate of transfer in Kbit/s otherwise you will saturate your network upload and break the internet. A value of around 4000 (500 KB/s) is reasonable for a slowish home router.

From remote to local just reverse the arguments:

```
scp username@ip-or-host:/path/on/remote /c/Users/eliot/path/to/file
```

## CSS ##

### Grid column content exceeds grid width ###

If the grid content exceeds its parent width you need to specify a min-width for the row or column. See https://css-tricks.com/preventing-a-grid-blowout/.

Not this:

```
  grid-template-columns: 1fr 300px;
```

Do this instead:

```
grid-template-columns: minmax(0, 1fr) 300px;
```
