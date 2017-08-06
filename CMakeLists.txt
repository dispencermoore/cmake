
cmake_minimum_required(VERSION 2.8 FATAL_ERROR)
SET(sampleName MyApp)
find_package(PCL 1.2 REQUIRED)
FIND_PACKAGE(MRPT REQUIRED base;bayes;obs;gui)
include_directories(${PCL_INCLUDE_DIRS})
include_directories("G:/Matlab/extern/include")
include_directories("C:/Program Files/MobileRobots/Aria/include")
link_directories(${PCL_LIBRARY_DIRS})
link_directories("G:/Matlab/extern/lib/win32/microsoft")
link_directories("C:/Program Files/MobileRobots/Aria/lib")
add_definitions(${PCL_DEFINITIONS})
add_executable (MyApp Local.cpp part.h grab.h interface.h test.cpp test.h)
target_link_libraries (MyApp ${PCL_LIBRARIES} libeng.lib libmx.lib libmex.lib libmat.lib Aria.lib winmm.lib wsock32.lib)
TARGET_LINK_LIBRARIES(${sampleName}
${MRPT_LIBS} # This is filled by FIND_PACKAGE(MRPT ...)
""
)
