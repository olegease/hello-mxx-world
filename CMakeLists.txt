cmake_minimum_required( VERSION 3.30...4.3 FATAL_ERROR )
# experimental import std
if( CMAKE_VERSION VERSION_LESS 3.31 )
   set( CMAKE_EXPERIMENTAL_CXX_IMPORT_STD "0e5b6991-d74f-4b3d-a41c-cf096e0b2508" )
elseif( CMAKE_VERSION VERSION_LESS 4.3 )
   set( CMAKE_EXPERIMENTAL_CXX_IMPORT_STD "d0edc3af-4c50-42ea-a356-e2862fe7a444" )
else( )
   set( CMAKE_EXPERIMENTAL_CXX_IMPORT_STD "451f2fe2-a8a2-47c3-bc32-94786d8fc91b" )
endif( )
project( hello_mxx_world VERSION 0.0.0 LANGUAGES CXX )
set( app ${PROJECT_NAME} )
# private configuration under source directory
add_subdirectory( source )

# GNU Affero General Public License v3.0 or later
# NO WARRANTY OF ANY KIND more details at <https://www.gnu.org/licenses/>
# SPDX-License-Identifier: AGPL-3.0-or-later
# app: `hello-mxx-world` C++23 Hello Standard Modules Exemplar
# Ⓒ Copyright (C) 2026 Oleg'Ease'Kharchuk ᦒ
