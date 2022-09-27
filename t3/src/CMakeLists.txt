INCLUDE_DIRECTORIES(/usr/include/hello)
ADD_EXECUTABLE(main main.c)
# 链接工程目录下的库文件
#TARGET_LINK_LIBRARIES(main hello)
TARGET_LINK_LIBRARIES(main libhello.a)
