php-ffi-boilerplate
===================
To dynamically call foreign functions in php

1. Download prebuilt `.so` or build with this project, then place it to `extension_dir`
2. Add the following to local / global php.ini (check server setup first to see which fits, local php.ini is prefered)
    ```
    extension_dir=/www/modules
    ffi.enable=true
    extension=ffi.so
    ```
3. Restart / reload php-fpm process
4. Refer to [/prebuilt/README.md](/prebuilt/README.md)
