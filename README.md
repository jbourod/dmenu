# Jorge's dmenu
My custom dmenu build

## Features
### Fuzzy search
By default, dmenu will apply fuzzy matching on the input elements (can be disabled with the -F flag). The following patches are applied for this functionality:
* [fuzzymatch](https://tools.suckless.org/dmenu/patches/fuzzymatch/) (v 4.9)
* [fuzzyhighlight](https://tools.suckless.org/dmenu/patches/fuzzyhighlight/) (v 4.9)

    In order to make it fully integrated with the fuzzymatch patch, the following line in dmenu.c should be changed:
        
        if (*highlight == text[i]) {

    into:

        if (!fstrncmp(&(*highlight), &text[i], 1)) {

### Center on the screen
Using the -c flag, dmenu will appear centered on the current screen. The following patches are applied for this functionality:
* [center](https://tools.suckless.org/dmenu/patches/center/) (v 20200111-8cd37e1)

### Set a border
Using the -bw x flag, dmenu will appear with a border around of width x. The following patches are applied for this functionality:
* [border](https://tools.suckless.org/dmenu/patches/border/) (v 20201112-1a13d04)
