add_executable(TestConv TestConv.cpp)
target_compile_definitions(TestConv PRIVATE RTMEMREF_INTERNAL_API)
target_include_directories(TestConv
        PRIVATE
        ${ONNX_MLIR_BIN_ROOT}
        ${ONNX_MLIR_SRC_ROOT}/include)
target_link_libraries(TestConv
        ${OMLibs}
        ${MLIRLibs}
        ${CMAKE_DL_LIBS}
        rapidcheck
        MainUtils
        ExecutionSession
        OMTensorUtils)
add_test(NAME OMTestConv COMMAND TestConv)
