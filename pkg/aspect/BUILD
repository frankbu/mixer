package(default_visibility = ["//visibility:public"])

load("@io_bazel_rules_go//go:def.bzl", "go_prefix", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "aspect.go",
        "configError.go",
    ],
    deps = [
        "@com_github_golang_protobuf//proto:go_default_library",
        "@com_github_google_go_genproto//googleapis/rpc/code:go_default_library",
        "@com_github_hashicorp_go_multierror//:go_default_library",
    ],
)

go_test(
    name = "config_error_test",
    size = "small",
    srcs = ["configError_test.go"],
    library = ":go_default_library",
)
