# Comandos en Go

## `go run`
- Ejecuta el código fuente de Go directamente.
- Funciona compilando temporalmente y ejecutando el resultado.
- Ejemplo: `go run main.go`
- Útil para pruebas rápidas y desarrollo.

## `go build`
- Compila el programa Go.
- Genera un ejecutable binario.
- No instala el resultado.
- Ejemplo: `go build hello.go` genera un ejecutable `hello` (o `hello.exe` en Windows).

## `go install`
- Compila e instala el paquete.
- Usa `go.mod` para gestionar dependencias.
- Instala las dependencias para el módulo actual.
- A diferencia de Node.js, Go tiende a evitar paquetes globales, favoreciendo un enfoque más modular.

## `go test`
- Herramienta incorporada para ejecutar pruebas.
- Ejecuta archivos de prueba (terminados en `_test.go`).
- Ejemplos:
  - `go test -run ''`: Ejecuta todas las pruebas.
  - `go test -run Foo`: Ejecuta pruebas que coincidan con "Foo".

## `go get` (Deprecado)
- Anteriormente usado para descargar y instalar paquetes.
- Reemplazado por comandos más específicos en versiones recientes de Go.

## `go fmt`
- Formatea el código fuente según las convenciones de Go.
- Ejecuta `gofmt` en los paquetes especificados.
- Ayuda a mantener un estilo de código consistente.

## `go vet`
- Examina el código Go en busca de errores comunes.
- Funciona como un linter, identificando construcciones sospechosas.
- Ejemplo: Puede detectar llamadas a `printf` mal formateadas.
- No garantiza que todos los reportes sean errores, pero ayuda a identificar problemas potenciales.

## Notas adicionales
- La instalación de Go añade los binarios al PATH del sistema.
- El comando `go` invoca el binario principal de Go.
- Go compila y ejecuta el código fuente, lo que permite una ejecución rápida sin necesidad de un paso de compilación explícito para desarrollo.
