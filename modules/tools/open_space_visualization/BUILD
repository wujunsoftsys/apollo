load("//tools:cpplint.bzl", "cpplint")

package(default_visibility = ["//visibility:public"])

cc_binary(
    name = "hybrid_a_star_wrapper_lib.so",
    srcs = [
        "hybrid_a_star_wrapper.cc",
    ],
    linkshared = True,
    linkstatic = False,
    deps = [
        "//modules/planning/open_space/coarse_trajectory_generator:hybrid_a_star",
    ],
)

cc_binary(
    name = "distance_approach_problem_wrapper_lib.so",
    srcs = [
        "distance_approach_problem_wrapper.cc",
    ],
    linkshared = True,
    linkstatic = False,
    copts = ["-fopenmp"],
    deps = [
        "//modules/planning/open_space/trajectory_smoother:distance_approach_problem",
        "//modules/planning/open_space/trajectory_smoother:dual_variable_warm_start_problem",
        "//modules/planning/open_space/coarse_trajectory_generator:hybrid_a_star",
    ],
)

cc_binary(
    name = "open_space_roi_wrapper_lib.so",
    srcs = [
        "open_space_roi_wrapper.cc",
    ],
    linkshared = True,
    linkstatic = False,
    deps = [
        "//cyber/common:log",
        "//modules/common/math",
        "//modules/map/pnc_map",
        "//modules/planning/common:planning_gflags",
        "//modules/planning/proto:planner_open_space_config_proto",
        "@eigen",
    ],
)

cpplint()
