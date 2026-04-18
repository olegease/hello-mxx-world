set( CMAKE_CXX_STANDARD 23 )
set( CMAKE_CXX_STANDARD_REQUIRED ON )
set( CMAKE_CXX_EXTENSIONS OFF )
set( CMAKE_CXX_MODULE_STD ON )
# library
set( APP_FACE_EXT ".ixx" )
set( APP_IMPL_EXT ".mxx" )

file ( GLOB_RECURSE APP_FACE CONFIGURE_DEPENDS "${CMAKE_CURRENT_SOURCE_DIR}/*${APP_FACE_EXT}" )
file ( GLOB_RECURSE APP_IMPL CONFIGURE_DEPENDS "${CMAKE_CURRENT_SOURCE_DIR}/*${APP_IMPL_EXT}" )

set_source_files_properties( ${APP_FACE} PROPERTIES LANGUAGE CXX )
set_source_files_properties( ${APP_IMPL} PROPERTIES LANGUAGE CXX )

add_library( hello.world )
target_sources( hello.world
   PUBLIC FILE_SET CXX_MODULES FILES ${APP_FACE}
   PRIVATE ${APP_IMPL}
)
# application
add_executable( ${app} main.cxx )
target_link_libraries( ${app} PRIVATE hello.world )

# GNU Affero General Public License v3.0 or later
# NO WARRANTY OF ANY KIND more details at <https://www.gnu.org/licenses/>
# SPDX-License-Identifier: AGPL-3.0-or-later
# app: `hello-mxx-world` C++23 Hello Standard Modules Exemplar
# Ⓒ Copyright (C) 2026 Oleg'Ease'Kharchuk ᦒ
