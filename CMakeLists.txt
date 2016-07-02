cmake_minimum_required(VERSION 3.2)

project(iconv LANGUAGES C)

set(iconv_VERSION 1.14)

if(MSVC)
  set(CMAKE_DEBUG_POSTFIX "d")
endif()

add_executable(genflags
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/genflags.c)
target_include_directories(genflags PUBLIC
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/lib>
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>)
# add_custom_target(gen-flags
#   COMMAND genflags >
#   ${CMAKE_CURRENT_SOURCE_DIR}/lib/flags.h
#   BYPRODUCTS ${CMAKE_CURRENT_SOURCE_DIR}/lib/flags.h)

add_executable(genaliases
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/genaliases.c)
target_include_directories(genaliases PUBLIC
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/lib>
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>)
# add_custom_target(gen-aliases
#   COMMAND genaliases >
#   ${CMAKE_CURRENT_SOURCE_DIR}/lib/aliases.h
#   BYPRODUCTS ${CMAKE_CURRENT_SOURCE_DIR}/lib/aliases.h)

add_library(iconv STATIC
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/armscii_8.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/ascii.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/atarist.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/aliases.gperf
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/aliases.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/aliases_aix.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/aliases_aix_sysaix.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/aliases_dos.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/aliases_extra.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/aliases_osf1.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/aliases_osf1_sysosf1.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/aliases_sysaix.gperf
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/aliases_sysaix.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/aliases_syshpux.gperf
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/aliases_syshpux.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/aliases_sysosf1.gperf
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/aliases_sysosf1.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/aliases_syssolaris.gperf
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/aliases_syssolaris.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/aliases2.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/big5hkscs2008.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/c99.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/ces_big5.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/ces_gbk.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cjk_variants.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cns11643.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cns11643_1.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cns11643_2.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cns11643_3.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cns11643_4.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cns11643_4a.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cns11643_4b.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cns11643_5.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cns11643_6.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cns11643_7.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cns11643_15.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cns11643_inv.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/config.h.in
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/converters.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp437.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp737.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp775.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp850.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp852.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp853.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp855.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp856.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp857.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp858.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp860.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp861.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp862.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp863.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp864.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp865.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp866.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp869.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp874.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp922.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp932.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp932ext.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp936.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp936ext.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp943.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp949.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp950.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp950ext.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp1046.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp1124.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp1125.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp1129.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp1131.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp1133.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp1161.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp1162.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp1163.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp1250.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp1251.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp1252.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp1253.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp1254.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp1255.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp1256.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp1257.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp1258.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp50221_0208_ext.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/cp50221_0212_ext.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/dec_hanyu.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/dec_kanji.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/encodings.def
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/encodings_aix.def
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/encodings_dos.def
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/encodings_extra.def
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/encodings_local.def
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/encodings_osf1.def
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/euc_cn.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/euc_jisx0213.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/euc_jp.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/euc_kr.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/euc_tw.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/flushwc.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/gb2312.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/gb12345.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/gb12345ext.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/gb18030.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/gb18030ext.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/gb18030uni.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/gbk.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/gbkext_inv.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/gbkext1.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/gbkext2.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/georgian_academy.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/georgian_ps.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/hkscs1999.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/hkscs2001.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/hkscs2004.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/hkscs2008.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/hp_roman8.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/hz.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/iconv.c
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/iconv_open1.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/iconv_open2.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/iso646_cn.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/iso646_jp.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/iso2022_cn.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/iso2022_cnext.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/iso2022_jp.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/iso2022_jp1.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/iso2022_jp2.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/iso2022_jp3.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/iso2022_jpms.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/iso2022_kr.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/iso8859_1.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/iso8859_2.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/iso8859_3.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/iso8859_4.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/iso8859_5.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/iso8859_6.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/iso8859_7.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/iso8859_8.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/iso8859_9.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/iso8859_10.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/iso8859_11.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/iso8859_13.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/iso8859_14.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/iso8859_15.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/iso8859_16.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/isoir165.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/isoir165ext.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/java.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/jisx0201.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/jisx0208.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/jisx0212.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/jisx0213.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/johab.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/johab_hangul.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/koi8_r.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/koi8_ru.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/koi8_t.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/koi8_u.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/ksc5601.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/loop_unicode.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/loop_wchar.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/loops.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/mac_arabic.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/mac_centraleurope.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/mac_croatian.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/mac_cyrillic.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/mac_greek.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/mac_hebrew.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/mac_iceland.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/mac_roman.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/mac_romania.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/mac_thai.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/mac_turkish.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/mac_ukraine.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/Makefile.in
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/mulelao.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/nextstep.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/pt154.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/relocatable.c
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/relocatable.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/riscos1.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/rk1048.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/shift_jisx0213.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/sjis.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/tcvn.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/tds565.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/tis620.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/translit.def
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/translit.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/ucs2.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/ucs2be.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/ucs2internal.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/ucs2le.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/ucs2swapped.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/ucs4.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/ucs4be.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/ucs4internal.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/ucs4le.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/ucs4swapped.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/uhc_1.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/uhc_2.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/utf7.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/utf8.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/utf16.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/utf16be.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/utf16le.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/utf32.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/utf32be.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/utf32le.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/vietcomb.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/viscii.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/aliases_aix.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/aliases_dos.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/aliases_extra.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/aliases_osf1.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/aliases2.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/armscii_8.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/ascii.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/atarist.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/big5.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/big5_2003.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/big5hkscs1999.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/big5hkscs2001.h
  ${CMAKE_CURRENT_SOURCE_DIR}/lib/big5hkscs2004.h
)
target_include_directories(
  iconv PRIVATE
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/lib> 
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/libcharset/include> 

)

include(CMakePackageConfigHelpers)
write_basic_package_version_file(
  ${CMAKE_CURRENT_BINARY_DIR}/iconv-config-version.cmake
  VERSION ${iconv_VERSION}
  COMPATIBILITY AnyNewerVersion
)

install(TARGETS iconv EXPORT iconv
  RUNTIME DESTINATION bin
  ARCHIVE DESTINATION lib
  LIBRARY DESTINATION lib)


install(FILES
  ${CMAKE_CURRENT_SOURCE_DIR}/include/iconv.h
  DESTINATION include)

install(EXPORT iconv
  FILE
    iconv.cmake
  NAMESPACE
    iconv::
  DESTINATION
    lib/cmake/iconv
)
install(
  FILES
    cmake/iconv-config.cmake
    ${CMAKE_CURRENT_BINARY_DIR}/iconv-config-version.cmake
  DESTINATION
    lib/cmake/iconv
)