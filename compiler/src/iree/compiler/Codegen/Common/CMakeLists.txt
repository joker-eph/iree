################################################################################
# Autogenerated by build_tools/bazel_to_cmake/bazel_to_cmake.py from           #
# compiler/src/iree/compiler/Codegen/Common/BUILD.bazel                        #
#                                                                              #
# Use iree_cmake_extra_content from iree/build_defs.oss.bzl to add arbitrary   #
# CMake-only content.                                                          #
#                                                                              #
# To disable autogeneration for this file entirely, delete this header.        #
################################################################################

iree_add_all_subdirs()

iree_tablegen_library(
  NAME
    FoldTensorExtractOpIncGen
  TD_FILE
    "FoldTensorExtractOp.td"
  OUTS
    --gen-rewriters FoldTensorExtractOp.cpp.inc
)

iree_cc_library(
  NAME
    TransformDialectInterpreterPass
  SRCS
    "TransformDialectInterpreterPass.cpp"
  DEPS
    IREEDialectsTransforms
    IREELinalgExtDialect
    IREELinalgExtTransformOps
    IREELinalgTransformDialect
    LLVMSupport
    MLIRAffineDialect
    MLIRAffineTransformOps
    MLIRAffineUtils
    MLIRAnalysis
    MLIRArithDialect
    MLIRArithTransforms
    MLIRArithUtils
    MLIRAsyncDialect
    MLIRBufferizationDialect
    MLIRBufferizationTransformOps
    MLIRBufferizationTransforms
    MLIRFuncDialect
    MLIRGPUDialect
    MLIRGPUTransformOps
    MLIRIR
    MLIRLLVMDialect
    MLIRLinalgDialect
    MLIRLinalgTransformOps
    MLIRLinalgTransforms
    MLIRMemRefTransformOps
    MLIRPDLDialect
    MLIRPDLInterpDialect
    MLIRPass
    MLIRRewrite
    MLIRSCFDialect
    MLIRSCFTransformOps
    MLIRSCFTransforms
    MLIRSCFUtils
    MLIRSupport
    MLIRTensorDialect
    MLIRTensorTransforms
    MLIRTransformDialect
    MLIRTransformDialectTransforms
    MLIRVectorDialect
    MLIRVectorTransformOps
    MLIRVectorTransforms
    iree::compiler::Codegen::Common::TransformExtensions::CommonExtensions
    iree::compiler::Codegen::LLVMCPU::TransformExtensions::LLVMCPUExtensions
    iree::compiler::Codegen::LLVMGPU::TransformExtensions::LLVMGPUExtensions
    iree::compiler::Codegen::PassHeaders
    iree::compiler::Codegen::TransformDialectStrategies::Common::TransformDialectStrategies
    iree::compiler::Dialect::Flow::IR
    iree::compiler::Dialect::Flow::TransformExtensions::FlowExtensions
    iree::compiler::Utils
  PUBLIC
)

