include_directories(../../include)

add_library(
  ecdsa

  OBJECT

  ecdsa.c
  ecdsa_asn1.c
)


if(ENABLE_TESTS)
add_executable(
  ecdsa_test

  ecdsa_test.cc

  $<TARGET_OBJECTS:test_support>
)

target_link_libraries(ecdsa_test crypto)
add_dependencies(all_tests ecdsa_test)
endif()
