# FreeRDP: A Remote Desktop Protocol Client
# FreeRDP cmake build script
#
# Copyright 2011 O.S. Systems Software Ltda.
# Copyright 2011 Otavio Salvador <otavio@ossystems.com.br>
# Copyright 2011 Marc-Andre Moreau <marcandre.moreau@gmail.com>
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

set(XRDPVR_ALSA_SRCS
	xrdpvr_alsa.c
)

include_directories(..)
include_directories(${ALSA_INCLUDE_DIRS})

add_library(xrdpvr_alsa ${XRDPVR_ALSA_SRCS})
set_target_properties(xrdpvr_alsa PROPERTIES PREFIX "")

target_link_libraries(xrdpvr_alsa freerdp-utils)
target_link_libraries(xrdpvr_alsa ${ALSA_LIBRARIES})

install(TARGETS xrdpvr_alsa DESTINATION ${FREERDP_PLUGIN_PATH})

