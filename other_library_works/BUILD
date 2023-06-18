load("@rules_cc//cc:defs.bzl", "cc_library", "cc_test")

cc_library(
    name = "opencv",
    srcs = select({
        "@bazel_tools//src/conditions:darwin": ["@bazelrio_edu_wpi_first_thirdparty_frc_opencv_opencv-cpp_osxuniversal//:shared_libs"],
        "@bazel_tools//src/conditions:linux_x86_64": ["@bazelrio_edu_wpi_first_thirdparty_frc_opencv_opencv-cpp_linuxx86-64//:shared_libs"],
    }),
    deps = [
        "@bazelrio_edu_wpi_first_thirdparty_frc_opencv_opencv-cpp_headers//:headers",
    ],
)

cc_test(
    name = "test",
    srcs = ["test.cc"],
    deps = [
        ":opencv",
        "@googletest//:gtest_main",
    ],
)
