project('Catch', 'cpp')

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

test('tests', executable(
  'tests'
, source_paths
, include_directories : include
))

catch = declare_dependency(include_directories : include)