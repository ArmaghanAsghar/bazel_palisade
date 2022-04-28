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
    name = "palisade",
    build_file = "//patches:palisade.BUILD",
    remote="https://gitlab.com/palisade/palisade-release.git",
    commit = "0860127401ab794591f931fa2c61426c7b56ee2d",
    shallow_since = "1643411789 +0000",
    init_submodules = True,
)
