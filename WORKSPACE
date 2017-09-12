workspace(name = "iptf")

local_repository(
  name = "org_tensorflow",
  path = "tensorflow",
)

local_repository(
  name = "org_tensorflow_tensorboard",
  path = "tensorboard",
)

local_repository(
  name = "com_github_ipfs_go_ipfs",
  path = "go-ipfs",
)

local_repository(
  name = "io_bazel_rules_go",
  path = "rules_go",
)


# TensorFlow depends on "io_bazel_rules_closure" so we need this here.
# Needs to be kept in sync with the same target in TensorFlow's WORKSPACE file.
http_archive(
    name = "io_bazel_rules_closure",
    sha256 = "4be8a887f6f38f883236e77bb25c2da10d506f2bf1a8e5d785c0f35574c74ca4",
    strip_prefix = "rules_closure-aac19edc557aec9b603cd7ffe359401264ceff0d",
    urls = [
        "http://mirror.bazel.build/github.com/bazelbuild/rules_closure/archive/aac19edc557aec9b603cd7ffe359401264ceff0d.tar.gz",  # 2017-05-10
        "https://github.com/bazelbuild/rules_closure/archive/aac19edc557aec9b603cd7ffe359401264ceff0d.tar.gz",
    ],
)

# Please add all new TFI dependencies in workspace.bzl.
load('//iptf:workspace.bzl', 'iptf_workspace')
iptf_workspace()

# Specify the minimum required bazel version.
load("@org_tensorflow//tensorflow:workspace.bzl", "check_version")
check_version("0.4.5")
