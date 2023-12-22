
project('LibRaw', 'cpp')

libraw_src = [
'src/x3f/x3f_utils_patched.cpp',
'src/x3f/x3f_parse_process.cpp',
'src/decoders/decoders_libraw.cpp',
'src/decoders/dng.cpp',
'src/decoders/kodak_decoders.cpp',
'src/decoders/fuji_compressed.cpp',
'src/decoders/fp_dng.cpp',
'src/decoders/decoders_dcraw.cpp',
'src/decoders/canon_600.cpp',
'src/decoders/generic.cpp',
'src/decoders/crx.cpp',
'src/decoders/smal.cpp',
'src/decoders/decoders_libraw_dcrdefs.cpp',
'src/decoders/unpack.cpp',
'src/decoders/unpack_thumb.cpp',
'src/decoders/load_mfbacks.cpp',
'src/postprocessing/dcraw_process.cpp',
'src/postprocessing/postprocessing_utils_dcrdefs.cpp',
'src/postprocessing/mem_image.cpp',
'src/postprocessing/postprocessing_utils.cpp',
'src/postprocessing/postprocessing_aux.cpp',
'src/postprocessing/aspect_ratio.cpp',
'src/metadata/samsung.cpp',
'src/metadata/pentax.cpp',
'src/metadata/sony.cpp',
'src/metadata/mediumformat.cpp',
'src/metadata/olympus.cpp',
'src/metadata/identify.cpp',
'src/metadata/identify_tools.cpp',
'src/metadata/normalize_model.cpp',
'src/metadata/misc_parsers.cpp',
'src/metadata/makernotes.cpp',
'src/metadata/adobepano.cpp',
'src/metadata/leica.cpp',
'src/metadata/cr3_parser.cpp',
'src/metadata/tiff.cpp',
'src/metadata/ciff.cpp',
'src/metadata/exif_gps.cpp',
'src/metadata/kodak.cpp',
'src/metadata/nikon.cpp',
'src/metadata/minolta.cpp',
'src/metadata/p1.cpp',
'src/metadata/epson.cpp',
'src/metadata/canon.cpp',
'src/metadata/hasselblad_model.cpp',
'src/metadata/fuji.cpp',
'src/integration/dngsdk_glue.cpp',
'src/integration/rawspeed_glue.cpp',
'src/utils/read_utils.cpp',
'src/utils/thumb_utils.cpp',
'src/utils/decoder_info.cpp',
'src/utils/curves.cpp',
'src/utils/phaseone_processing.cpp',
'src/utils/open.cpp',
'src/utils/utils_libraw.cpp',
'src/utils/init_close_utils.cpp',
'src/utils/utils_dcraw.cpp',
'src/preprocessing/raw2image.cpp',
'src/preprocessing/subtract_black.cpp',
'src/preprocessing/ext_preprocess.cpp',
'src/demosaic/dht_demosaic.cpp',
'src/demosaic/dcb_demosaic.cpp',
'src/demosaic/xtrans_demosaic.cpp',
'src/demosaic/aahd_demosaic.cpp',
'src/demosaic/ahd_demosaic.cpp',
'src/demosaic/misc_demosaic.cpp',
'src/write/file_write.cpp',
'src/write/apply_profile.cpp',
'src/write/tiff_writer.cpp',
'src/tables/colordata.cpp',
'src/tables/wblists.cpp',
'src/tables/cameralist.cpp',
'src/tables/colorconst.cpp',
'src/libraw_c_api.cpp',
'src/libraw_datastream.cpp'
]

#jpeg_dep = dependency('libjpeg', required: get_option('jpeg'), fallback : ['libjpeg-turbo', 'jpeg_dep'])
#tiff_dep = dependency('libtiff-4', required: get_option('tiff'), fallback : ['libtiff', 'libtiff4_dep'])
#jpeg_dep = dependency('libjpeg', required: true, fallback : ['libjpeg-turbo', 'jpeg_dep'])
#tiff_dep = dependency('libtiff-4', required: true, fallback : ['libtiff', 'libtiff4_dep'])
#liblcms2_dep = dependency('lcms2', required : true, fallback : ['lcms2', 'liblcms2_dep'])
#libxml2_dep = dependency('libxml2', required : true, fallback : ['libxml2', 'libxml2_dep'])
#zlib_dep = dependency('zlib', required : true, fallback : ['zlib', 'zlib_dep'])

jpeg_dep = dependency('libjpeg', required: true)
tiff_dep = dependency('libtiff-4', required: true)
liblcms2_dep = dependency('lcms2', required : true)
libxml2_dep = dependency('libxml2', required : true)
zlib_dep = dependency('zlib', required : true)
openmp_dep = dependency('OpenMP', required : true, language : 'cpp')

inc = include_directories('libraw')
libraw = library(
  'raw',
  libraw_src,
  include_directories : inc,
  dependencies : [openmp_dep, liblcms2_dep],
  install : true
)

libraw_dep = declare_dependency(link_with : libraw,
  include_directories : inc)
