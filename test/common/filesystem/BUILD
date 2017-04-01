package(default_visibility = ["//visibility:public"])

load("//bazel:envoy_build_system.bzl", "envoy_cc_test")

envoy_cc_test(
    name = "filesystem_impl_test",
    srcs = ["filesystem_impl_test.cc"],
    deps = [
        "//source/common/common:thread_lib",
        "//source/common/event:dispatcher_lib",
        "//source/common/event:dispatcher_lib_includes",
        "//source/common/filesystem:filesystem_lib",
        "//source/common/stats:stats_lib",
        "//test/mocks/event:event_mocks",
        "//test/mocks/filesystem:filesystem_mocks",
        "//test/test_common:environment_lib",
    ],
)

envoy_cc_test(
    name = "watcher_impl_test",
    srcs = ["watcher_impl_test.cc"],
    deps = [
        "//source/common/common:assert_lib",
        "//source/common/event:dispatcher_lib",
        "//source/common/event:dispatcher_lib_includes",
        "//source/common/filesystem:watcher_lib",
        "//test/test_common:environment_lib",
    ],
)