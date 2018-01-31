project(
  'Catch', 'cpp'
, default_options : [
    'warning_level=3'
  , 'werror=true'
  ]
)

source_files = [
  'ApproxTests.cpp'
, 'BDDTests.cpp'
, 'ClassTests.cpp'
, 'CmdLineTests.cpp'
, 'CompilationTests.cpp'
, 'ConditionTests.cpp'
, 'DecompositionTests.cpp'
, 'EnumToString.cpp'
, 'ExceptionTests.cpp'
, 'GeneratorTests.cpp'
, 'MessageTests.cpp'
, 'MiscTests.cpp'
, 'PartTrackerTests.cpp'
, 'TagAliasTests.cpp'
, 'TestMain.cpp'
, 'ToStringGeneralTests.cpp'
, 'ToStringPair.cpp'
, 'ToStringTuple.cpp'
, 'ToStringVector.cpp'
, 'ToStringWhich.cpp'
, 'TrickyTests.cpp'
, 'VariadicMacrosTests.cpp'
, 'MatchersTests.cpp'
]

source_paths = []
foreach file : source_files
  source_paths += join_paths('projects/SelfTest', file)
endforeach

include = include_directories('include')

cpp_compiler = meson.get_compiler('cpp')

maybe_cpp_test_flags = [
  '-fdiagnostics-color'
, '-ftemplate-backtrace-limit=0'
, '-Wwrite-strings'
, '-Wno-gnu-statement-expression' # clang issue with assert.h
]
cpp_test_flags = []
foreach flag : maybe_cpp_test_flags
  if cpp_compiler.has_argument(flag)
    cpp_test_flags += flag
  endif
endforeach

test('tests'
, executable(
    'tests'
  , source_paths
  , include_directories : include
  , implicit_include_directories : false
  , cpp_args : cpp_test_flags
  )
, args : ['-s']
)

catch = declare_dependency(include_directories : include)