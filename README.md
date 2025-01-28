## Readme
The following repo contains the keymap files that are located in
`~/qmk_firmware/keyboards/lily58/keymaps/my-lily-keymap`

## Setup and flashing

### Check if qmk is ready
``` bash
qmk doctor
```

### 1. Visit [qmk configurator](https://config.qmk.fm/#/sofle/) and make your layouts!
Then donwload the keymap.json file

### 2. Compile the keymap.json you downloaded from qmk configurator
``` bash
# the following command will generate a keymap.c file in 
# ~/qmk_firmware/.build/obj_lily58_rev1_my_lily58_rev1_keymap/src/
qmk compile layout.json
```

### 3. Create a new keymap if you don't already have one
``` bash
qmk new-keymap -kb lily58/rev1
# and give it a name like my-lily-keymap
```

### 4. Update rules.mk
``` bash
# Add the following in
#  ~/qmk_firmware/keyboards/lily58/keymaps/my-lily-keymap/rules.mk
MOUSEKEY_ENABLE = yes
EXTRAKEY_ENABLE = yes
BOOTLOADER = caterina
```

### 5. Update keymap.c
replace the default `keymap.c` in `~/qmk_firmware/keyboards/lily58/keymaps/my-lily-keymap` with the one that you built manually in `~/qmk_firmware/.build/obj_lily58_rev1_my_lily58_rev1_keymap/src/`

### 6. Compile & flash
``` bash
qmk compile -kb lily58/rev1 -km my-lily-keymap   
qmk flash -kb lily58/rev1 -km my-lily-keymap   
# connect one side of the keyboard and hit the reset button
# then repeat for the other side
```

