load("@rules_foreign_cc//foreign_cc:defs.bzl", "cmake")

filegroup(
  name = "all_srcs",
  srcs = glob(["**"]),
  visibility = ["//visibility:public"]
)

cmake(
  name = "turbo_jpeg",
  lib_source = ":all_srcs",
  out_static_libs = [
    "libjpeg.a",
    "libturbojpeg.a",
  ],
  out_shared_libs = [
    "libjpeg.dylib",
    "libturbojpeg.dylib",
  ],
)

