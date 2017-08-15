include_defs('//BUCKAROO_DEPS')

prebuilt_cxx_library(
  name = 'bsoncxx-cmake-generated',
  header_namespace = 'bsoncxx',
  header_only = True,
  exported_platform_headers = [
    (
      'default',
      subdir_glob([
        ('cmake-generated/macosx-x86_64/src/bsoncxx', '**/*.hpp'),
        ('cmake-generated/macosx-x86_64/src/bsoncxx', '**/*.hh'),
      ]),
    ),
    (
      '^macos.*',
      subdir_glob([
        ('cmake-generated/macosx-x86_64/src/bsoncxx', '**/*.hpp'),
        ('cmake-generated/macosx-x86_64/src/bsoncxx', '**/*.hh'),
      ]),
    ),
  ],
)

cxx_library(
  name = 'bsoncxx',
  header_namespace = '',
  exported_headers = subdir_glob([
    ('src', 'bsoncxx/**/*.hpp'),
    ('src', 'bsoncxx/**/*.hh'),
  ]),
  srcs = glob([
    'src/bsoncxx/**/*.cpp',
  ], excludes = [
    'src/bsoncxx/test/**/*.cpp',
  ]),
  deps = BUCKAROO_DEPS + [
    ':bsoncxx-cmake-generated',
  ],
  visibility = [
    'PUBLIC',
  ],
)

prebuilt_cxx_library(
  name = 'mongocxx-cmake-generated',
  header_namespace = 'mongocxx',
  header_only = True,
  exported_platform_headers = [
    (
      'default',
      subdir_glob([
        ('cmake-generated/macosx-x86_64/src/mongocxx', '**/*.hpp'),
        ('cmake-generated/macosx-x86_64/src/mongocxx', '**/*.hh'),
      ]),
    ),
    (
      '^macos.*',
      subdir_glob([
        ('cmake-generated/macosx-x86_64/src/mongocxx', '**/*.hpp'),
        ('cmake-generated/macosx-x86_64/src/mongocxx', '**/*.hh'),
      ]),
    ),
  ],
)

cxx_library(
  name = 'mongocxx',
  header_namespace = '',
  exported_headers = subdir_glob([
    ('src', 'mongocxx/**/*.hpp'),
    ('src', 'mongocxx/**/*.hh'),
  ]),
  srcs = glob([
    'src/mongocxx/**/*.cpp',
  ], excludes = [
    'src/mongocxx/test/**/*.cpp',
  ]),
  deps = BUCKAROO_DEPS + [
    ':mongocxx-cmake-generated',
    ':bsoncxx',
  ],
  visibility = [
    'PUBLIC',
  ],
)

cxx_library(
  name = 'catch',
  header_namespace = '',
  exported_headers = subdir_glob([
    ('src/third_party/catch/include', '**/*.hpp'),
  ]),
  srcs = glob([
    'src/third_party/catch/**/*.cpp',
  ]),
  visibility = [
    '//...',
  ],
)
