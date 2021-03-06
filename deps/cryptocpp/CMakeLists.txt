if (MSVC)
    set (ASM_SOURCE_LIST src/x64dll.asm src/x64masm.asm)
else()
        set (ASM_SOURCE_LIST rdrand.s)
endif()
add_library(
    crypto
    src/3way.cpp 
    src/adler32.cpp
    src/algebra.cpp 
    src/algparam.cpp 
    src/arc4.cpp 
    src/aria-simd.cpp 
    src/aria.cpp 
    src/ariatab.cpp 
    src/asn.cpp 
    src/authenc.cpp 
    src/base32.cpp 
    src/base64.cpp 
    src/basecode.cpp 
    src/bfinit.cpp 
    src/blake2-simd.cpp 
    src/blake2.cpp 
    src/blowfish.cpp 
    src/blumshub.cpp 
    src/camellia.cpp
    src/cast.cpp 
    src/casts.cpp 
    src/cbcmac.cpp 
    src/ccm.cpp 
    src/chacha.cpp 
    src/cham-simd.cpp 
    src/cham.cpp 
    src/channels.cpp 
    src/cmac.cpp 
    src/cpu.cpp 
    src/crc-simd.cpp 
    src/crc.cpp 
    src/cryptlib.cpp 
    src/default.cpp 
    src/des.cpp 
    src/dessp.cpp 
    src/dh.cpp 
    src/dh2.cpp 
    src/dll.cpp 
    src/dsa.cpp 
    src/eax.cpp 
    src/ec2n.cpp 
    src/eccrypto.cpp 
    src/ecp.cpp 
    src/elgamal.cpp 
    src/emsa2.cpp 
    src/eprecomp.cpp 
    src/esign.cpp 
    src/files.cpp 
    src/filters.cpp 
    src/fips140.cpp 
    src/fipstest.cpp 
    src/gcm-simd.cpp
    src/gcm.cpp 
    src/gf2_32.cpp 
    src/gf2n.cpp 
    src/gf256.cpp 
    src/gfpcrypt.cpp 
    src/gost.cpp 
    src/gzip.cpp 
    src/hc128.cpp 
    src/hc256.cpp 
    src/hex.cpp 
    src/hight.cpp 
    src/hmac.cpp 
    src/hrtimer.cpp 
    src/ida.cpp 
    src/idea.cpp 
    src/integer.cpp 
    src/iterhash.cpp 
    src/kalyna.cpp 
    src/kalynatab.cpp 
    src/keccak.cpp 
    src/keccakc.cpp 
    src/lea-simd.cpp 
    src/lea.cpp 
    src/luc.cpp 
    src/mars.cpp 
    src/marss.cpp 
    src/md2.cpp 
    src/md4.cpp 
    src/md5.cpp 
    src/misc.cpp 
    src/modes.cpp 
    src/mqueue.cpp 
    src/mqv.cpp 
    src/nbtheory.cpp 
    src/oaep.cpp 
    src/osrng.cpp 
    src/padlkrng.cpp 
    src/panama.cpp 
    src/pch.cpp 
    src/pkcspad.cpp 
    src/poly1305.cpp 
    src/polynomi.cpp 
    src/pssr.cpp 
    src/pubkey.cpp 
    src/queue.cpp 
    src/rabbit.cpp 
    src/rabin.cpp 
    src/randpool.cpp 
    src/rc2.cpp 
    src/rc5.cpp 
    src/rc6.cpp 
    src/rdrand.cpp 
    src/rdtables.cpp 
    src/rijndael-simd.cpp 
    src/rijndael.cpp 
    src/ripemd.cpp 
    src/rng.cpp 
    src/rsa.cpp 
    src/rw.cpp 
    src/safer.cpp 
    src/salsa.cpp 
    src/scrypt.cpp 
    src/seal.cpp 
    src/seed.cpp 
    src/serpent.cpp 
    src/sha-simd.cpp 
    src/sha.cpp 
    src/sha3.cpp 
    src/shacal2-simd.cpp 
    src/shacal2.cpp 
    src/shark.cpp 
    src/sharkbox.cpp 
    src/simeck-simd.cpp 
    src/simeck.cpp 
    src/simon.cpp 
    src/simon64-simd.cpp 
    src/simon128-simd.cpp 
    src/simple.cpp 
    src/skipjack.cpp 
    src/sm3.cpp 
    src/sm4.cpp 
    src/sm4-simd.cpp
    src/sosemanuk.cpp 
    src/speck.cpp 
    src/speck64-simd.cpp 
    src/speck128-simd.cpp 
    src/square.cpp 
    src/squaretb.cpp 
    src/sse-simd.cpp 
    src/strciphr.cpp 
    src/tea.cpp 
    src/tftables.cpp 
    src/threefish.cpp 
    src/tiger.cpp 
    src/tigertab.cpp 
    src/ttmac.cpp 
    src/tweetnacl.cpp 
    src/twofish.cpp 
    src/vmac.cpp 
    src/wake.cpp 
    src/whrlpool.cpp 
    src/xtr.cpp 
    src/xtrcrypt.cpp 
    src/zdeflate.cpp 
    src/zinflate.cpp 
    src/zlib.cpp 
    ${ASM_SOURCE_LIST}
)

target_include_directories(
    crypto
    PUBLIC include ${CMAKE_CURRENT_SOURCE_DIR}/src
)

set_target_properties(
    crypto
    PROPERTIES CXX_STANDARD 11
)

add_executable(
    cryptocpp_test
    test/bench1.cpp 
    test/bench2.cpp 
    test/bench3.cpp 
    test/datatest.cpp 
    test/dlltest.cpp 
    test/fipsalgt.cpp 
    test/regtest1.cpp
    test/regtest2.cpp 
    test/regtest3.cpp 
    test/regtest4.cpp 
    test/test.cpp 
    test/validat0.cpp
    test/validat1.cpp
    test/validat2.cpp
    test/validat3.cpp 
    test/validat4.cpp
    test/validat5.cpp
    test/validat6.cpp
    test/validat7.cpp
    test/validat8.cpp
    test/validat9.cpp
    test/validat10.cpp
)

target_link_libraries(
    cryptocpp_test
    PRIVATE crypto
)

target_include_directories(
    cryptocpp_test
    PUBLIC include
)

set_target_properties(
    cryptocpp_test 
    PROPERTIES CXX_STANDARD 11
)
