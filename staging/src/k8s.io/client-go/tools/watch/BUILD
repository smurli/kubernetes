load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = ["until.go"],
    importmap = "k8s.io/kubernetes/vendor/k8s.io/client-go/tools/watch",
    importpath = "k8s.io/client-go/tools/watch",
    visibility = ["//visibility:public"],
    deps = [
        "//staging/src/k8s.io/apimachinery/pkg/util/wait:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/watch:go_default_library",
        "//vendor/github.com/golang/glog:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = ["until_test.go"],
    embed = [":go_default_library"],
    deps = [
        "//staging/src/k8s.io/apimachinery/pkg/runtime:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/runtime/schema:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/util/wait:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/watch:go_default_library",
    ],
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [":package-srcs"],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
