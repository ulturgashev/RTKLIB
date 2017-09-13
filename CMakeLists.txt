CMAKE_MINIMUM_REQUIRED(VERSION 2.8.11)

IF(POLICY CMP0043)
    CMAKE_POLICY(SET CMP0043 OLD)
ENDIF()

PROJECT(rtklib)

ADD_DEFINITIONS(-DENAGLO)

SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wall -O3")

INCLUDE_DIRECTORIES(${CMAKE_SOURCE_DIR}/src)
INCLUDE_DIRECTORIES(${CMAKE_SOURCE_DIR}/src/rcv)

SET(SOURCES
    src/convkml.c
    src/convrnx.c
    src/datum.c
    src/download.c
    src/ephemeris.c
    src/geoid.c
    src/ionex.c
    src/lambda.c
    src/options.c
    src/pntpos.c
    src/postpos.c
    src/ppp.c
    src/ppp_ar.c
    src/preceph.c
    src/qzslex.c
    src/rcvraw.c
    src/rinex.c
    src/rtcm.c
    src/rtcm2.c
    src/rtcm3.c
    src/rtcm3e.c
    src/rtkcmn.c
    src/rtkpos.c
    src/rtksvr.c
    src/sbas.c
    src/solution.c
    src/stream.c
    src/streamsvr.c
    src/tle.c

    src/rcv/binex.c
    src/rcv/crescent.c
    src/rcv/gw10.c
    src/rcv/javad.c
    src/rcv/novatel.c
    src/rcv/nvs.c
    src/rcv/rcvlex.c
    src/rcv/rt17.c
    src/rcv/septentrio.c
    src/rcv/skytraq.c
    src/rcv/ss2.c
    src/rcv/ublox.c
)

SET(HEADERS
    src/rtklib.h
)

ADD_LIBRARY(
    ${PROJECT_NAME}
    SHARED
    ${HEADERS}
    ${SOURCES}
)
