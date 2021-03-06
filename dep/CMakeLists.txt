# Copyright (C) 2008-2016 TrinityCore <http://www.trinitycore.org/>
#
# This file is free software; as a special exception the author gives
# unlimited permission to copy and/or distribute it, with or without
# modifications, as long as this notice is preserved.
#
# This program is distributed in the hope that it will be useful, but
# WITHOUT ANY WARRANTY, to the extent permitted by law; without even the
# implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.

if( MSVC )
  add_definitions(/W0)
else()
  add_definitions(-w)
endif()

add_subdirectory(threads)

if(SERVERS OR TOOLS)
  add_subdirectory(boost)
  add_subdirectory(zlib)
  add_subdirectory(g3dlite)
  add_subdirectory(recastnavigation)
  add_subdirectory(jemalloc)
  add_subdirectory(cppformat)
  add_subdirectory(SFMT)
  add_subdirectory(utf8cpp)
  add_subdirectory(valgrind)
  add_subdirectory(openssl)
endif()

if(SERVERS)
  add_subdirectory(mysql)
  add_subdirectory(process)
  add_subdirectory(readline)
  add_subdirectory(gsoap)
  add_subdirectory(rapidjson)
endif()

if(TOOLS)
  add_subdirectory(bzip2)
  add_subdirectory(CascLib)
endif()
