project('krkrsdl2', ['c', 'cpp'], default_options: ['optimization=3', 'debug=true', 'warning_level=0'], version: 'unknown')

if target_machine.system() == 'darwin'
	add_languages('objcpp')
endif

cxx = meson.get_compiler('cpp')
host_system = host_machine.system()

sdl2_dep = dependency('sdl2', method: 'auto')

krkrsdl2_src = run_command('cat', files('src/config/src_list/kirikirisdl2/sources.txt')).stdout().strip().split('\n')
krkrsdl2_includes = run_command('cat', files('src/config/src_list/kirikirisdl2/includes.txt')).stdout().strip().split('\n')
if get_option('builtin_plugin_enable_kagparser') == true
	krkrsdl2_src += run_command('cat', files('src/config/src_list/kagparser/sources.txt')).stdout().strip().split('\n')
endif
if get_option('builtin_plugin_enable_extrans') == true
	krkrsdl2_src += run_command('cat', files('src/config/src_list/extrans/sources.txt')).stdout().strip().split('\n')
endif
if get_option('builtin_plugin_enable_extrans') == true
	krkrsdl2_src += run_command('cat', files('src/config/src_list/wutcwf/sources.txt')).stdout().strip().split('\n')
endif
if get_option('builtin_plugin_enable_csvparser') == true
	krkrsdl2_src += run_command('cat', files('src/config/src_list/csvparser/sources.txt')).stdout().strip().split('\n')
endif
if get_option('builtin_plugin_enable_fstat') == true
	krkrsdl2_src += run_command('cat', files('src/config/src_list/fstat/sources.txt')).stdout().strip().split('\n')
endif
if get_option('builtin_plugin_enable_getsample') == true
	krkrsdl2_src += run_command('cat', files('src/config/src_list/getsample/sources.txt')).stdout().strip().split('\n')
endif
if get_option('builtin_plugin_enable_json') == true
	krkrsdl2_src += run_command('cat', files('src/config/src_list/json/sources.txt')).stdout().strip().split('\n')
endif
if get_option('builtin_plugin_enable_layerexbtoa') == true
	krkrsdl2_src += run_command('cat', files('src/config/src_list/layerexbtoa/sources.txt')).stdout().strip().split('\n')
endif
if get_option('builtin_plugin_enable_layereximage') == true
	krkrsdl2_src += run_command('cat', files('src/config/src_list/layereximage/sources.txt')).stdout().strip().split('\n')
endif
if get_option('builtin_plugin_enable_wuvorbis') == true
	krkrsdl2_src += run_command('cat', files('src/config/src_list/wuvorbis/sources.txt')).stdout().strip().split('\n')
	krkrsdl2_includes += run_command('cat', files('src/config/src_list/wuvorbis/includes.txt')).stdout().strip().split('\n')
endif
if get_option('builtin_plugin_enable_kratrac9') == true
	krkrsdl2_src += run_command('cat', files('src/config/src_list/kratrac9/sources.txt')).stdout().strip().split('\n')
endif
if get_option('builtin_plugin_enable_krglhwebp') == true
	krkrsdl2_src += run_command('cat', files('src/config/src_list/krglhwebp/sources.txt')).stdout().strip().split('\n')
	krkrsdl2_includes += run_command('cat', files('src/config/src_list/krglhwebp/includes.txt')).stdout().strip().split('\n')
endif
if get_option('builtin_plugin_enable_kri18n') == true
	krkrsdl2_src += run_command('cat', files('src/config/src_list/kri18n/sources.txt')).stdout().strip().split('\n')
endif
if get_option('builtin_plugin_enable_ksupport') == true
	krkrsdl2_src += run_command('cat', files('src/config/src_list/ksupport/sources.txt')).stdout().strip().split('\n')
endif
if get_option('builtin_plugin_enable_savestruct') == true
	krkrsdl2_src += run_command('cat', files('src/config/src_list/savestruct/sources.txt')).stdout().strip().split('\n')
endif
if get_option('builtin_plugin_enable_varfile') == true
	krkrsdl2_src += run_command('cat', files('src/config/src_list/varfile/sources.txt')).stdout().strip().split('\n')
endif
if get_option('builtin_plugin_enable_scriptsex') == true
	krkrsdl2_src += run_command('cat', files('src/config/src_list/scriptsex/sources.txt')).stdout().strip().split('\n')
endif
if get_option('builtin_plugin_enable_binarystream') == true
	krkrsdl2_src += run_command('cat', files('src/config/src_list/binarystream/sources.txt')).stdout().strip().split('\n')
endif
if get_option('builtin_plugin_enable_layerexareaaverage') == true
	krkrsdl2_src += run_command('cat', files('src/config/src_list/layerexareaaverage/sources.txt')).stdout().strip().split('\n')
