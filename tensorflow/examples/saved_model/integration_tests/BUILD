licenses(["notice"])  # Apache 2.0

exports_files(["LICENSE"])

load("//tensorflow:tensorflow.bzl", "py_test")

py_binary(
    name = "export_text_rnn_model",
    srcs = ["export_text_rnn_model.py"],
    deps = [
        "//tensorflow:tensorflow_py",
    ],
)

py_binary(
    name = "use_text_rnn_model",
    srcs = ["use_text_rnn_model.py"],
    deps = [
        "//tensorflow:tensorflow_py",
    ],
)

py_binary(
    name = "export_rnn_cell",
    srcs = ["export_rnn_cell.py"],
    deps = [
        "//tensorflow:tensorflow_py",
    ],
)

py_binary(
    name = "use_rnn_cell",
    srcs = ["use_rnn_cell.py"],
    deps = [
        "//tensorflow:tensorflow_py",
    ],
)

py_binary(
    name = "export_simple_text_embedding",
    srcs = ["export_simple_text_embedding.py"],
    deps = [
        "//tensorflow:tensorflow_py",
    ],
)

py_binary(
    name = "use_model_in_sequential_keras",
    srcs = ["use_model_in_sequential_keras.py"],
    deps = [
        "//tensorflow:tensorflow_py",
    ],
)

py_test(
    name = "saved_model_test",
    srcs = [
        "saved_model_test.py",
    ],
    data = [
        ":export_rnn_cell",
        ":export_simple_text_embedding",
        ":export_text_rnn_model",
        ":use_model_in_sequential_keras",
        ":use_rnn_cell",
        ":use_text_rnn_model",
    ],
    srcs_version = "PY2AND3",
    tags = [
        "noasan",  # forge input size exceeded
        "nomsan",  # forge input size exceeded
        "notsan",  # forge input size exceeded
    ],
    deps = [
        "//tensorflow:tensorflow_py",
    ],
)