iree_cc_library(
  NAME
    CommonPasses
  HDRS
    "BufferizationAnalysis.h"
    "CommonPasses.h"
    "EncodingInfo.h"
    "Transforms.h"
  SRCS
    "BubbleUpOrdinalOps.cpp"
    "BufferizationAnalysis.cpp"
    "BufferizeCopyOnlyDispatchesPass.cpp"
    "CleanupBufferAllocViewPass.cpp"
    "ConcretizePadResultShape.cpp"
    "ConvertBf16ArithToF32.cpp"
    "ConvertBf16ToUInt16Buffers.cpp"
    "ConvertToDestinationPassingStylePass.cpp"
    "DecomposeAffineOpsPass.cpp"
    "DecomposePackUnPackOps.cpp"
    "EraseHALDescriptorTypeFromMemRef.cpp"
    "FlattenMemRefSubspanPass.cpp"
    "FoldTensorExtractOpPass.cpp"
    "ForOpCanonicalizationPass.cpp"
    "FuseTensorPadWithConsumer.cpp"
    "HoistStaticallyBoundAllocations.cpp"
    "IREEComprehensiveBufferizePass.cpp"
    "IREEExpandStridedMetadata.cpp"
    "InstrumentMemoryAccesses.cpp"
    "LowerUKernelsToCalls.cpp"
    "MaterializeEncodingIntoPackUnPack.cpp"
    "OptimizeVectorTransferPass.cpp"
    "PolynomialApproximationPass.cpp"
    "RematerializeParallelOps.cpp"
    "SplitFullPartialTransferPass.cpp"
    "TestExecutablePreprocessing.cpp"
    "TestPartitionableLoopsInterface.cpp"
    "TileAndDistributeToWorkgroupsPass.cpp"
    "TileDispatchUsingInterface.cpp"
    "TypePropagationPass.cpp"
    "VectorizePad.cpp"
    "WorkgroupSpecializationPass.cpp"
  DEPS
    IREELinalgExtDialect
    IREELinalgExtPasses
    IREELinalgExtTransforms
    LLVMSupport
    MLIRAffineDialect
    MLIRAffineTransforms
    MLIRAffineUtils
    MLIRAnalysis
    MLIRArithDialect
    MLIRArithTransforms
    MLIRArithUtils
    MLIRBufferizationDialect
    MLIRBufferizationTransforms
    MLIRFuncDialect
    MLIRGPUDialect
    MLIRIR
    MLIRLLVMCommonConversion
    MLIRLLVMDialect
    MLIRLinalgDialect
    MLIRLinalgTransforms
    MLIRLinalgUtils
    MLIRMathDialect
    MLIRMathTransforms
    MLIRMemRefDialect
    MLIRMemRefTransforms
    MLIRPass
    MLIRSCFDialect
    MLIRSCFToControlFlow
    MLIRSCFTransforms
    MLIRSCFUtils
    MLIRSideEffectInterfaces
    MLIRSupport
    MLIRTensorDialect
    MLIRTensorTransforms
    MLIRTensorUtils
    MLIRTilingInterface
    MLIRTransformDialect
    MLIRTransforms
    MLIRVectorDialect
    MLIRVectorTransforms
    MLIRViewLikeInterface
    iree::builtins::ukernel::exported_bits
    iree::compiler::Codegen::Common::FoldTensorExtractOpIncGen
    iree::compiler::Codegen::Dialect::IREECodegenDialect
    iree::compiler::Codegen::Interfaces::BufferizationInterfaces
    iree::compiler::Codegen::Interfaces::PartitionableLoopsInterface
    iree::compiler::Codegen::Interfaces::UKernelOpInterface
    iree::compiler::Codegen::PassHeaders
    iree::compiler::Codegen::Transforms
    iree::compiler::Codegen::Utils
    iree::compiler::Dialect::Flow::IR
    iree::compiler::Dialect::HAL::IR
    iree::compiler::Dialect::Util::IR
    iree::compiler::Dialect::VMVX::IR
    iree::compiler::Dialect::VMVX::IR::VMVXDialect
    iree::compiler::Utils
  PUBLIC
)

iree_cc_library(
  NAME
    Common
  HDRS
    "ExtractAddressComputation.h"
    "UserConfig.h"
  SRCS
    "DecomposeConvolutionToLowerDimOps.cpp"
    "DecomposeLinalgGeneric.cpp"
    "ExtractAddressComputation.cpp"
    "FoldAffineMinInDistributedLoops.cpp"
    "MemrefCopyToLinalg.cpp"
    "PadDynamicAlloc.cpp"
    "RemoveTrivialLoops.cpp"
    "UserConfig.cpp"
  DEPS
    ::CommonPasses
    ::TransformDialectInterpreterPass
    IREELinalgExtDialect
    IREELinalgExtPasses
    IREELinalgExtTransforms
    LLVMSupport
    MLIRAffineAnalysis
    MLIRAffineDialect
    MLIRAffineUtils
    MLIRAnalysis
    MLIRArithDialect
    MLIRArithTransforms
    MLIRArithUtils
    MLIRBufferizationDialect
    MLIRBufferizationTransforms
    MLIRFuncDialect
    MLIRGPUDialect
    MLIRIR
    MLIRLLVMCommonConversion
    MLIRLLVMDialect
    MLIRLinalgDialect
    MLIRLinalgTransforms
    MLIRMathDialect
    MLIRMathTransforms
    MLIRMemRefDialect
    MLIRMemRefTransforms
    MLIRPass
    MLIRSCFDialect
    MLIRSCFToControlFlow
    MLIRSCFTransforms
    MLIRSCFUtils
    MLIRSideEffectInterfaces
    MLIRSupport
    MLIRTensorDialect
    MLIRTensorTransforms
    MLIRTilingInterface
    MLIRTransformDialect
    MLIRTransforms
    MLIRValueBoundsOpInterface
    MLIRVectorDialect
    MLIRVectorToSCF
    MLIRVectorTransforms
    MLIRViewLikeInterface
    iree::compiler::Codegen::Common::FoldTensorExtractOpIncGen
    iree::compiler::Codegen::Dialect::IREECodegenDialect
    iree::compiler::Codegen::Interfaces::BufferizationInterfaces
    iree::compiler::Codegen::Interfaces::PartitionableLoopsInterface
    iree::compiler::Codegen::PassHeaders
    iree::compiler::Codegen::Transforms
    iree::compiler::Codegen::Utils
    iree::compiler::Dialect::Flow::IR
    iree::compiler::Dialect::HAL::IR
    iree::compiler::Dialect::Util::IR
    iree::compiler::Utils
  PUBLIC
)

### BAZEL_TO_CMAKE_PRESERVES_ALL_CONTENT_BELOW_THIS_LINE ###
