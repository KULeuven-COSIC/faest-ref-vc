sources = configure_file(
    input: '../crypto_sign.c.in',
    output: 'crypto_sign.c',
    configuration: param_256f
)
headers = [
    configure_file(
        input: '../crypto_sign.h.in',
        output: 'crypto_sign.h',
        configuration: param_256f
    ),
    configure_file(
        input: '../crypto_sign.h.in',
        output: 'api.h',
        configuration: param_256f
    )
]

libfaest_256f = static_library('faest_256f',
  sources,
  dependencies: libfaest_dependency,
  include_directories: include_directories,
  c_args: defines + c_flags
)
install_headers(headers, subdir: 'faest_256f')
libfaest_dependency = declare_dependency(
  link_with: libfaest,
  include_directories: include_directories
)