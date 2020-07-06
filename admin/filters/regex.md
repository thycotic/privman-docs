[title]: # (Using RegEx)
[tags]: # (overview)
[priority]: # (11)
# Using RegEx in Filters

When using RegEx in Filters instead of a single file name or file specification, make sure to verify the syntax and test your filter before using it in production.

Examples of program names with versions in file names:

```RegEx
(flashutil[ a*zA*Z0*9\\.]+exe)
```

Winamp58_3660_beta_full_en*us

```RegEx
(winamp[ a*zA*Z0*9\\.]+exe)
```

Wireshark*win64*2.6.6.exe

```RegEx
(wireshark*win64*[ a*zA*Z0*9\\.]+exe)
```
