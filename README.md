    1、这是cartographer_ws工作空间的src中的3个包，分别是cartographer、cartographer_ros、ceres-solver-1.13.0

    2、以上代码我修改了如下部分：
    cartographer/CMakeLists.txt，修改第55行。 用 /usr/src/googletest/googlemock 替代 /usr/src/gmock。
    3、原因：
    google的gmock和gtest 从 1.7.0-4升级到 1.8.0-2后，就开始出现这个问题了：/usr/src/googletest/googletest/cmake/internal_utils.cmake处的 CMake 错误：149 (add_library)：add_library无法创建目标“gmock”，因为已存在另一个同名目标。我们按照几年前的博客（关于cartographer安装编译） 操作会报错，原因可能就是这里。