endif
if get_option('builtin_plugin_enable_layerexlongexposure') == true
	krkrsdl2_src += run_command('cat', files('src/config/src_list/layerexlongexposure/sources.txt')).stdout().strip().split('\n')
endif
if get_option('builtin_plugin_enable_layerexraster') == true
	krkrsdl2_src += run_command('cat', files('src/config/src_list/layerexraster/sources.txt')).stdout().strip().split('\n')
endif
if get_option('builtin_plugin_enable_lineparser') == true
	krkrsdl2_src += run_command('cat', files('src/config/src_list/lineparser/sources.txt')).stdout().strip().split('\n')
endif
if get_option('builtin_plugin_enable_shrinkcopy') == true
	krkrsdl2_src += run_command('cat', files('src/config/src_list/shrinkcopy/sources.txt')).stdout().strip().split('\n')
endif
if get_option('builtin_plugin_enable_fftgraph') == true
	krkrsdl2_src += run_command('cat', files('src/config/src_list/fftgraph/sources.txt')).stdout().strip().split('\n')
endif
if target_machine.system() == 'emscripten'
	krkrsdl2_src += [
		'src/plugins/kremscripten.cpp',
	]
endif
krkrsdl2_cflags = []
if get_option('warning_level') == '0'
	if cxx.get_id() == 'gcc'
		krkrsdl2_cflags += ['-w']
	endif
	if cxx.get_id() == 'clang' or cxx.get_id() == 'clang-cl' or cxx.get_id() == 'emscripten'
		krkrsdl2_cflags += ['-Wno-everything']
	endif
endif
krkrsdl2_cflags += [
	'-DTVP_OPUS_DECODER_IMPLEMENT',
	'-DTVP_LOG_TO_COMMANDLINE_CONSOLE',
	'-DHAVE_CONFIG_H',
	'-DFT2_BUILD_LIBRARY',
	'-DUSE_ALLOCA',
	'-DOPUS_BUILD',
	'-DHAVE_LRINTF',
	'-DHAVE_LRINT',
	'-DFLOAT_APPROX',
	'-DPNG_ARM_NEON_OPT=0',
]
if target_machine.system() == 'emscripten'
	krkrsdl2_cflags += [
		'-s', 'DISABLE_EXCEPTION_CATCHING=0',
		'-s', 'EXIT_RUNTIME=1',
	]
	if get_option('emscripten_enable_wasm_simd') == true
		krkrsdl2_cflags += [
			'-msimd128',
			'-msse4.2',
		]
	endif
	if get_option('emscripten_enable_threads') == true
		krkrsdl2_cflags += [
			'-s', 'USE_PTHREADS=1',
			'-s', 'PROXY_TO_PTHREAD=1',
			'-s', 'OFFSCREEN_FRAMEBUFFER=1',
		]
	endif
endif
krkrsdl2_cppflags = []
krkrsdl2_cppflags += krkrsdl2_cflags
krkrsdl2_cppflags += [
	'-std=c++11',
	'-Wno-non-virtual-dtor',
]
if cxx.get_id() == 'gcc'
	krkrsdl2_cppflags += ['-fno-delete-null-pointer-checks']
endif
krkrsdl2_ldflags = []
if target_machine.system() == 'linux'
	krkrsdl2_ldflags += ['-pthread']
endif
if target_machine.system() == 'emscripten'
	krkrsdl2_ldflags += [
		'-s', 'DISABLE_EXCEPTION_CATCHING=0',
		'-s', 'EXIT_RUNTIME=1',
		'-s', 'ALLOW_MEMORY_GROWTH=1',
		'-s', 'INITIAL_MEMORY=' + get_option('emscripten_initial_memory').to_string(),
		'-s', 'FORCE_FILESYSTEM=1',
		'-s', 'ASSERTIONS=0',
		'-s', 'STACK_OVERFLOW_CHECK=0',
		'-lidbfs.js',
		'--bind',
		'--no-heap-copy',
	]
	if get_option('emscripten_enable_js_fallback') == true
		krkrsdl2_ldflags += [
			'-s', 'WASM=2',
		]
	else
		krkrsdl2_ldflags += [
			'-s', 'WASM=1',
		]
	endif
	if get_option('emscripten_enable_threads') == true
		krkrsdl2_ldflags += [
			'-s', 'USE_PTHREADS=1',
			'-s', 'PROXY_TO_PTHREAD=1',
			'-s', 'OFFSCREEN_FRAMEBUFFER=1',
		]
	endif
	if get_option('emscripten_enable_source_maps') == true
		krkrsdl2_ldflags += [
			'-g4',
			'--source-map-base', 'http://127.0.0.1:8080/'
		]
	endif
