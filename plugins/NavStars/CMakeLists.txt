SET(NS_MAJOR 0)
SET(NS_MINOR 2)
SET(NS_PATCH 3)
SET(NS_VERSION "${NS_MAJOR}.${NS_MINOR}.${NS_PATCH}")

IF(APPLE)
     SET(CMAKE_INSTALL_PREFIX $ENV{HOME}/Library/Application\ Support/Stellarium)
ElSE(APPLE)
     SET(CMAKE_INSTALL_PREFIX $ENV{HOME}/.stellarium)
ENDIF(APPLE)

ADD_DEFINITIONS(-DNAVSTARS_PLUGIN_VERSION="${NS_VERSION}")
ADD_DEFINITIONS(-DNAVSTARS_PLUGIN_LICENSE="GNU GPLv2+")

ADD_SUBDIRECTORY( src )

INSTALL(FILES DESTINATION "modules/NavStars")
