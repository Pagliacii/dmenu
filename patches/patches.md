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

