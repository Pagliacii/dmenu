# dmenu

dmenu is a dynamic menu for X, originally designed for [dwm](https://dwm.suckless.org). It manages large numbers of user-defined menu items efficiently.

## Patches

For instructions on how to submit and format patches, take a look at the [hacking guidelines](https://suckless.org/hacking).

**Usage**:

```shell
# in dmenu folder
$ patch < patches/<patch file>
$ rm -f config.h
$ sudo make clean install
```

### border

**Description**: This patch adds a border around the dmenu window. It is intended to be used with the center or xyw patches, to make the menu stand out from similarly coloured windows.

**File**: `patches/dmenu-border-4.9.diff`

![border patch](https://tools.suckless.org/dmenu/patches/border/dmenu_border.png)

### center

**Description**: This patch centers dmenu in the middle of the screen. With `dmenu-center-20191105-f1ca0d0.diff`, you can use *-c* to center dmenu.

**File**: `patches/dmenu-center-20191105-f1ca0d0.diff`

### fuzzymatch

**Description**: This patch adds support for fuzz-matching to dmenu, allowing users to type non-consecutive portions of the string to be matched. Adds the option *fuzzy* to `config.def.h` and the flag *-F* to dmenu which enable to turn fuzzy-matching on and off.

**File**: `patches/dmenu-fuzzymatch-4.9.diff`

**Note**:

+ Supports dmenu's case insensitive switch (-i)
+ This patch enables fuzzy-matching as default, and use the flag *-F* to turn off it. You can change this by modify these codes:

```c
// change fuzzy to 0 to disable fuzzy-matching as default, in config.def.h
static int fuzzy = 0;
// change fuzzy to 1 to enable fuzzy-matching by the flag -F, in dmenu.c
else if (!strcmp(argv[i], "-F"))
        fuzzy = 1;
```

