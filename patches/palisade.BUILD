load("@rules_foreign_cc//foreign_cc:defs.bzl", "cmake")

package(
    default_visibility = ["//visibility:private"],
)

cmake(
    name = "core",
    cache_entries = {
        #"BUILD_BENCHMARKS": "OFF",
        #"BUILD_UNITTESTS": "OFF",
        #"CMAKE_BUILD_TYPE": "Release",
    	#"WITH_OPENMP":"ON",
	"BUILD_UNITTESTS":  "OFF",
	"BUILD_EXAMPLES":   "OFF",
	"BUILD_BENCHMARKS": "OFF",
	"BUILD_EXTRAS":     "OFF",
	"BUILD_STATIC":     "OFF",
	"BUILD_SHARED":     "ON",
	"GIT_SUBMOD_AUTO":  "ON",
	"WITH_BE2":         "ON",
	"WITH_BE4":         "ON",
	"WITH_NTL":         "OFF",
	"WITH_TCM":         "OFF",
	"WITH_INTEL_HEXL":  "OFF",
	"WITH_OPENMP":      "ON",
	"NATIVE_SIZE":      "64",
	"CKKS_M_FACTOR":    "1",
	"WITH_NATIVEOPT":   "OFF",
	"WITH_COVTEST":     "OFF"
	},
    defines = ["MATHBACKEND=2"],
    env = {
        "CMAKE_BUILD_PARALLEL_LEVEL": "16",
    },
    includes = [
        "palisade",
        "palisade/core",
    ],
    lib_source = ":palisade_srcs",
    out_include_dir = "include",
    out_shared_libs = [
        "libPALISADEcore.so.1",
    ],
    visibility = ["//visibility:public"],
)

cmake(
    name = "pke",
    cache_entries = {
       # "BUILD_BENCHMARKS": "OFF",
       # "BUILD_UNITTESTS": "OFF",
       # "CMAKE_BUILD_TYPE": "Release",
    	"BUILD_UNITTESTS":  "OFF",
	"BUILD_EXAMPLES":   "OFF",
	"BUILD_BENCHMARKS": "OFF",
	"BUILD_EXTRAS":     "OFF",
	"BUILD_STATIC":     "OFF",
	"BUILD_SHARED":     "ON",
	"GIT_SUBMOD_AUTO":  "ON",
	"WITH_BE2":         "ON",
	"WITH_BE4":         "ON",
	"WITH_NTL":         "OFF",
	"WITH_TCM":         "OFF",
	"WITH_INTEL_HEXL":  "OFF",
	"WITH_OPENMP":      "ON",
	"NATIVE_SIZE":      "64",
	"CKKS_M_FACTOR":    "1",
	"WITH_NATIVEOPT":   "OFF",
	"WITH_COVTEST":     "OFF"
    },
    defines = ["MATHBACKEND=2"],
    env = {
        "CMAKE_BUILD_PARALLEL_LEVEL": "16",
    },
    includes = [
        "palisade",
        "palisade/core",
        "palisade/pke",
    ],
    lib_source = ":palisade_srcs",
    out_include_dir = "include",
    out_shared_libs = [
        "libPALISADEcore.so.1",
        "libPALISADEpke.so.1",
    ],
    visibility = ["//visibility:public"],
)

cmake(
    name = "binfhe",
    cache_entries = {
        "BUILD_BENCHMARKS": "OFF",
        "BUILD_UNITTESTS": "OFF",
        "CMAKE_BUILD_TYPE": "Release",
    },
    defines = ["MATHBACKEND=2"],
    env = {
        "CMAKE_BUILD_PARALLEL_LEVEL": "16",
    },
    includes = [
        "palisade",
        "palisade/binfhe",
        "palisade/core",
    ],
    lib_source = ":palisade_srcs",
    out_include_dir = "include",
    out_shared_libs = [
        "libPALISADEbinfhe.so.1",
        "libPALISADEcore.so.1",
    ],
    visibility = ["//visibility:public"],
)

# Private rules follow below.

filegroup(
    name = "palisade_srcs",
    srcs = glob([
        "*",
        "configure/**",
        "src/**",
        "third-party/**",
    ]),
)