endif
krkrsdl2_dependson = [
	sdl2_dep,
]

if get_option('enable_coretext_rasterizer') == true
	if target_machine.system() == 'darwin'
		coretext_dep = dependency('appleframeworks', modules: 'CoreText')
		krkrsdl2_dependson += [
			coretext_dep
		]
		krkrsdl2_cppflags += [
			'-DKRKRZ_CORETEXT_SUPPORT',
			'-mmacosx-version-min=10.15',
		]
		krkrsdl2_src += [
			'external/krkrz/visual/darwin/CoreTextFontFallback.mm',
			'external/krkrz/visual/darwin/CoreTextFontRasterizer.cc',
			'external/krkrz/visual/darwin/CoreTextFontRasterizer.h',
			'external/krkrz/visual/darwin/CoreTextFontStorage.cc',
			'external/krkrz/visual/darwin/CoreTextFontStorage.h',
		]
	endif
endif

if get_option('builtin_plugin_enable_menu') == true
	krkrsdl2_src += [
		'src/plugins/menu/menu.cc',
	]
	if target_machine.system() == 'darwin'
		cocoa_dep = dependency('appleframeworks', modules: 'Cocoa')
		krkrsdl2_dependson += [
			cocoa_dep
		]
		krkrsdl2_src += [
			'src/plugins/menu/cocoa.mm',
		]
	endif
endif

if get_option('enable_wavemixer_openal') == true
	krkrsdl2_cppflags += [
		'-DTVP_USE_OPENAL',
	]
	if target_machine.system() == 'darwin'
		openal_dep = dependency('appleframeworks', modules: 'OpenAL')
		krkrsdl2_dependson += [
			openal_dep
		]
	else
		openal_dep = dependency('openal', method: 'pkg-config')
		krkrsdl2_dependson += [
			openal_dep
		]
	endif
endif

if get_option('enable_canvas') == true
	krkrsdl2_cppflags += [
		'-DKRKRZ_ENABLE_CANVAS',
	]
	krkrsdl2_src += [
		'external/krkrz/visual/opengl/CanvasIntf.cpp',
		'external/krkrz/visual/opengl/DrawCycleTimer.cpp',
		'external/krkrz/visual/opengl/GLFrameBufferObject.cpp',
		'external/krkrz/visual/opengl/GLShaderUtil.cpp',
		'external/krkrz/visual/opengl/Matrix32Intf.cpp',
		'external/krkrz/visual/opengl/Matrix44Intf.cpp',
		'external/krkrz/visual/opengl/OffscreenIntf.cpp',
		'external/krkrz/visual/opengl/ShaderProgramIntf.cpp',
		'external/krkrz/visual/opengl/TextureIntf.cpp',
		'external/krkrz/visual/opengl/VertexBinderIntf.cpp',
		'external/krkrz/visual/opengl/VertexBufferIntf.cpp',
		'src/core/visual/sdl2/opengl/OpenGLPlatformSDL2.cpp',
		'src/core/visual/sdl2/opengl/OpenGLScreenSDL2.cpp',
	]
	krkrsdl2_includes += [
		'src/core/visual/sdl2/opengl',
		'external/krkrz/visual/opengl',
		'external/krkrz/external/angle/include',
		'external/krkrz/external/glm',
	]
	if target_machine.system() == 'emscripten'
		krkrsdl2_ldflags += [
			'-s', 'MAX_WEBGL_VERSION=2',
			'-s', 'FULL_ES3=1',
		]
	endif
endif

if get_option('enable_case_insensitivity') == true
	krkrsdl2_cppflags += [
		'-DKRKRZ_CASE_INSENSITIVE',
	]
endif

krkrsdl2_override_options = []
if target_machine.system() == 'emscripten'
	krkrsdl2_override_options += [
		'optimization=s',
		'debug=false',
		'b_lto=true'
	]
endif
krkrsdl2 = executable(
	'krkrsdl2',
	sources: krkrsdl2_src,
	c_args: krkrsdl2_cflags,
	cpp_args: krkrsdl2_cppflags,
	objcpp_args: krkrsdl2_cppflags,
	link_args: krkrsdl2_ldflags,
	include_directories: include_directories(krkrsdl2_includes),
	dependencies: krkrsdl2_dependson,
	install: true,
	override_options: krkrsdl2_override_options
)
if target_machine.system() == 'emscripten'
	conf_data = configuration_data()
	conf_data.set('exe_name', krkrsdl2.name())
	krkrsdl2_html = configure_file(input: 'src/config/index.html.in',
		output: 'index.html',
		configuration: conf_data
	)
	krkrsdl2_dependson += krkrsdl2_html
endif
