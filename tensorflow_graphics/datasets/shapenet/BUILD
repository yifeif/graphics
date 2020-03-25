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
# google internal package dependency 8
load("//production/dependency/rpc/testing/hermetic:build_defs.bzl", "py2and3_hermetic_test")

licenses(["notice"])  # Apache 2.0

package(default_visibility = ["//visibility:public"])

py_library(
    name = "shapenet",
    srcs = ["__init__.py"],
    deps = [
        ":shapenet_dataset",
    ],
)

py_library(
    name = "shapenet_dataset",
    srcs = ["shapenet.py"],
    data = [
        ":checksums",
    ],
    deps = [
        # google internal package dependency 1,
        # google internal package dependency 5,
        "//tensorflow_graphics/datasets/features",
    ],
)

py2and3_hermetic_test(
    name = "shapenet_test",
    srcs = ["shapenet_test.py"],
    data = [
        ":fake_examples",
    ],
    deps = [
        ":shapenet_dataset",
        # google internal package dependency 5,
    ],
)

filegroup(
    name = "fake_examples",
    srcs = glob([
        "fakes/**",
    ]),
)

filegroup(
    name = "checksums",
    srcs = glob([
        "checksums/*",
    ]),
)
