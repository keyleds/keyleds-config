# Keyleds -- Gaming keyboard tool
# Copyright (C) 2017 Julien Hartmann, juli1.hartmann@gmail.com
#
# This program is free software: you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation, either version 3 of the License, or
# (at your option) any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program.  If not, see <http://www.gnu.org/licenses/>.

cmake_minimum_required (VERSION 3.0)
project (keyleds-config LANGUAGES CXX)

##############################################################################
# Settings

include(GNUInstallDirs)

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY "${PROJECT_BINARY_DIR}/lib")
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY "${PROJECT_BINARY_DIR}/lib")
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${PROJECT_BINARY_DIR}/bin")

add_compile_options(-Wall -Wextra -Werror
                    -Wcast-align -Wcast-qual -Wold-style-cast
                    -Wconversion -Wsign-conversion -Wshadow -Wstrict-overflow=3)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)

##############################################################################
# Global dependencies

find_package(Qt5 COMPONENTS Core Widgets REQUIRED)


##############################################################################
# Include subprojects

add_executable(${PROJECT_NAME}
    src/main.cxx
)
target_link_libraries(${PROJECT_NAME} Qt5::Core Qt5::Widgets)
