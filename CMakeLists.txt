cmake_minimum_required(VERSION 2.8.4)
project(plog)

include_directories("./include")
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_HOME_DIRECTORY}/lib)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

#set(CMAKE_CXX_COMPILER "/opt/local/bin/g++-mp-4.9")
#set(CMAKE_CC_COMPILER "/opt/local/bin/gcc-mp-4.9")

set(HEADER_FILES
  include/plog/Init.h
  include/plog/Log.h
  include/plog/Logger.h
  include/plog/Record.h
  include/plog/Severity.h
  include/plog/Util.h
  include/plog/Appenders/AndroidAppender.h
  include/plog/Appenders/ColorConsoleAppender.h
  include/plog/Appenders/ConsoleAppender.h
  include/plog/Appenders/DebugOutputAppender.h
  include/plog/Appenders/EventLogAppender.h
  include/plog/Appenders/IAppender.h
  include/plog/Appenders/RollingFileAppender.h
  include/plog/Converters/UTF8Converter.h
  include/plog/Formatters/CsvFormatter.h
  include/plog/Formatters/FuncMessageFormatter.h
  include/plog/Formatters/TxtFormatter.h
  )

add_library(plog SHARED ${HEADER_FILES} ${SOURCE_FILES})
set_target_properties(plog PROPERTIES LINKER_LANGUAGE CXX)
