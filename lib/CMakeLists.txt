# For more information about using CMake with Android Studio, read the
# documentation: https://d.android.com/studio/projects/add-native-code.html

# Sets the minimum version of CMake required to build the native library.

cmake_minimum_required(VERSION 3.4.1)

# Creates and names a library, sets it as either STATIC
# or SHARED, and provides the relative paths to its source code.
# You can define multiple libraries, and CMake builds them for you.
# Gradle automatically packages shared libraries with your APK.

add_library(# Sets the name of the library.
            rtmp-srv-jni

            # Sets the library as a shared library.
            SHARED

            # Provides a relative path to your source file(s).
            src/main/cpp/native-lib.cpp
            src/main/cpp/ngx_rtmp.c
            src/main/cpp/ngx_rtmp.h
            src/main/cpp/ngx_rtmp_access_module.c
            src/main/cpp/ngx_rtmp_amf.c
            src/main/cpp/ngx_rtmp_amf.h
            src/main/cpp/ngx_rtmp_auto_push_module.c
            src/main/cpp/ngx_rtmp_bandwidth.c
            src/main/cpp/ngx_rtmp_bandwidth.h
            src/main/cpp/ngx_rtmp_bitop.c
            src/main/cpp/ngx_rtmp_bitop.h
            src/main/cpp/ngx_rtmp_cmd_module.c
            src/main/cpp/ngx_rtmp_cmd_module.h
            src/main/cpp/ngx_rtmp_codec_module.c
            src/main/cpp/ngx_rtmp_codec_module.h
            src/main/cpp/ngx_rtmp_control_module.c
            src/main/cpp/ngx_rtmp_core_module.c
            src/main/cpp/ngx_rtmp_eval.c
            src/main/cpp/ngx_rtmp_eval.h
            src/main/cpp/ngx_rtmp_exec_module.c
            src/main/cpp/ngx_rtmp_flv_module.c
            src/main/cpp/ngx_rtmp_handler.c
            src/main/cpp/ngx_rtmp_handshake.c
            src/main/cpp/ngx_rtmp_init.c
            src/main/cpp/ngx_rtmp_limit_module.c
            src/main/cpp/ngx_rtmp_live_module.c
            src/main/cpp/ngx_rtmp_live_module.h
            src/main/cpp/ngx_rtmp_log_module.c
            src/main/cpp/ngx_rtmp_mp4_module.c
            src/main/cpp/ngx_rtmp_netcall_module.c
            src/main/cpp/ngx_rtmp_netcall_module.h
            src/main/cpp/ngx_rtmp_notify_module.c
            src/main/cpp/ngx_rtmp_play_module.c
            src/main/cpp/ngx_rtmp_play_module.h
            src/main/cpp/ngx_rtmp_proxy_protocol.c
            src/main/cpp/ngx_rtmp_proxy_protocol.h
            src/main/cpp/ngx_rtmp_receive.c
            src/main/cpp/ngx_rtmp_record_module.c
            src/main/cpp/ngx_rtmp_record_module.h
            src/main/cpp/ngx_rtmp_relay_module.c
            src/main/cpp/ngx_rtmp_relay_module.h
            src/main/cpp/ngx_rtmp_send.c
            src/main/cpp/ngx_rtmp_shared.c
            src/main/cpp/ngx_rtmp_stat_module.c
            src/main/cpp/ngx_rtmp_streams.h
            src/main/cpp/ngx_rtmp_version.h
            )

# Searches for a specified prebuilt library and stores the path as a
# variable. Because CMake includes system libraries in the search path by
# default, you only need to specify the name of the public NDK library
# you want to add. CMake verifies that the library exists before
# completing its build.

find_library( # Sets the name of the path variable.
              log-lib

              # Specifies the name of the NDK library that
              # you want CMake to locate.
              log )

# Specifies libraries CMake should link to your target library. You
# can link multiple libraries, such as libraries you define in this
# build script, prebuilt third-party libraries, or system libraries.

target_link_libraries( # Specifies the target library.
                       rtmp-srv-jni

                       # Links the target library to the log library
                       # included in the NDK.
                       ${log-lib} )