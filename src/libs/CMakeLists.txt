find_package(Curses REQUIRED)
include_directories(${CURSES_INCLUDE_DIR})

add_library(display display.c)
target_link_libraries(display ${CURSES_LIBRARIES})

add_library(compress compress.c)

find_package(CARES REQUIRED)
#include_directories(${CARES_INCLUDE_DIR})
include_directories(/opt/local/include)

add_library(nameres nameres.c)
target_link_libraries(nameres ${CARES_LIBRARIES})

find_package(OpenSSL REQUIRED)
find_package(CRYPTO)
add_library(crypto crypto.c)
target_link_libraries(crypto ${OPENSSL_LIBRARIES} ${CRYPTO_LIBRARIES})

add_library(fec fec.c)
add_library(crc crc.c)