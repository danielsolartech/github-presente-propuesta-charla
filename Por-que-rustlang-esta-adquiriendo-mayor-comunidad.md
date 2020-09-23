# ¿Por qué Rustlang está adquiriendo mayor comunidad?

## Contenido
* [Objetivo](#Objetivo)
* [Descripción](#Descripción)
* [Guión](#Guión)
* [Ejemplos](#Ejemplos)

## Objetivo
* Incentivar el aprendizaje del lenguaje de programación Rustlang, contribuyendo a la comunidad en proyectos open source.

## Descripción
Explicación del auge del lenguaje de programación Rust en el ámbito del bajo nivel en el desarrollo de software; al igual, las ventajas y desventajas respecto a otros lenguajes de programación como C/C++ o Go.

Por otro lado, se busca incentivar a los oyentes sobre aprender un lenguaje de programación de backend como Rust, explicando su sintaxis básica en live coding, y mencionando proyectos grandes que usan Rust en su desarrollo como Microsoft, Discord, Mozilla o Samsung.

## Guión
Antes de ir al tema de la charla, comenzaré explicándoles qué es Rustlang. Rustlang es un lenguaje de programación compilado, es decir, el código que escribas en el se pasa a lenguaje de máquina; este es multiparadigma y su propósito es ser un lenguaje seguro, concurrente y práctico. Mozilla comenzó a patrocinarlo en 2009 y para 2012 se lanzó el compilador de Rustlang escrito en Rustlang, llamado rustc.

Ahora bien, Rustlang es un lenguaje de esta época, pues su primera versión estable (La 1.0) fue lanzada el 15 de Mayo de 2015.

Rustlang hasta el momento es considerado "inmaduro", puesto que en sus primeras versiones cambiaba demasiado una respecto a la otra haciendo que fuese más difícil seguir una ruta de aprendizaje.

Hablemos un poco sobre el "Garbage Collector" de Rustlang, antes quiero aclarar que Rustlang no posee un Garbage Collector, sino que se trata de un "Ownership"; este permite que sea mucho más rápido respecto a otros lenguajes como Go; sin embargo, esto no se nota hasta que se tenga una aplicación que requiera un enorme consumo de memoria.

A todo esto, ¿Qué proyectos usan Rustlang? Discord es un gran ejemplo, esta empresa pasó de utilizar Go a utilizar Rust en algunas de sus características para mejorar la latencia entre el servidor y sus usuarios; esto fue explicado en un artículo publicado en su blog oficial (https://blog.discord.com/why-discord-is-switching-from-go-to-rust-a190bbca2b1f). Otro gran ejemplo es la alianza entre Mozilla y Samsung para hacer el navegador web Servo paralelo a Firefox.

No podemos dejar atrás a Microsoft, puesto que este usa Rust en Microsoft Azure IoT Edge (una plataforma usada para ejecutar servicios de Azure e inteligencia articial en dispositivos de IoT) para algunos componentes. También tenemos el ya conocido Deno, el nuevo entorno de ejecución de JavaScript que usa el motor V8 de Google.

Con Discord podemos hacer infinidad de cosas desde un sistema operativo o una simple aplicación de consola; también aplicaciones de escritorio, videojuegos, páginas web o incluso utilizarlo en conjunto a JavaScript usando WebAssembly.

A continuación veremos unos pequeños ejemplos de código en Rustlang. ([Ver Ejemplos](#Ejemplos))

## Ejemplos

### Ejemplo 1
Hola mundo.

```rust
fn main() {
  println!("¡Hola mundo!");
}
```

### Ejemplo 2
Leer la línea actual usando la dependencia `rustyline`.

Dependencias (Cargo.toml)
```toml
[dependencies]
rustyline = "6.2.0"
```

Código
```rust
use rustyline::*;

fn main() {
  // Creando el editor de rustyline.
  let mut editor = Editor::<()>::new();

  // Leyendo la línea actual.
  let linea = editor.readline("Ingresa un mensaje: ");

  // Capturando el mensaje o un error.
  match linea {
    Ok(mensaje) => {
      println!("El mensaje ingresado fue: {:?}", mensaje);
    },
    Err(error) => {
      println!("Error capturado: {:?}", error);
    },
  }
}
```
