load("@rules_cc//cc:defs.bzl", "cc_import", "cc_test")

cc_import(
    name = "wpiutil",
    shared_library = select({
        "@bazel_tools//src/conditions:darwin": "libwpiutil.dylib",
        "@bazel_tools//src/conditions:linux_x86_64": "libwpiutil.so",
    }),
    deps = [
        "@bazelrio_edu_wpi_first_wpiutil_wpiutil-cpp_headers//:headers",
    ],
    linkopts = select({
        "@bazel_tools//src/conditions:darwin": ["-install_name -id @rpath/libwpiutil.dylib libwpiutil.dylib"],
        "//conditions:default": [],
    })
)

cc_test(
    name = "test",
    srcs = ["test.cc"],
    deps = [
        ":wpiutil",
        "@googletest//:gtest_main",
    ],
)
