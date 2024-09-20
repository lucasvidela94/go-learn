# Notas sobre main.go, paquetes y funciones en Go

## Archivo main.go

1. **Importancia del nombre:**
   - Go busca por defecto un archivo llamado `main.go`.
   - Es una convención, no una regla estricta.

2. **Paquete main:**
   - El archivo `main.go` típicamente contiene `package main`.
   - `package main` indica que este es el paquete ejecutable principal.

## Paquetes en Go

1. **Declaración de paquetes:**
   - Cada archivo Go debe comenzar con una declaración de paquete.
   - Ejemplo: `package authentication`

2. **Alcance del paquete:**
   - Todo el código en el archivo pertenece al paquete declarado.
   - Los paquetes ayudan a organizar y modularizar el código.

## Funciones en Go

1. **Declaración de funciones:**
   - Se usa la palabra clave `func`.
   - Ejemplo básico:
     ```go
     func main() {
         // código aquí
     }
     ```

2. **Funciones como valores:**
   - Las funciones pueden ser asignadas a variables.
   - Ejemplo:
     ```go
     hello := func() {
         fmt.Println("Hola!!")
     }
     hello() // Llama a la función
     ```

3. **Función main:**
   - `func main()` es el punto de entrada de un programa Go ejecutable.
   - Debe estar en el paquete `main`.

## Punto importante

- La combinación de `package main` y `func main()` es esencial para crear un programa ejecutable en Go.

