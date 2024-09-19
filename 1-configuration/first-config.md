Estructura de Proyectos en Go - Notas Personales
Instalación y Configuración Inicial
Instalé Golang en Fedora así:

bash
Copiar código
sudo dnf install golang
Nota: Para otras distribuciones como Ubuntu, usarías sudo apt install golang, y en MacOS, podrías usar Homebrew con brew install go.

Configuración del entorno: No fue necesario configurar manualmente variables de entorno, ya que Go usa su propio sistema de módulos (go mod).

Estructura de Directorios
Estructura Básica de un Módulo en Go
go.mod: Archivo de configuración del módulo, que gestiona dependencias y versiones del proyecto.

Contiene la versión de Go usada y las dependencias externas necesarias para el proyecto.
modname.go: Un archivo dentro del proyecto que define un paquete de Go (package modname). Es común que cada archivo .go pertenezca a un paquete.

modname_test.go: Archivo donde van los tests asociados al paquete del módulo.

Ejemplo expandido:

go
Copiar código
go.mod
modname.go
modname_test.go
auth.go
auth_test.go
hash.go
hash_test.go
Observaciones personales:

Aunque no parece importar exactamente cómo se nombren los archivos, lo importante es que cada archivo .go pertenezca a un paquete coherente con su funcionalidad.
Este módulo puede ser publicado como un repositorio y organizado como un paquete para funcionar como dependencia en otros proyectos. Esto es gracias al sistema de módulos de Go.
Puedes usar el comando go install github.com/tu-usuario/tu-repositorio para instalar un módulo en otro proyecto de Go.
Convenciones y Escalabilidad
No hay una estructura de carpetas rígida en Go, ya que depende de la complejidad del proyecto.
Por ejemplo, una herramienta CLI podría tener una carpeta cmd, mientras que un módulo de autenticación podría estar en auth.
El diseño de Go sugiere como mejor práctica la separación en módulos y paquetes para mantener el código reutilizable y limpio.
Enfoques de Estructura de Proyectos
1. Estructura con Separación por Carpetas
csharp
Copiar código
cmd/
internal/
pkg/
api/
web/
scripts/
configs/
tests/
docs/
Notas sobre cada carpeta:

cmd: Contiene los entry points (puntos de entrada) para cada aplicación o servicio dentro del proyecto. Útil en proyectos que implementan microservicios o herramientas CLI.

internal: Almacena código privado que no debería ser reutilizable fuera del proyecto. Go impone restricciones para que los paquetes dentro de internal no puedan ser importados desde fuera del módulo.

pkg: Aquí van los paquetes reutilizables que pueden ser exportados y utilizados por otros proyectos externos. Es discutido en la comunidad de Go, ya que algunos prefieren evitar esta convención y usar directamente internal o mantener el código bien organizado en módulos.

api: Código relacionado con APIs (HTTP, RPC), como los manejadores, middlewares, y las definiciones de rutas.

web: El front-end del proyecto, si corresponde. Podría contener archivos estáticos (HTML, CSS, JS) si el proyecto incluye una interfaz de usuario.

scripts: Scripts para tareas comunes como build, despliegue, o mantenimiento.

configs: Archivos de configuración específicos para diferentes entornos (desarrollo, staging, producción, etc.).

tests: Tests unitarios, de integración y otros.

docs: Documentación relacionada con el proyecto, como documentos de diseño o la documentación de la API.

Nota: Esta estructura es flexible y puede ajustarse según el tamaño y las necesidades del proyecto. En proyectos más pequeños, puede ser innecesaria la complejidad que aporta esta organización.

2. Estructura Plana
go
Copiar código
main.go
handler.go
config.go
database.go
static/
templates/
scripts/
configs/
tests/
docs/
Cuándo usarlo: En proyectos más simples o pequeños, donde no se requiere mucha organización por capas o módulos.

3. Estructura por Capas
Organiza el código por capas, promoviendo la separación de responsabilidades. Cada capa maneja una parte distinta del flujo de datos.

markdown
Copiar código
main.go
web/
  - handler.go
  - static/
  - templates/
api/
  - routes.go
  - middleware/
data/
  - database.go
  - repository.go
config/
tests/
docs/
Cuándo usarlo: Cuando se necesita un orden lógico en la interacción entre los componentes. Suele ser útil en aplicaciones web o APIs donde las capas están bien definidas (web, lógica, datos).

4. Domain-Driven Design (DDD)
go
Copiar código
project-root/
    ├── domain/
    │   ├── model.go
    │   ├── repository.go
    ├── application/
    ├── infrastructure/
    ├── tests/
    └── docs/
Cuándo usarlo: Este enfoque es útil cuando el proyecto está altamente orientado al dominio de negocio. Se separa la lógica del negocio (domain) de la infraestructura.

5. Clean Architecture
go
Copiar código
project-root/
    ├── cmd/
    │   ├── your-app/
    │   │   ├── main.go
    ├── internal/
    │   ├── app/
    │   │   ├── handler.go
    │   │   ├── service.go
    │   ├── domain/
    │   │   ├── model.go
    │   │   ├── repository.go
    ├── pkg/
    │   ├── utility/
    │   │   ├── ...
    ├── api/
    │   ├── ...
    ├── web/
    │   ├── ...
    ├── scripts/
    ├── configs/
    ├── tests/
    └── docs/
Concepto de arquitectura limpia: Aquí la idea es que los detalles de implementación (infraestructura) estén separados de la lógica de negocio (domain). La carpeta app suele contener la lógica específica de la aplicación, mientras que domain alberga la lógica central o "reglas de negocio".

6. Estructura Modular
csharp
Copiar código
project-root/
    ├── module1/
    │   ├── cmd/
    │   ├── internal/
    │   ├── pkg/
    │   ├── api/
    │   ├── web/
    │   ├── scripts/
    │   ├── configs/
    │   ├── tests/
    │   └── docs/
    ├── module2/
    │   ├── ...
Ventajas: Facilita la independencia y escalabilidad de cada módulo. Ideal para sistemas complejos o basados en microservicios.

Desventaja: Puede haber cierta repetición en la estructura de carpetas entre módulos.

Preguntas Pendientes
¿Qué se considera una arquitectura "limpia" en Go?

Se refiere a la separación clara entre lógica de negocio y detalles de implementación, facilitando la mantenibilidad y prueba del código.
¿Por qué en la estructura de Clean Architecture hay carpetas app y domain dentro de internal?

app contiene la lógica específica de la aplicación (como servicios), mientras que domain representa las reglas de negocio que son independientes de la infraestructura.
¿Cuáles son las ventajas y desventajas de cada enfoque de estructura?

Cada enfoque tiene su lugar dependiendo del tamaño y la complejidad del proyecto. Proyectos pequeños pueden beneficiarse de una estructura más simple, mientras que proyectos grandes y modulares pueden aprovechar una estructura más compleja.

