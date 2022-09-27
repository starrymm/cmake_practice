SET(SRC_LIST hello.c)
ADD_LIBRARY(hello SHARED ${SRC_LIST})
ADD_LIBRARY(hello_static STATIC ${SRC_LIST})
# 设置输出的名称
SET_TARGET_PROPERTIES(hello_static PROPERTIES OUTPUT_NAME "hello")

# set dynmaic lib version
SET_TARGET_PROPERTIES(hello PROPERTIES VERSION 1.2 SOVERSION 1)



# 静态库和动态库 安装在 ${perfix}/lib
INSTALL(TARGETS hello hello_static
    LIBRARY DESTINATION lib
    ARCHIVE DESTINATION lib
)

# hello.h 安装在 ${perfix}/include/hello/
INSTALL(FILES hello.h DESTINATION include/hello)
