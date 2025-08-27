project(
  'cpp23-hello-world',
  'cpp',
  version: '0.1.0',
  license: 'MIT',
  license_files: ['LICENSE'],
  default_options: ['cpp_std=c++23,c++latest'],
  meson_version: '>=1.3.0',
)

cxx = meson.get_compiler('cpp')

link_args = []

code = '''
#include <print>

int main() {
    std::println("Hello, World!");
    return 0;
}'''

if cxx.links(code, name: 'std::println without libstdc++exp')
  message('std::println works without extra linking')
elif cxx.links(code, name: 'std::println with libstdc++exp', args: ['-lstdc++exp'])
  message('std::println requires -lstdc++exp')
  link_args += ['-lstdc++exp']
else
  warning(
    'Test using std::println did not succeed. This likely means <print> is not usable with this compiler version or setup.',
  )
endif

exe = executable('main', 'main.cpp', install: true, link_args: link_args)

test('main', exe)
