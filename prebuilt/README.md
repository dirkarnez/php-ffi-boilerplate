Prebuilt
========
### [ffi.so](ffi.so) (tested on php 8)
How to build
- No need, just copy from `docker run -it --rm -p 81:80 -v "%cd%:/home" rechtlogisch/php-with-ffi:8.0-cli`

References
- [PHP: FFI - Manual](https://www.php.net/manual/en/class.ffi.php)
- [PHP FFI详解 - 一种全新的PHP扩展方式 - 风雪之隅](https://www.laruence.com/2020/03/11/5475.html)
- [gabrielrcouto/awesome-php-ffi: PHP FFI examples and use cases](https://github.com/gabrielrcouto/awesome-php-ffi)
- [dstogov/php-ffi: PHP Foreign Function Interface](https://github.com/dstogov/php-ffi)
- [dev-blog/让PHP能够调用C的函数-FFI扩展.php at master · zhangyue0503/dev-blog](https://github.com/zhangyue0503/dev-blog/blob/master/php/202004/source/%E8%AE%A9PHP%E8%83%BD%E5%A4%9F%E8%B0%83%E7%94%A8C%E7%9A%84%E5%87%BD%E6%95%B0-FFI%E6%89%A9%E5%B1%95.php)

### [libcalculator_library.so](libcalculator_library.so) (for testing only, tested on php 8)
How to build
- Using the `calculator` submodule in this boilerplate project

How to use
- ```php
  <?php
    $ffiCalculator = FFI::cdef(
      "int Calculator_Add(int n1, int n2);", // this is a regular C declaration
      dirname(__FILE__) . "/../modules/libcalculator_library.so"); // any location you like which you put this .so
    
    echo $ffiCalculator->Calculator_Add(9, 8);
  ?>
  ```
