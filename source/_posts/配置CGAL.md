---
title: 配置CGAL
date: 2022-10-28 18:51:17
categories: cgal
tags: [cgal, cmake]
urlname: cgal-configuration
---
## 前言
这里记录一下CGAL的配置过程

## 下载CGAL包
[CGAL-5.5.1.zip](https://github.com/CGAL/cgal/releases/download/v5.5.1/CGAL-5.5.1.zip)
解压到路径：\CGAL-5.5.1

## 下载GMP和MPFR

[GMP and MPFR libraries, for Windows 64bits](https://github.com/CGAL/cgal/releases/download/v5.5.1/CGAL-5.5.1-win64-auxiliary-libraries-gmp-mpfr.zip)
解压到CGAL下auxiliary里：\CGAL-5.5.1\auxiliary\gmp

## 下载boost
[boost_1_71_0-msvc-14.2-64.exe](https://sourceforge.net/projects/boost/files/boost-binaries/1.71.0/boost_1_71_0-msvc-14.2-64.exe/download)
解压到路径：\boost_1_71_0
并添加两个环境变量：
* BOOST_LIBRARYDIR = \boost_1_71_0\lib64-msvc-14.2
* BOOST_INCLUDEDIR = \boost_1_71_0

再将路径`\boost_1_71_0\lib64-msvc-14.2`添加到PATH中，

## 创建cmake项目
用vs2019创建cmake项目，CMakeLists.txt如下：
```cmake
cmake_minimum_required(VERSION 3.1...3.23)
project( test_cgal )

find_package(CGAL)

add_executable( test_cgal "CGAL.cpp" )

target_link_libraries(test_cgal CGAL::CGAL)
```
CMakeSettings.json如下：

```json
{
  "configurations": [
    {
      "name": "x64-Release",
      "generator": "Ninja",
      "configurationType": "RelWithDebInfo",
      "buildRoot": "${projectDir}\\build\\${name}",
      "installRoot": "${projectDir}\\install\\${name}",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "",
      "ctestCommandArgs": "",
      "inheritEnvironments": [ "msvc_x64_x64" ],
      "variables": [
        {
          "name": "CGAL_DIR",
          "value": "E:/Work/vs2019Work/Third_Party/CGAL-5.5.1",
          "type": "PATH"
        }
      ]
    }
  ]
}
```

然后就可以用cmake和CGAL愉快地玩耍了=v=


