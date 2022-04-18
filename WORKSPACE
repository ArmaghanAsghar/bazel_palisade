workspace(name = "bazel_testing")


load("@bazel_tools//tools/build_defs/repo:git.bzl","new_git_repository")
load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# Install TFHE
http_archive(
    name = "rules_foreign_cc",
    sha256 = "bcd0c5f46a49b85b384906daae41d277b3dc0ff27c7c752cc51e43048a58ec83",
    strip_prefix = "rules_foreign_cc-0.7.1",
    url = "https://github.com/bazelbuild/rules_foreign_cc/archive/0.7.1.tar.gz",
)


load("@rules_foreign_cc//foreign_cc:repositories.bzl", "rules_foreign_cc_dependencies")

rules_foreign_cc_dependencies()



# Install OpenFHE

new_git_repository(
    name = "openfhe",
    build_file = "//patches:openfhe.BUILD",
    remote="https://gitlab.com/palisade/palisade-development.git",
    commit = "fded3711c5855e968467e2e73ccf2fcd7948dc7d",
    init_submodules = True,
    shallow_since = "1649455211 -0400",
    )
