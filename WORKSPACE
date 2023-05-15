load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "bazel_skylib",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/bazel-skylib/releases/download/1.3.0/bazel-skylib-1.3.0.tar.gz",
        "https://github.com/bazelbuild/bazel-skylib/releases/download/1.3.0/bazel-skylib-1.3.0.tar.gz",
    ],
    sha256 = "74d544d96f4a5bb630d465ca8bbcfe231e3594e5aae57e1edbf17a6eb3ca2506",
)

http_archive(
    name = "aspect_bazel_lib",
    sha256 = "b4cd1114874ab15f794134eefbc254eb89d3e1de640bf4a11f2f402e886ad29e",
    strip_prefix = "bazel-lib-1.27.2",
    url = "https://github.com/aspect-build/bazel-lib/releases/download/v1.27.2/bazel-lib-v1.27.2.tar.gz",
)


http_archive(
    name = "rules_nodejs",
    sha256 = "40b56e18c38295425381644f4d4efebccb5c704ac313f8baf88d047a3a6b4ab3",
    urls = ["https://github.com/bazelbuild/rules_nodejs/releases/download/5.7.2/rules_nodejs-core-5.7.2.tar.gz"],
)

http_archive(
    name = "aspect_rules_js",
    sha256 = "dcd1567d4a93a8634ec0b888b371a60b93c18d980f77dace02eb176531a71fcf",
    strip_prefix = "rules_js-1.26.0",
    url = "https://github.com/aspect-build/rules_js/releases/download/v1.26.0/rules_js-v1.26.0.tar.gz",
)

load("@aspect_rules_js//js:repositories.bzl", "rules_js_dependencies")
load("@aspect_rules_js//npm:npm_import.bzl", "npm_translate_lock")

rules_js_dependencies()

load("@rules_nodejs//nodejs:repositories.bzl", "nodejs_register_toolchains")

nodejs_register_toolchains(
    name = "nodejs",
    node_version = "14.20.0",
)

npm_translate_lock(
    name = "npm",
    pnpm_lock = "//:pnpm-lock.yaml",
    npmrc = "//:.npmrc",
)

load("@npm//:repositories.bzl", "npm_repositories")

npm_repositories()