load("@rules_cc//cc:defs.bzl", "cc_library", "cc_test")

cc_test(
    name = "wpiutil_test",
    srcs = ["wpiutil_test.cc"],
    deps = [
        "//goal:wpiutil",
        "@googletest//:gtest_main",
    ],
)

cc_test(
    name = "wpinet_test",
    srcs = ["wpinet_test.cc"],
    deps = [
        "//goal:wpinet",
        "@googletest//:gtest_main",
    ],
)
