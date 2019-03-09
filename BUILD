load("@io_bazel_rules_docker//go:image.bzl", "go_image")
load("@io_bazel_rules_go//go:def.bzl", "go_binary", "go_library")

go_library(
    deps = ["@org_golang_google_grpc//:go_default_library"],
    importpath = "github.com/obeattie/poc-bazel-690",
    name = "go_default_library",
    srcs = ["main.go"],
    visibility = ["//visibility:public"],
)

go_binary(
    embed = [":go_default_library"],
    name = "bazel-poc-690",
    out = "bazel-poc-690",
    visibility = ["//visibility:public"],
)

go_image(
    embed = [":go_default_library"],
    goarch = "amd64",
    goos = "linux",
    name = "image",
    pure = "on",
    visibility = ["//visibility:public"],
)