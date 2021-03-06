# ******************************************************************************
# Copyright 2017-2020 Intel Corporation
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
# ******************************************************************************

set(LIBS
    mlir_backend
    MLIROptLib
    MLIRPass
    MLIRParser
    LLVMSupport
)

add_executable(ngraph-opt
    ngraph_opt.cpp
)

target_link_libraries(ngraph-opt PRIVATE ${LIBS})

set_target_properties(ngraph-opt PROPERTIES
                      RUNTIME_OUTPUT_DIRECTORY_DEBUG ${NGRAPH_BUILD_BIN}
                      RUNTIME_OUTPUT_DIRECTORY_RELEASE ${NGRAPH_BUILD_BIN}
)

install(TARGETS ngraph-opt RUNTIME DESTINATION ${NGRAPH_INSTALL_BIN})
