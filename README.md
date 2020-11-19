# lvgl

This is a project written by using lvgl GUI lib.

- version:
  - lvgl: v7.7.2
  - lvgl_drivers: v7.7.2

Just `make` the project in your environment: Linux PC, raspberrypi, or something else.

# Set-up the project

### Download lvgl

`https://github.com/lvgl/lvgl`

#### Modfiy lvgl/src/lv_font/lv_font_loader.c:

error: ‘for’ loop initial declarations are only allowed in C99 mode

```
for(int i = 0;...)
=>
int i;
for(i=0;...)
```



### Download lvgl_drivers

`https://github.com/lvgl/lv_drivers`

### Download lv_port_linux_frame_buffer

`https://github.com/lvgl/lv_port_linux_frame_buffer`

#### Modify Makefile:

- Remove `-Wshift-negative-value` in CFLAGS to pass compiling on Ubuntu.
- Remove `-lSDL2` in LDFLAGS to pass compiling on RaspberryPi (other platforms without SDL2 libs as well.)

#### Remove lv_examples related:

- Remove lv_ex_conf.h
- Remove lv_example related code in main.c
- Remove lv_example related code in Makefile

