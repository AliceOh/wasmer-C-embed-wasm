# wasmer-C-embed-wasm
Example code to load a wasm file, add.wasm, into a C file and calling the function in the C file.

$ make clean instance && ./instance
Creating the store...
Compiling module...
Creating imports...
Instantiating module...
Retrieving exports...
Calling `add_one` function...
Results of `add_one`: 124



Environmentt needed:
(1)
Install wasmer:
curl https://get.wasmer.io -sSfL | sh
$ wasmer config --pkg-config
prefix=/Users/USER/.wasmer
exec_prefix=/Users/USER/.wasmer/bin
includedir=/Users/USER/.wasmer/include
libdir=/Users/syrus/.wasmer/lib

Name: wasmer
Description: The Wasmer library for running WebAssembly
Version: 2.0.0
Cflags: -I/Users/USER/.wasmer/include/wasmer
Libs: -L/Users/syrus/.wasmer/lib -lwasmer

(2)
Install wasienv to compile C/C++ into WASI WebAssembly binary code
$ curl https://raw.githubusercontent.com/wasienv/wasienv/master/install.sh | sh
$  wasienv install-sdk unstable
$ wasicc add.c -o add.wasm

Tools you may want:
https://github.com/WebAssembly/wabt  - for example: wasm2wat add.wasm -o add.wat 
https://docs.rs/wasmer-c-api/2.0.0/wasmer_c_api/wasm_c_api/index.html wasm_c_api document
