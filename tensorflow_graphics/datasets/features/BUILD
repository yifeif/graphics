#Copyright 2019 Google LLC
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#    https://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
load("//production/dependency/rpc/testing/hermetic:build_defs.bzl", "py2and3_hermetic_test")

licenses(["notice"])  # Apache 2.0

package(
    default_visibility = ["//visibility:public"],
)

py_library(
    name = "features",
    srcs = ["__init__.py"],
    deps = [
        ":trimesh_feature",
    ],
)

py_library(
    name = "trimesh_feature",
    srcs = ["trimesh_feature.py"],
    deps = [
        # google internal package dependency 6
        "//third_party/py/six",
        # google internal package dependency 1,
        # google internal package dependency 5,
        "//tensorflow_graphics/io:triangle_mesh",
        "//third_party/py/trimesh",
    ],
)

py2and3_hermetic_test(
    name = "trimesh_feature_test",
    srcs = ["trimesh_feature_test.py"],
    data = [
        "//tensorflow_graphics/datasets/features/test_data",
    ],
    deps = [
        ":trimesh_feature",
        # google internal package dependency 6
        # google internal package dependency 1,
        # google internal package dependency 5,
        "//third_party/py/trimesh",
    ],
)
