package(default_visibility = ["//visibility:public"])

load("//bazel:envoy_build_system.bzl", "envoy_cc_library")

envoy_cc_library(
    name = "configuration_lib",
    srcs = ["configuration_impl.cc"],
    hdrs = ["configuration_impl.h"],
    deps = [
        "//include/envoy/http:filter_includes",
        "//include/envoy/network:connection_includes",
        "//include/envoy/network:filter_includes",
        "//include/envoy/runtime:runtime_includes",
        "//include/envoy/server:configuration_includes",
        "//include/envoy/server:instance_includes",
        "//include/envoy/ssl:context_manager_includes",
        "//source/common/common:logger_lib",
        "//source/common/common:utility_lib",
        "//source/common/json:config_schemas_lib",
        "//source/common/json:json_loader_lib",
        "//source/common/network:utility_lib",
        "//source/common/ratelimit:ratelimit_lib",
        "//source/common/ssl:context_config_lib",
        "//source/common/tracing:http_tracer_lib",
        "//source/common/upstream:cluster_manager_lib",
    ],
)

envoy_cc_library(
    name = "connection_handler_lib",
    srcs = ["connection_handler_impl.cc"],
    hdrs = ["connection_handler_impl.h"],
    deps = [
        "//include/envoy/api:api_includes",
        "//include/envoy/common:time_includes",
        "//include/envoy/event:deferred_deletable",
        "//include/envoy/event:dispatcher_includes",
        "//include/envoy/event:timer_includes",
        "//include/envoy/network:connection_handler_includes",
        "//include/envoy/network:connection_includes",
        "//include/envoy/network:filter_includes",
        "//include/envoy/network:listen_socket_includes",
        "//include/envoy/network:listener_includes",
        "//source/common/common:linked_object",
        "//source/common/common:non_copyable",
        "//source/common/event:dispatcher_lib_includes",
        "//source/common/network:listen_socket_lib",
        "//source/common/network:listener_lib",
    ],
)

envoy_cc_library(
    name = "drain_manager_lib",
    srcs = ["drain_manager_impl.cc"],
    hdrs = ["drain_manager_impl.h"],
    deps = [
        "//include/envoy/event:dispatcher_includes",
        "//include/envoy/event:timer_includes",
        "//include/envoy/runtime:runtime_includes",
        "//include/envoy/server:drain_manager_includes",
        "//include/envoy/server:instance_includes",
        "//source/common/common:assert_lib",
        "//source/common/common:logger_lib",
    ],
)

envoy_cc_library(
    name = "guarddog_lib",
    srcs = ["guarddog_impl.cc"],
    hdrs = ["guarddog_impl.h"],
    deps = [
        ":watchdog_lib",
        "//include/envoy/event:dispatcher_includes",
        "//include/envoy/server:configuration_includes",
        "//include/envoy/server:guarddog_includes",
        "//include/envoy/server:watchdog_includes",
        "//include/envoy/stats:stats_includes",
        "//source/common/common:assert_lib",
        "//source/common/common:logger_lib",
        "//source/common/common:thread_lib",
        "//source/common/event:libevent_lib",
    ],
)

envoy_cc_library(
    name = "options_lib",
    srcs = ["options_impl.cc"],
    hdrs = ["options_impl.h"],
    external_deps = ["tclap"],
    deps = [
        "//:version_generated",
        "//include/envoy/server:options_includes",
        "//source/common/common:macros",
        "//source/common/common:version_lib",
    ],
)

envoy_cc_library(
    name = "server_lib",
    srcs = ["server.cc"],
    hdrs = ["server.h"],
    deps = [
        ":configuration_lib",
        ":connection_handler_lib",
        ":test_hooks_lib",
        ":worker_lib",
        "//:version_generated",
        "//include/envoy/common:optional_includes",
        "//include/envoy/event:dispatcher_includes",
        "//include/envoy/event:signal_includes",
        "//include/envoy/event:timer_includes",
        "//include/envoy/network:dns_includes",
        "//include/envoy/network:listener_includes",
        "//include/envoy/server:drain_manager_includes",
        "//include/envoy/server:instance_includes",
        "//include/envoy/server:options_includes",
        "//include/envoy/ssl:context_manager_includes",
        "//include/envoy/stats:stats_macros",
        "//include/envoy/tracing:http_tracer_includes",
        "//include/envoy/upstream:cluster_manager_includes",
        "//source/common/access_log:access_log_manager_lib",
        "//source/common/api:api_lib",
        "//source/common/common:utility_lib",
        "//source/common/common:version_lib",
        "//source/common/json:config_schemas_lib",
        "//source/common/memory:stats_lib",
        "//source/common/network:utility_lib",
        "//source/common/runtime:runtime_lib",
        "//source/common/ssl:context_lib",
        "//source/common/stats:statsd_lib",
        "//source/common/thread_local:thread_local_lib",
        "//source/server/http:admin_lib",
    ],
)

envoy_cc_library(
    name = "test_hooks_lib",
    hdrs = ["test_hooks.h"],
)

envoy_cc_library(
    name = "watchdog_lib",
    srcs = ["watchdog_impl.cc"],
    hdrs = ["watchdog_impl.h"],
    deps = [
        "//include/envoy/common:time_includes",
        "//include/envoy/event:dispatcher_includes",
        "//include/envoy/server:watchdog_includes",
        "//source/common/common:assert_lib",
    ],
)

envoy_cc_library(
    name = "worker_lib",
    srcs = ["worker.cc"],
    hdrs = ["worker.h"],
    deps = [
        ":connection_handler_lib",
        ":guarddog_lib",
        "//include/envoy/event:dispatcher_includes",
        "//include/envoy/event:timer_includes",
        "//include/envoy/server:configuration_includes",
        "//include/envoy/thread_local:thread_local_includes",
        "//source/common/api:api_lib",
        "//source/common/common:thread_lib",
        "//source/common/network:listen_socket_lib",
    ],
)