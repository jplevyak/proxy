# Copyright 2017 Istio Authors. All Rights Reserved.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0

# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

licenses(["notice"])

cc_library(
    name = "control_lib",
    srcs = [
        "attributes_builder.cc",
        "attributes_builder.h",
        "client_context.cc",
        "client_context.h",
        "controller_impl.cc",
        "controller_impl.h",
        "request_handler_impl.cc",
        "request_handler_impl.h",
        "service_context.cc",
        "service_context.h",
    ],
    visibility = ["//visibility:public"],
    deps = [
        "//include/istio/control/http:headers_lib",
        "//include/istio/utils:attribute_names_header",
        "//src/istio/authn:context_proto_cc_proto",
        "//src/istio/control:common_lib",
        "//src/istio/utils:attribute_names_lib",
        "//src/istio/utils:utils_lib",
    ],
)

cc_library(
    name = "mock_headers",
    hdrs = [
        "mock_check_data.h",
        "mock_report_data.h",
    ],
    visibility = ["//visibility:public"],
)

cc_test(
    name = "attributes_builder_test",
    size = "small",
    srcs = [
        "attributes_builder_test.cc",
    ],
    linkstatic = 1,
    deps = [
        ":control_lib",
        ":mock_headers",
        "//external:googletest_main",
    ],
)

cc_test(
    name = "request_handler_impl_test",
    size = "small",
    srcs = [
        "request_handler_impl_test.cc",
    ],
    linkstatic = 1,
    deps = [
        ":control_lib",
        ":mock_headers",
        "//external:googletest_main",
        "//src/istio/control:mock_mixer_client",
    ],
)
