# Sets the minimum version of CMake required to build your native library.
# This ensures that a certain set of CMake features is available to
# your build.

cmake_minimum_required(VERSION 3.4.1)

# Specifies a library name, specifies whether the library is STATIC or
# SHARED, and provides relative paths to the source code. You can
# define multiple libraries by adding multiple add_library() commands,
# and CMake builds them for you. When you build your app, Gradle
# automatically packages shared libraries with your APK.

# now build app's shared lib
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -std=c99 -DANDROID_STL=gnustl_static -DANDROID_TOOLCHAIN=clang")

# -Wimplicit-function-declaration
# -Wno-missing-prototypes -Werror=return-type -Wdocumentation -Wunreachable-code-aggressive -Wno-missing-braces
# -Wparentheses -Wswitch -Wno-unused-function -Wunused-label -Wno-unused-parameter -Wunused-variable -Wunused-value -Wempty-body
# -Wconditional-uninitialized -Wno-unknown-pragmas -pedantic -Wshadow -Wfour-char-constants -Wno-conversion -Wconstant-conversion
# -Wint-conversion -Wbool-conversion -Wenum-conversion -Wassign-enum -Wno-shorten-64-to-32 -Wpointer-sign -Wnewline-eof
# -Wdeprecated-declarations -Wno-sign-conversion

add_library( # The name of the library.
             core

             # Shared library.
             SHARED

             # Core files
             src/main/jni/weywallet-core/BRAddress.c
             src/main/jni/weywallet-core/BRAddress.h
             src/main/jni/weywallet-core/BRArray.h
             src/main/jni/weywallet-core/BRBase58.c
             src/main/jni/weywallet-core/BRBase58.h
             src/main/jni/weywallet-core/BRBIP32Sequence.c
             src/main/jni/weywallet-core/BRBIP32Sequence.h
             src/main/jni/weywallet-core/BRBIP38Key.c
             src/main/jni/weywallet-core/BRBIP38Key.h
             src/main/jni/weywallet-core/BRBIP39Mnemonic.c
             src/main/jni/weywallet-core/BRBIP39Mnemonic.h
             src/main/jni/weywallet-core/BRBIP39WordsEn.h
             src/main/jni/weywallet-core/BRBloomFilter.c
             src/main/jni/weywallet-core/BRBloomFilter.h
             src/main/jni/weywallet-core/BRCrypto.c
             src/main/jni/weywallet-core/BRCrypto.h
             src/main/jni/weywallet-core/BRInt.h
             src/main/jni/weywallet-core/BRKey.c
             src/main/jni/weywallet-core/BRKey.h
             src/main/jni/weywallet-core/BRMerkleBlock.c
             src/main/jni/weywallet-core/BRMerkleBlock.h
             src/main/jni/weywallet-core/BRPaymentProtocol.c
             src/main/jni/weywallet-core/BRPaymentProtocol.h
             src/main/jni/weywallet-core/BRPeer.c
             src/main/jni/weywallet-core/BRPeer.h
             src/main/jni/weywallet-core/BRPeerManager.c
             src/main/jni/weywallet-core/BRPeerManager.h
             src/main/jni/weywallet-core/BRSet.c
             src/main/jni/weywallet-core/BRSet.h
             src/main/jni/weywallet-core/BRTransaction.c
             src/main/jni/weywallet-core/BRTransaction.h
             src/main/jni/weywallet-core/BRWallet.c
             src/main/jni/weywallet-core/BRWallet.h

             # BCash files
             src/main/jni/weywallet-core/bcash/BRBCashAddr.c
             src/main/jni/weywallet-core/bcash/BRBCashAddr.h
             src/main/jni/weywallet-core/bcash/BRBCashParams.h

             # Core JNI files
             src/main/jni/weywallet-core/Java/BRCoreJni.h
             src/main/jni/weywallet-core/Java/BRCoreJni.c
             src/main/jni/weywallet-core/Java/com_weywallet_core_BRCoreJniReference.c
             src/main/jni/weywallet-core/Java/com_weywallet_core_BRCoreJniReference.h
             src/main/jni/weywallet-core/Java/com_weywallet_core_BRCoreAddress.c
             src/main/jni/weywallet-core/Java/com_weywallet_core_BRCoreAddress.h
             src/main/jni/weywallet-core/Java/com_weywallet_core_BRCoreChainParams.c
             src/main/jni/weywallet-core/Java/com_weywallet_core_BRCoreChainParams.h
             src/main/jni/weywallet-core/Java/com_weywallet_core_BRCorePeer.c
             src/main/jni/weywallet-core/Java/com_weywallet_core_BRCorePeer.h
             src/main/jni/weywallet-core/Java/com_weywallet_core_BRCoreMasterPubKey.c
             src/main/jni/weywallet-core/Java/com_weywallet_core_BRCoreMasterPubKey.h
             src/main/jni/weywallet-core/Java/com_weywallet_core_BRCoreKey.h
             src/main/jni/weywallet-core/Java/com_weywallet_core_BRCoreKey.c
             src/main/jni/weywallet-core/Java/com_weywallet_core_BRCoreMerkleBlock.c
             src/main/jni/weywallet-core/Java/com_weywallet_core_BRCoreMerkleBlock.h
             src/main/jni/weywallet-core/Java/com_weywallet_core_BRCorePeerManager.c
             src/main/jni/weywallet-core/Java/com_weywallet_core_BRCorePeerManager.h
             src/main/jni/weywallet-core/Java/com_weywallet_core_BRCoreTransaction.c
             src/main/jni/weywallet-core/Java/com_weywallet_core_BRCoreTransaction.h
             src/main/jni/weywallet-core/Java/com_weywallet_core_BRCoreTransactionInput.c
             src/main/jni/weywallet-core/Java/com_weywallet_core_BRCoreTransactionInput.h
             src/main/jni/weywallet-core/Java/com_weywallet_core_BRCoreTransactionOutput.c
             src/main/jni/weywallet-core/Java/com_weywallet_core_BRCoreTransactionOutput.h
             src/main/jni/weywallet-core/Java/com_weywallet_core_BRCorePaymentProtocol.c
             src/main/jni/weywallet-core/Java/com_weywallet_core_BRCorePaymentProtocol.h
             src/main/jni/weywallet-core/Java/com_weywallet_core_BRCoreWallet.c
             src/main/jni/weywallet-core/Java/com_weywallet_core_BRCoreWallet.h

             # BCash files
             src/main/jni/weywallet-core/bcash/BRBCashAddr.c
             src/main/jni/weywallet-core/bcash/BRBCashAddr.h
             src/main/jni/weywallet-core/bcash/BRBCashParams.h

             # Bech32 files
             src/main/jni/weywallet-core/BRBech32.c
             src/main/jni/weywallet-core/BRBech32.h

             )

include_directories(src/main/jni/weywallet-core/bcash)
include_directories(src/main/jni/weywallet-core/Java)
include_directories(src/main/jni/weywallet-core/)
include_directories(src/main/jni/weywallet-core/secp256k1/include)
include_directories(src/main/jni/weywallet-core/secp256k1/src)
include_directories(src/main/jni/weywallet-core/secp256k1)

include_directories(src/main/secp/secp256k1/include/)
include_directories(src/main/secp/secp256k1/src/)
include_directories(src/main/secp/secp256k1/)
include_directories(src/main/secp/)

# add lib dependencies
target_link_libraries(
    core
    android
    log)
