package(default_visibility = ["//visibility:public"])

licenses(["notice"])

load("@io_bazel_rules_go//go:def.bzl", "go_prefix", "go_library", "go_test")

go_prefix("istio.io/mixer/pkg/aspect/listChecker")

ISTIO_DEPS = [
    "//:mixer/v1",
    "//:mixer/v1/config",
    "//:mixer/v1/config/aspect",
]

DEPS = [
    "//pkg/aspect:go_default_library",
    "//pkg/aspect/listChecker:go_default_library",
    "//pkg/aspectsupport:go_default_library",
    "@com_github_golang_protobuf//proto:go_default_library",
    "@com_github_google_go_genproto//googleapis/rpc/code:go_default_library",
    "//pkg/attribute:go_default_library",
    "//pkg/expr:go_default_library",
] + ["@com_github_istio_api" + d for d in ISTIO_DEPS]

SRCS = glob(
    include = ["*.go"],
    exclude = ["*_test.go"],
)

go_library(
    name = "go_default_library",
    srcs = SRCS,
    deps = DEPS,
)

go_test(
    name = "manager_test",
    size = "small",
    srcs = ["manager_test.go"],
    library = ":go_default_library",
)
