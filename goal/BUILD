load("@rules_cc//cc:defs.bzl", "cc_library", "cc_test")

cc_library(
    name = "wpiutil",
    srcs = select({
        "@bazel_tools//src/conditions:darwin": ["@bazelrio_edu_wpi_first_wpiutil_wpiutil-cpp_osxuniversal//:shared_libs"],
        "@bazel_tools//src/conditions:linux_x86_64": ["@bazelrio_edu_wpi_first_wpiutil_wpiutil-cpp_linuxx86-64//:shared_libs"],
    }),
    linkstatic = True,
    deps = [
        "@bazelrio_edu_wpi_first_wpiutil_wpiutil-cpp_headers//:headers",
    ],
)

cc_library(
    name = "wpinet",
    srcs = select({
        "@bazel_tools//src/conditions:darwin": ["@bazelrio_edu_wpi_first_wpinet_wpinet-cpp_osxuniversal//:shared_libs"],
        "@bazel_tools//src/conditions:linux_x86_64": ["@bazelrio_edu_wpi_first_wpinet_wpinet-cpp_linuxx86-64//:shared_libs"],
    }),
    linkstatic = True,
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
