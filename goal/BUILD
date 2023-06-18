load("@rules_cc//cc:defs.bzl", "cc_library", "cc_test")

cc_binary(
    name = "wpiutil",
    srcs = select({
        "@bazel_tools//src/conditions:darwin": ["@bazelrio_edu_wpi_first_wpiutil_wpiutil-cpp_osxuniversal//:shared_libs"],
        "@bazel_tools//src/conditions:linux_x86_64": ["@bazelrio_edu_wpi_first_wpiutil_wpiutil-cpp_linuxx86-64//:shared_libs"],
    }),
    deps = [
        "@bazelrio_edu_wpi_first_wpiutil_wpiutil-cpp_headers//:headers",
    ],
    linkopts = select({
        "@bazel_tools//src/conditions:darwin": ["-install_name", "-id", "@rpath/libwpiutil.dylib", "./libwpiutil.dylib"],
        "//conditions:default": [],
    }),
    linkshared=True
)

cc_test(
    name = "test",
    srcs = ["test.cc"],
    deps = [
        ":wpiutil",
        "@googletest//:gtest_main",
    ],
)
