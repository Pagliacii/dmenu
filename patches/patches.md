# Patches

All patches could be found at this [link](https://tools.suckless.org/dmenu/patches/).

## Usage

```shell
# in dmenu folder
$ patch < patches/<patch file>
$ rm -f config.h
$ sudo make clean install
```

## border

**File**: `dmenu-border-4.9.diff`

### Description

This patch adds a border around the dmenu window. It is intended to be used with the center or xyw patches, to make the menu stand out from similarly coloured windows.

### Authors

+ Leon Plickat [leonhenrik.plickat@stud.uni-goettingen.de](mailto:leonhenrik.plickat@stud.uni-goettingen.de)

![border patch](https://tools.suckless.org/dmenu/patches/border/dmenu_border.png)

## center

**File**: `dmenu-center-20191105-f1ca0d0.diff`

### Description

This patch centers dmenu in the middle of the screen. With `dmenu-center-20191105-f1ca0d0.diff`, you can use *-c* to center dmenu.

### Authors

+ Ed van Bruggen [edvb@uw.edu](mailto:edvb@uw.edu)
+ Nihal Jere [nihal@nihal.jere.xyz](mailto:nihal@nihal.jere.xyz) (20191105)

### fuzzymatch

**File**: `dmenu-fuzzymatch-4.9.diff`

### Description

This patch adds support for fuzz-matching to dmenu, allowing users to type non-consecutive portions of the string to be matched. Adds the option *fuzzy* to `config.def.h` and the flag *-F* to dmenu which enable to turn fuzzy-matching on and off.

### Authors

+ Jan Christoph Ebersbach [jceb@e-jc.de](mailto:jceb@e-jc.de)
+ Laslo Hunhold [dev@frign.de](mailto:dev@frign.de) (dmenu-4.6)
+ Aleksandrs Stier (4.9)

### Note

+ Supports dmenu's case insensitive switch (-i)
+ This patch enables fuzzy-matching as default, and use the flag *-F* to turn off it. You can change this by modify these codes:

```c
// change fuzzy to 0 to disable fuzzy-matching as default, in config.def.h
static int fuzzy = 0;
// change fuzzy to 1 to enable fuzzy-matching by the flag -F, in dmenu.c
else if (!strcmp(argv[i], "-F"))
        fuzzy = 1;
```

## Instant Mode

**File**: `dmenu-instant-4.7.diff`

### Description

Adds an flag which will cause dmenu to select an item immediately if theres one matching option left.

### Authors

+ Michael Stummvoll (stummi) [suckless@stummi.org](mailto:suckless@stummi.org)

## Line height

**File**: `dmenu-lineheight-4.9.diff`

### Description

The patch adds a *-h* option, which sets the minimum height of a dmenu line. This helps integrate dmenu with other UI elements that require a particular vertical size.

### Authors

+ Xarchus
+ Jonathon Fernyhough (jonathon at manjaro-dot-org) (4.7 rewrite)
+ Aleksandrs Stier (4.9 port)

![with '-h 24'](http://tools.suckless.org/dmenu/patches/line-height/dmenu-line-height.png)

