# Lista de Aprendizaje de Golang

## 1. Configuración y Herramientas
- [x] Instalar Go
  - [x] Descargar e instalar para tu sistema operativo
  - [x] Configurar variables de entorno (GOROOT, GOPATH)
- [x] Entender la estructura de directorios de Go
  - [x] src, pkg, bin
  - [x] Espacios de trabajo
- [ ] Aprender el sistema de módulos de Go
  - [ ] go mod init
  - [ ] go.mod y go.sum
  - [ ] Versionado semántico
- [ ] Dominar los comandos de Go
  - [ ] go run
  - [ ] go build
  - [ ] go install
  - [ ] go test
  - [ ] go get
  - [ ] go fmt
  - [ ] go vet
- [ ] Configurar tu IDE/editor preferido
  - [ ] VSCode con extensión Go
  - [ ] GoLand
  - [ ] Vim/Neovim con plugins de Go

## 2. Sintaxis Básica y Tipos de Datos
- [ ] Entender la estructura del programa
  - [ ] package main
  - [ ] func main()
- [ ] Aprender declaración de variables
  - [ ] var nombre tipo
  - [ ] Declaración corta (:=)
  - [ ] Declaración múltiple
- [ ] Dominar tipos de datos básicos
  - [ ] Enteros
  - [ ] Números de punto flotante
  - [ ] Números complejos
  - [ ] Booleanos
  - [ ] Strings
  - [ ] Runas
- [ ] Trabajar con constantes
  - [ ] Palabra clave const
  - [ ] iota para enumeraciones
- [ ] Practicar con operadores
  - [ ] Aritméticos
  - [ ] De comparación
  - [ ] Lógicos
  - [ ] De bits
- [ ] Entender la conversión de tipos
- [ ] Aprender sobre valores cero

## 3. Estructuras de Control
- [ ] Dominar declaraciones if-else
- [ ] Aprender declaraciones switch
- [ ] Practicar diferentes tipos de bucles for
- [ ] Entender break, continue, goto
- [ ] Usar etiquetas y saltos etiquetados

## 4. Funciones
- [ ] Escribir y usar funciones
- [ ] Trabajar con parámetros y valores de retorno
- [ ] Usar valores de retorno nombrados
- [ ] Crear funciones variádicas
- [ ] Entender funciones como valores y clausuras
- [ ] Implementar callbacks
- [ ] Practicar recursión
- [ ] Dominar la palabra clave defer
- [ ] Aprender mecanismos de panic y recover

## 5. Tipos de Datos Compuestos
- [ ] Trabajar con arrays
- [ ] Dominar slices
- [ ] Utilizar maps
- [ ] Crear y usar structs
- [ ] Entender y usar punteros

## 6. Métodos e Interfaces
- [ ] Definir y usar métodos
- [ ] Entender tipos de receptores (valor vs puntero)
- [ ] Crear e implementar interfaces
- [ ] Practicar aserciones de tipo y switch de tipo
- [ ] Entender el enfoque de Go hacia el polimorfismo
- [ ] Aprender sobre composición vs herencia
- [ ] Familiarizarse con interfaces comunes de la biblioteca estándar

## 7. Paquetes y Módulos
- [ ] Crear tus propios paquetes
- [ ] Practicar la importación de paquetes
- [ ] Entender visibilidad y encapsulamiento
- [ ] Aprender sobre inicialización de paquetes
- [ ] Dominar la gestión de dependencias

## 8. Manejo de Errores
- [ ] Entender la filosofía de manejo de errores de Go
- [ ] Crear y usar errores
- [ ] Implementar tipos de error personalizados
- [ ] Practicar el envolvimiento y desenvolvimiento de errores
- [ ] Aprender mejores prácticas para el manejo de errores

## 9. Concurrencia
- [ ] Entender y usar goroutines
- [ ] Dominar canales
- [ ] Practicar con declaraciones select
- [ ] Implementar patrones comunes de concurrencia
- [ ] Usar primitivas del paquete sync
- [ ] Aprender sobre el paquete atomic
- [ ] Entender concurrencia vs paralelismo

## 10. Entrada/Salida y Manejo de Archivos
- [ ] Usar el paquete os para operaciones de archivos
- [ ] Practicar con el paquete bufio
- [ ] Entender los paquetes path y filepath
- [ ] Dominar el manejo de JSON
- [ ] Aprender procesamiento de XML y CSV

## 11. Testing
- [ ] Escribir y ejecutar tests
- [ ] Implementar tests basados en tablas
- [ ] Usar subtests
- [ ] Realizar benchmarking
- [ ] Escribir ejemplos como documentación
- [ ] Practicar mocking
- [ ] Analizar cobertura de código
- [ ] Explorar fuzzing (Go 1.18+)

## 12. Reflexión y Metaprogramación
- [ ] Entender el paquete reflect
- [ ] Practicar inspección de tipos en tiempo de ejecución
- [ ] Aprender sobre generación de código
- [ ] Usar go generate

## 13. Networking
- [ ] Usar el paquete net
- [ ] Crear clientes y servidores HTTP
- [ ] Trabajar con templates
- [ ] Implementar middlewares
- [ ] Aprender sobre WebSockets
- [ ] Explorar gRPC

## 14. Contexts
- [ ] Entender la interfaz context.Context
- [ ] Crear y usar contexts
- [ ] Implementar cancelación y timeouts
- [ ] Aprender mejores prácticas para el uso de context

## 15. Programación Genérica (Go 1.18+)
- [ ] Entender la sintaxis genérica
- [ ] Practicar con restricciones de tipo
- [ ] Crear funciones y tipos genéricos
- [ ] Dominar la inferencia de tipos en genéricos

## 16. Herramientas y Mejores Prácticas
- [ ] Usar go fmt y gofmt
- [ ] Integrar golint
- [ ] Utilizar go vet
- [ ] Configurar golangci-lint
- [ ] Escribir documentación con godoc
- [ ] Aprender técnicas de perfilado y optimización
- [ ] Usar el detector de carreras
- [ ] Implementar versionado semántico
- [ ] Configurar Integración Continua para proyectos Go

## 17. Patrones de Diseño en Go
- [ ] Implementar patrón Singleton
- [ ] Usar patrón Factory
- [ ] Practicar patrón Builder
- [ ] Entender patrón Adapter
- [ ] Implementar patrón Decorator
- [ ] Usar patrón Observer
- [ ] Practicar patrón Strategy

## 18. Temas Avanzados
- [ ] Explorar cgo para interoperabilidad con C
- [ ] Aprender sobre compilación condicional
- [ ] Manejar señales del sistema operativo
- [ ] Entender plugins de Go
- [ ] Explorar Assembly en Go
- [ ] Profundizar en el paquete runtime
- [ ] Aprender sobre ajuste del recolector de basura
