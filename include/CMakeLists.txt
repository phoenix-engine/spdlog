add_library(SpdLog INTERFACE)

target_include_directories(
  SpdLog
  INTERFACE
  ${CMAKE_CURRENT_LIST_DIR}/
)

file(GLOB_RECURSE SpdLog_HEADERS
  LIST_DIRECTORIES true
  ${CMAKE_CURRENT_LIST_DIR}/spdlog/*.h
)

target_sources(
  SpdLog
  INTERFACE
  ${SpdLog_HEADERS}
)

if("${CMAKE_GENERATOR}" STREQUAL "Xcode")
  add_custom_target(SpdLogHeaders SOURCES ${SpdLog_HEADERS})
endif()
