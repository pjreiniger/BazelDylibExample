load("@rules_cc//cc:defs.bzl", "cc_library", "cc_test")

cc_library(
    name = "wpiutil",
    srcs = select({
        "@bazel_tools//src/conditions:darwin": ["libwpiutil.dylib"],
        "@bazel_tools//src/conditions:linux_x86_64": ["libwpiutil.so"],
    }),
    deps = [
        "@bazelrio_edu_wpi_first_wpiutil_wpiutil-cpp_headers//:headers",
    ],
)

cc_library(
    name = "wpinet",
    srcs = select({
        "@bazel_tools//src/conditions:darwin": ["libwpinet.dylib"],
        "@bazel_tools//src/conditions:linux_x86_64": ["libwpinet.so"],
    }),
    deps = [
        ":wpiutil",
        "@bazelrio_edu_wpi_first_wpinet_wpinet-cpp_headers//:headers",
    ],
)

cc_test(
    name = "wpiutil_test",
    srcs = ["wpiutil_test.cc"],
    deps = [
        ":wpiutil",
        "@googletest//:gtest_main",
    ],
)

cc_test(
    name = "wpinet_test",
    srcs = ["wpinet_test.cc"],
    deps = [
        ":wpinet",
        "@googletest//:gtest_main",
    ],
)
