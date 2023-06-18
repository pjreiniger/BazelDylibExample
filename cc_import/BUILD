load("@rules_cc//cc:defs.bzl", "cc_import", "cc_test")

cc_import(
    name = "wpiutil_import",
    shared_library = select({
        "@bazel_tools//src/conditions:darwin": "libwpiutil.dylib",
        "@bazel_tools//src/conditions:linux_x86_64": "libwpiutil.so",
    }),
    deps = [
        "@bazelrio_edu_wpi_first_wpiutil_wpiutil-cpp_headers//:headers",
    ],
    alwayslink=1,
)

cc_library(
    name = "wpiutil",
    linkopts = select({
        "@bazel_tools//src/conditions:darwin": ["-Wl,-install_name,@rpath/libwpiutil.dylib"],
        "//conditions:default": [],
    }),
    deps = [":wpiutil_import"],
)

cc_test(
    name = "test",
    srcs = ["test.cc"],
    deps = [
        ":wpiutil",
        "@googletest//:gtest_main",
    ],
)
