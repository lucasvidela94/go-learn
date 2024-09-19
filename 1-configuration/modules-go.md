# Módulos en Go y Versionado Semántico

## Módulos en Go

### Definición
Un módulo en Go es una colección de paquetes relacionados que se versiona como una unidad. Funciona como una pieza de un rompecabezas más grande en la arquitectura de una aplicación.

### Características
- Encapsulan funcionalidades específicas (ej. módulo de autenticación)
- Pueden ser utilizados por otros módulos (ej. una API REST usando el módulo de autenticación)
- Promueven la modularidad y reutilización del código

### Gestión de módulos

#### `go mod init`
- Inicializa un nuevo módulo, creando el archivo `go.mod`
- Se usa típicamente al inicio de un nuevo proyecto o módulo
- Sintaxis: `go mod init [nombre-del-módulo]`

#### `go.mod`
- Archivo que define el módulo
- Contiene:
  - Nombre del módulo
  - Versión de Go requerida
  - Dependencias directas del módulo

#### `go.sum`
- Archivo que contiene los hashes criptográficos de las dependencias
- Asegura la integridad de las dependencias descargadas
- Funciona como un "historial de descargas" de módulos

## Versionado Semántico (SemVer)

### Definición
Sistema de versionado que utiliza tres números para representar cambios en el software: MAJOR.MINOR.PATCH

### Componentes
1. MAJOR: Cambios incompatibles con versiones anteriores
2. MINOR: Nuevas funcionalidades compatibles con versiones anteriores
3. PATCH: Correcciones de errores compatibles con versiones anteriores

### Ejemplo
- Versión inicial: 1.0.0
- Nueva funcionalidad: 1.1.0
- Corrección de error: 1.1.1
- Cambio incompatible: 2.0.0

### SemVer en Go
- Los módulos en Go usan SemVer para su versionado
- Por defecto, un módulo comienza en la versión v0 o v1
- Cambios mayores (v2, v3, etc.) requieren modificación manual del import path

### Beneficios
- Facilita la gestión de dependencias
- Ayuda a prevenir "dependency hell"
- Permite una clara comunicación de cambios entre versiones

### Buenas prácticas
- Documentar claramente los cambios entre versiones
- Mantener la compatibilidad hacia atrás cuando sea posible
- Utilizar tags en el sistema de control de versiones para marcar releases

# Módulos en Go, Versionado Semántico y Flujo de Git para Release


## Flujo de Git para un Release

### Pasos para realizar un release

1. **Realizar cambios en la rama correspondiente**
   - Ejemplo: `git add .`
   - `git commit -m "style: Refactor form x template"`

2. **Push a la rama específica**
   - Ejemplo: `git push origin feature-style-refactor`
   - Nota: Asegurarse de estar en la rama correcta antes de hacer commit para evitar errores

3. **Merge a la rama de destino**
   - Opciones:
     a) Merge directo a la rama de producción o desarrollo
     b) Crear un Pull Request para revisión antes del merge

4. **Crear y actualizar el tag de release**
   - Crear un nuevo tag: `git tag -a v1.2.3 -m "Release version 1.2.3"`
   - Push del tag: `git push origin v1.2.3`

5. **Actualizar el commit con respecto al release**
   - Actualizar CHANGELOG.md si se utiliza
   - Commit de los cambios relacionados con el release: `git commit -m "Bump version to 1.2.3"`

### Buenas prácticas
- Utilizar ramas feature para desarrollos específicos
- Realizar code reviews antes de mergear a ramas principales
- Mantener un historial de cambios (CHANGELOG) actualizado
- Seguir las convenciones de commit semántico (ej. "feat:", "fix:", "docs:")
- Probar exhaustivamente en un entorno de staging antes de release a producción

### Relación con versionado semántico
- El número de versión del tag debe seguir las reglas de SemVer
- Decidir el incremento de versión basado en la naturaleza de los cambios (MAJOR, MINOR, PATCH)

Este flujo de trabajo ayuda a mantener un historial de cambios claro y facilita la gestión de versiones en proyectos Go, alineándose con las mejores prácticas de desarrollo y control de versiones.
