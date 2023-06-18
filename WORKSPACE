load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "googletest",
    sha256 = "24564e3b712d3eb30ac9a85d92f7d720f60cc0173730ac166f27dda7fed76cb2",
    strip_prefix = "googletest-release-1.12.1",
    urls = ["https://github.com/google/googletest/archive/release-1.12.1.zip"],
)

HEADERS_BUILD_FILE = """cc_library(
    name = "headers",
    hdrs = glob(["**"]),
    includes = ["."],
    visibility = ["//visibility:public"],
)
"""

SHARED_LIBRARY_BUILD_FILE = """filegroup(
    name = "shared_libs",
    srcs = glob([
        "**/*.dll", 
        "**/*.so*", 
        "**/*.dylib",
    ], exclude=[
        "**/*.jni.dylib",
        "**/lib*_java*.dylib",
    ]),
    visibility = ["//visibility:public"],
)"""

# wpiutil
http_archive(
    name = "bazelrio_edu_wpi_first_wpiutil_wpiutil-cpp_headers",
    build_file_content = HEADERS_BUILD_FILE,
    sha256 = "4fb3ccb42fe750ccbacb7bf1d8d39ddee60e87b801d0ffb3c4a44ba32924d131",
    url = "https://frcmaven.wpi.edu/release/edu/wpi/first/wpiutil/wpiutil-cpp/2023.3.2/wpiutil-cpp-2023.3.2-headers.zip",
)

http_archive(
    name = "bazelrio_edu_wpi_first_wpiutil_wpiutil-cpp_linuxx86-64",
    url = "https://frcmaven.wpi.edu/release/edu/wpi/first/wpiutil/wpiutil-cpp/2023.3.2/wpiutil-cpp-2023.3.2-linuxx86-64.zip",
    sha256 = "1bb33b1d081c7be991bd874e3c9154a16dd0f55501bd33ad0aef638529af8f97",
    build_file_content = SHARED_LIBRARY_BUILD_FILE,
)

http_archive(
    name = "bazelrio_edu_wpi_first_wpiutil_wpiutil-cpp_osxuniversal",
    url = "https://frcmaven.wpi.edu/release/edu/wpi/first/wpiutil/wpiutil-cpp/2023.3.2/wpiutil-cpp-2023.3.2-osxuniversal.zip",
    sha256 = "1f7568fdbeb0cd00940f0e15b051095811ce7db4e2a46a4bc2ef652b81bea463",
    build_file_content = SHARED_LIBRARY_BUILD_FILE,
)


# OpenCV
http_archive(
    name = "bazelrio_edu_wpi_first_thirdparty_frc_opencv_opencv-cpp_headers",
    build_file_content = HEADERS_BUILD_FILE,
    sha256 = "69c9693c87c620d4b07b93f322f21e813ba9ce0ad16604709c8b373774422736",
    url = "https://frcmaven.wpi.edu/release/edu/wpi/first/thirdparty/frc2023/opencv/opencv-cpp/4.6.0-4/opencv-cpp-4.6.0-4-headers.zip",
)

http_archive(
    name = "bazelrio_edu_wpi_first_thirdparty_frc_opencv_opencv-cpp_linuxx86-64",
    build_file_content = SHARED_LIBRARY_BUILD_FILE,
    sha256 = "1024fa62ad0b6b894c37ad92142061fc8c7dffcebae3d6076c871a25475f9486",
    url = "https://frcmaven.wpi.edu/release/edu/wpi/first/thirdparty/frc2023/opencv/opencv-cpp/4.6.0-4/opencv-cpp-4.6.0-4-linuxx86-64.zip",
)

http_archive(
    name = "bazelrio_edu_wpi_first_thirdparty_frc_opencv_opencv-cpp_osxuniversal",
    build_file_content = SHARED_LIBRARY_BUILD_FILE,
    sha256 = "4cf8bbf6760bebf474bee18a57d40e9d83c6888bac1abe1669116cc603b01e5b",
    url = "https://frcmaven.wpi.edu/release/edu/wpi/first/thirdparty/frc2023/opencv/opencv-cpp/4.6.0-4/opencv-cpp-4.6.0-4-osxuniversal.zip",
)
