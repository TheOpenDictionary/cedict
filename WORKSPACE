load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

RULES_PYTHON_VERSION = "0.1.0"

ODICT_VERSION = "1.4.5"

http_archive(
    name = "rules_python",
    sha256 = "b6d46438523a3ec0f3cead544190ee13223a52f6a6765a29eae7b7cc24cc83a0",
    url = "https://github.com/bazelbuild/rules_python/releases/download/%s/rules_python-%s.tar.gz" % (RULES_PYTHON_VERSION, RULES_PYTHON_VERSION),
)

load("@rules_python//python:pip.bzl", "pip_install")

pip_install(
    name = "deps",
    requirements = "//:requirements.txt",
)

http_archive(
    name = "odict",
    sha256 = "d278002e52c3c43076103e6de31cdd9e052260993267aaeb74f4716de9b86bfa",
    strip_prefix = "odict-%s" % ODICT_VERSION,
    url = "https://github.com/TheOpenDictionary/odict/archive/%s/odict-%s.tar.gz" % (ODICT_VERSION, ODICT_VERSION),
)

load("@odict//bazel:odict_deps.bzl", "odict_deps")

odict_deps()

load("@odict//bazel:odict_extra_deps.bzl", "odict_extra_deps")

odict_extra_deps()
