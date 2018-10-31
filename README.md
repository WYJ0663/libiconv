# libiconv
编译libiconv


下载地址 https://ftp.gnu.org/pub/gnu/libiconv/

# 1、再Ubuntu执行  ./configure  
# 2、配置cmake
# 3、修改所有#define HAVE_LANGINFO_CODESET 0 不然会报Error:(403) undefined reference to 'nl_langinfo'    


# build/intermediates/cmake/debug/obj/${ANDROID_ABI}/libiconv.so
# 使用

 add_library( iconv_lib
           SHARED
           IMPORTED )

  set_target_properties( # Specifies the target library.
                         iconv_lib

                         # Specifies the parameter you want to define.
                         PROPERTIES IMPORTED_LOCATION

                         # Provides the path to the library you want to import.
                         ${PROJECT_SOURCE_DIR}/src/main/cpp/iconv/${ANDROID_ABI}/libiconv.so )

  target_link_libraries(TKAT PRIVATE iconv_lib)
