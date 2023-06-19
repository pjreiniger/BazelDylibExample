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
        "@bazel_tools//src/conditions:darwin": ["-Wl,-install_name,@rpath/libwpiutil.dylib"],
        "//conditions:default": [],
    }),
)

cc_import(
    name = "wpinet",
    shared_library = select({
        "@bazel_tools//src/conditions:darwin": "libwpinet.dylib",
        "@bazel_tools//src/conditions:linux_x86_64": "libwpinet.so",
    }),
    deps = [
        ":wpiutil",
        "@bazelrio_edu_wpi_first_wpinet_wpinet-cpp_headers//:headers",
    ],
    linkopts = select({
        "@bazel_tools//src/conditions:darwin": [
            "-Wl,-install_name,@rpath/libwpiutil.dylib",
            "-Wl,-install_name,@rpath/libwpinet.dylib",
        ],
        "//conditions:default": [],
    }),
)

cc_test(
    name = "wpiutil_test",
    srcs = ["wpiutil_test.cc"],
    linkopts = select({
        "@bazel_tools//src/conditions:darwin": ["-Wl,-install_name,@rpath/libwpiutil.dylib"],
        "//conditions:default": [],
    }),
    deps = [
        ":wpiutil",
        "@googletest//:gtest_main",
    ],
)

cc_test(
    name = "wpinet_test",
    srcs = ["wpinet_test.cc"],
    linkopts = select({
        "@bazel_tools//src/conditions:darwin": [
            "-Wl,-install_name,@rpath/libwpiutil.dylib",
            "-Wl,-install_name,@rpath/libwpinet.dylib",
        ],
        "//conditions:default": [],
    }),
    deps = [
        ":wpinet",
        "@googletest//:gtest_main",
    ],
)
