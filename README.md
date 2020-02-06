Instalar GraalVM. Se aconseja hacerlo con [SDKMAN!](https://sdkman.io/)

Según la documentación de GraalVM, hay que ejecutar lo siguiente en la consola

```
$ gu install llvm-toolchain
$ export LLVM_TOOLCHAIN=$(lli --print-toolchain-path)
```

A mi lo segundo no me ha funcionado, así que he buscado donde está el ejecutable `clang`, que en mi caso está en `~/.sdkman/candidates/java/19.2.1-grl/jre/languages/llvm/native/bin/`

Por lo tanto he ejecutado

`$ export LLVM_TOOLCHAIN=export LLVM_TOOLCHAIN=~/.sdkman/candidates/java/19.2.1-grl/jre/languages/llvm/native/bin/`

Para compilar `hello.c`, ejecutar lo siguiente:

`$ $LLVM_TOOLCHAIN/clang hello.c -o hello`

Ahora compilar el `Polyglot.java`

`$ javac Polyglot.java`

Ejecutar

`$ java Polyglot`

Más info en la [documentación de GraalVM](https://www.graalvm.org/docs/reference-manual/languages/llvm/)
