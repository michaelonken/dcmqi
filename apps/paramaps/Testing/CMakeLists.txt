
#-----------------------------------------------------------------------------
include(dcmqiTest)

#-----------------------------------------------------------------------------
set(BASELINE ${CMAKE_SOURCE_DIR}/data/paramaps/)
include_directories(${ITK_INCLUDE_DIRS})

#-----------------------------------------------------------------------------
set(MODULE_NAME itkimage2paramap)

dcmqi_add_test_executable(
  MODULE_NAME ${MODULE_NAME}
  EXECUTABLE_NAME ${MODULE_NAME}Test
  )

dcmqi_add_test(
  NAME ${MODULE_NAME}_hello
  MODULE_NAME ${MODULE_NAME}
  COMMAND $<TARGET_FILE:${MODULE_NAME}> --help
  )

dcmqi_add_test(
  NAME ${MODULE_NAME}_makeParametricMap
  MODULE_NAME ${MODULE_NAME}
  COMMAND $<TARGET_FILE:${MODULE_NAME}>
    --inputMetadata ${CMAKE_SOURCE_DIR}/doc/examples/pm-example.json
    --inputImage ${BASELINE}/pm-example.nrrd
    --inputDICOM ${BASELINE}/pm-example-slice.dcm
    --outputDICOM ${TEMP_DIR}/paramap.dcm
  )

dcmqi_add_test(
  NAME ${MODULE_NAME}_makeParametricMapFP
  MODULE_NAME ${MODULE_NAME}
  COMMAND $<TARGET_FILE:${MODULE_NAME}>
    --inputMetadata ${CMAKE_SOURCE_DIR}/doc/examples/pm-example-float.json
    --inputImage ${BASELINE}/pm-example-float.nrrd
    --inputDICOM ${BASELINE}/pm-example-slice.dcm
    --outputDICOM ${TEMP_DIR}/paramap-float.dcm
  )

#-----------------------------------------------------------------------------
set(MODULE_NAME paramap2itkimage)

dcmqi_add_test(
  NAME ${MODULE_NAME}_hello
  MODULE_NAME ${MODULE_NAME}
  COMMAND $<TARGET_FILE:${MODULE_NAME}> --help
  )

dcmqi_add_test_executable(
  MODULE_NAME ${MODULE_NAME}
  EXECUTABLE_NAME ${MODULE_NAME}Test
  )

dcmqi_add_test(
  NAME ${MODULE_NAME}_makeNRRDParametricMap
  MODULE_NAME ${MODULE_NAME}
  RESOURCE_LOCK ${TEMP_DIR}/pmap.nrrd
  COMMAND $<TARGET_FILE:${MODULE_NAME}Test>
    --compare ${BASELINE}/pm-example.nrrd ${TEMP_DIR}/pmap.nrrd
    ${MODULE_NAME}Test
      --inputDICOM ${TEMP_DIR}/paramap.dcm
      --outputDirectory ${TEMP_DIR}
  TEST_DEPENDS
    itkimage2paramap_makeParametricMap
  )

dcmqi_add_test(
  NAME ${MODULE_NAME}_makeNRRDParametricMapFP
  MODULE_NAME ${MODULE_NAME}
  RESOURCE_LOCK ${TEMP_DIR}/pmap.nrrd
  COMMAND $<TARGET_FILE:${MODULE_NAME}Test>
    --compare ${BASELINE}/pm-example-float.nrrd ${TEMP_DIR}/pmap.nrrd
    ${MODULE_NAME}Test
      --inputDICOM ${TEMP_DIR}/paramap-float.dcm
      --outputDirectory ${TEMP_DIR}
  TEST_DEPENDS
    itkimage2paramap_makeParametricMapFP
  )
