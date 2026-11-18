# VetCare - Proyecto Aplicaciones Web 6to Semestre

Sistema web de gestión de citas y pacientes para la clínica veterinaria **"Huellitas"** de Quito.

Proyecto Bimestre 1 - Desarrollo de Aplicaciones Web - Escuela Politécnica Nacional


- **Sitio publicado:** `https://aplicacioneswebgr2sw2026bgr6.github.io/vetcare/`
- **Repositorio:** `https://github.com/AplicacionesWebGR2SW2026BGR6/vetcare`

## ¿Qué es VetCare?

La clínica atiende cerca de 40 mascotas al día con tres veterinarios y una recepcionista, y hoy lleva citas e historiales en papel. VetCare representa el sistema que lo reemplaza: registrar propietarios y mascotas, agendar y gestionar citas, registrar atenciones médicas y administrar veterinarios y servicios.

- **Usuarios:** recepcionista, veterinario y administrador.
- **Tecnología:** solo HTML5 y CSS3. No hay servidor, base de datos ni JavaScript; las pantallas son estáticas y los datos son de ejemplo.

## Integrantes y reparto del trabajo

Cada integrante es dueño de un módulo completo: especifica sus casos de uso en el documento, construye sus pantallas, mantiene una hoja de estilos común y lleva un entregable compartido.

| # | Integrante | Módulo | Casos de uso | Pantallas | Hoja CSS | Entregable compartido |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Juan Chugá | Acceso, estructura común y propietarios | CU-01, CU-02 | 9 | `base.css` | Repositorio, GitHub Pages y README |
| 2 | Bryan Ayala | Mascotas y atención clínica | CU-03, CU-07, CU-08 | 7 | `formularios.css` | 3.3 Diagrama de casos de uso |
| 3 | Lenin Jeréz | Citas y agenda | CU-04, CU-05, CU-06 | 6 | `componentes.css` | 3.4 Priorización y 3.5 Mapa navegacional |
| 4 | Eliana Pinargote | Veterinarios, servicios y documentación | CU-09, CU-10 | 10 | `tablas.css` | 3.1 Visión y PDF final |

## Casos de uso

| ID | Caso de uso | Actor | Integrante | Pantallas |
| --- | --- | --- | --- | --- |
| CU-01 | Iniciar sesión | Todos | 1 | `index.html`, `recepcion-inicio`, `veterinario-inicio`, `admin-inicio` |
| CU-02 | Gestionar propietarios | Recepcionista | 1 | `propietarios-*` (5) |
| CU-03 | Gestionar mascotas | Recepcionista | 2 | `mascotas-*` (5) |
| CU-04 | Agendar cita | Recepcionista | 3 | `citas-nueva` |
| CU-05 | Gestionar citas | Recepcionista | 3 | `citas-listado`, `citas-detalle`, `citas-reprogramar`, `citas-cancelar` |
| CU-06 | Consultar agenda del día | Veterinario | 3 | `agenda-dia` |
| CU-07 | Registrar atención médica | Veterinario | 2 | `atencion-registrar` |
| CU-08 | Consultar historial clínico | Veterinario | 2 | `historial-clinico` |
| CU-09 | Gestionar veterinarios | Administrador | 4 | `veterinarios-*` (5) |
| CU-10 | Gestionar servicios | Administrador | 4 | `servicios-*` (5) |

## Estructura del proyecto

```
vetcare/
├── index.html                    Inicio de sesión ............ CU-01 - 1
├── README.md                     Este archivo ......................... 1
├── css/
│   ├── base.css                  Variables, fuente, estructura, menú, botones - 1
│   ├── formularios.css           Campos y estados de validación - 2
│   ├── componentes.css           Menús de inicio, estados de cita, detalle, confirmación - 3
│   └── tablas.css                Listados, buscador, filas alternas - 4
├── img/                          Imágenes del sitio
├── docs/
│   ├── diagramas/
│   │   ├── casos-de-uso.drawio        Diagrama UML (3.3) ............ 2
│   │   └── mapa-navegacional.drawio   Mapa de pantallas (3.5) ....... 3
│   └── VetCare_Entregables.pdf   Entregables 3.1 a 3.5
└── pages/
    │   Recepcionista
    ├── recepcion-inicio.html ................................ CU-01
    ├── propietarios-listado.html ............................ CU-02
    ├── propietarios-detalle.html ............................ CU-02
    ├── propietarios-nuevo.html .............................. CU-02
    ├── propietarios-editar.html ............................. CU-02
    ├── propietarios-eliminar.html ........................... CU-02
    ├── mascotas-listado.html ................................ CU-03
    ├── mascotas-detalle.html ................................ CU-03
    ├── mascotas-nueva.html .................................. CU-03
    ├── mascotas-editar.html ................................. CU-03
    ├── mascotas-eliminar.html ............................... CU-03
    ├── citas-listado.html ................................... CU-05
    ├── citas-detalle.html ................................... CU-05
    ├── citas-nueva.html ..................................... CU-04
    ├── citas-reprogramar.html ............................... CU-05
    ├── citas-cancelar.html .................................. CU-05
    │
    │   Veterinario
    ├── veterinario-inicio.html .............................. CU-01
    ├── agenda-dia.html ...................................... CU-06
    ├── atencion-registrar.html .............................. CU-07
    ├── historial-clinico.html ............................... CU-08
    │
    │   Administrador
    ├── admin-inicio.html .................................... CU-01
    ├── veterinarios-listado.html ............................ CU-09
    ├── veterinarios-detalle.html ............................ CU-09
    ├── veterinarios-nuevo.html .............................. CU-09
    ├── veterinarios-editar.html ............................. CU-09
    ├── veterinarios-eliminar.html ........................... CU-09
    ├── servicios-listado.html ............................... CU-10
    ├── servicios-detalle.html ............................... CU-10
    ├── servicios-nuevo.html ................................. CU-10
    ├── servicios-editar.html ................................ CU-10
    └── servicios-eliminar.html .............................. CU-10
```

## Cómo se representa cada operación

Como no hay servidor, cada operación CRUD es una pantalla estática:

| Operación | Pantalla | Cómo funciona |
| --- | --- | --- |
| Create | `*-nuevo` / `*-nueva` | Formulario vacío con validación; su `action` apunta a la pantalla siguiente (normalmente el listado) y solo navega si los datos son válidos. |
| Read | `*-listado` y `*-detalle` | Tabla con datos de ejemplo, buscador (`type="search"`) y enlaces Ver, Editar y Eliminar. |
| Update | `*-editar` | El mismo formulario, precargado con `value`, `selected` y `checked`. |
| Delete | `*-eliminar` | Muestra el registro con los botones Confirmar y Cancelar. En citas, eliminar es **cancelar** y exige un motivo. |

## Reglas técnicas del enunciado del proyecto

- Solo HTML5 y CSS3. **Sin JavaScript** y sin frameworks de CSS (Bootstrap, Tailwind, etc.).
- **Sin estilos en línea** (`style="…"`): todo va en las hojas externas de `css/`.
- **Sin `novalidate`**: los formularios no se envían si hay datos inválidos.
- Documento HTML5 válido: `<!DOCTYPE html>`, `lang="es"`, `meta charset` y `meta viewport`.
- Etiquetas semánticas con la misma estructura en todas las pantallas: `header`, `nav`, `main`, `section`, `article`, `aside` y `footer`.
- Tablas accesibles: `caption`, `thead`, `tbody` y `th` con `scope`.
- Cada control con su `label` (`for`/`id`); los grupos de campos con `fieldset` y `legend`.
- En el sistema deben aparecer los tipos `email`, `tel`, `password`, `date`, `time`, `number`, `search`, `radio`, `checkbox`, `select`, `textarea` y `datalist`, y los atributos `required`, `pattern` (con `title`), `min`, `max`, `step`, `minlength`, `maxlength`, `placeholder` y `autocomplete`.
- CSS: variables en `:root`, Flexbox y Grid, al menos dos `@media` (móvil y escritorio), pseudoclases de validación (`:valid`, `:invalid`, `:user-invalid`, `:focus-visible`, `:required`), `:hover` y `:active`, selectores de atributo, `:nth-child()` en tablas, transiciones, al menos una fuente web y contraste AA.
- El sitio se prueba en **Chrome y Firefox** y debe pasar [validator.w3.org](https://validator.w3.org/) y [jigsaw.w3.org/css-validator](https://jigsaw.w3.org/css-validator/) **sin errores**.

## Convenciones del equipo

- **Nombres de archivo:** minúsculas, sin tildes ni espacios, con guion medio: `modulo-accion.html` (`mascotas-editar.html`, no `mascotas.editar.html` ni `Mascotas-Editar.html`). GitHub Pages distingue mayúsculas y Windows/XAMPP no, así que ese error solo aparece en el sitio publicado.
- **Rutas:** desde `pages/`, los estilos son `../css/base.css`, las imágenes `../img/…` y el inicio de sesión `../index.html`. Entre pantallas basta el nombre: `href="mascotas-detalle.html"`.
- **Hojas de estilo:** todas las pantallas enlazan las cuatro, en este orden: `base.css`, `formularios.css`, `tablas.css`, `componentes.css`. Cada hoja tiene un dueño; si necesitas un estilo en una hoja ajena, pídeselo a su dueño.
- **Colores, fuentes y espaciados:** solo con las variables de `:root` (por ejemplo `var(--color-primario)`), nunca escritos a mano.
- **Formularios:** `method="get"` (GitHub Pages no acepta POST) y `action` hacia la pantalla siguiente del mapa.
- **Menú:** en cada pantalla, el enlace de su sección lleva `class="activo"` (por ejemplo, las cinco pantallas de mascotas marcan "Mascotas").
- **Enlaces:** cada enlace lleva a una pantalla del mapa; en la entrega no queda ningún enlace roto.

## Reglas de negocio en HTML5

La misma regla se valida igual en todas las pantallas. Todo `pattern` lleva un `title` que explica el formato.

| Dato | Regla | Control y atributos |
| --- | --- | --- |
| Cédula | Exactamente 10 dígitos | `type="text" pattern="[0-9]{10}" maxlength="10" required` |
| Celular | 10 dígitos, empieza con 09 | `type="tel" pattern="09[0-9]{8}" required` |
| Correo | Formato válido | `type="email" required` |
| Nombres y apellidos | Solo letras y espacios, de 2 a 50 | `pattern="[A-Za-zÁÉÍÓÚÜáéíóúüÑñ ]{2,50}" minlength="2" maxlength="50" required` |
| Mascota | Un solo propietario; especie Perro, Gato, Ave, Roedor u Otro | `select` de propietario y de especie, `required` |
| Peso | De 0,1 a 120 kg, un decimal | `type="number" min="0.1" max="120" step="0.1"` |
| Fecha de nacimiento | No posterior a hoy | `type="date" max="2026-11-18"` |
| Fecha de la cita | Lunes a sábado, nunca en el pasado | `type="date" min="2026-11-18"` |
| Hora de la cita | 08:00 a 18:00, en bloques de 30 minutos | `type="time" min="08:00" max="17:30" step="1800"` |
| Cancelación de cita | Exige motivo, máximo 200 caracteres | `textarea required maxlength="200"` |
| Precio del servicio | De $1,00 a $500,00 | `type="number" min="1" max="500" step="0.01"` |
| Contraseña | Mínimo 8 caracteres, con letra y número | `type="password" minlength="8" maxlength="30" pattern="(?=.*[A-Za-z])(?=.*[0-9]).{8,30}"` |

HTML no sabe qué día es hoy ni puede bloquear los domingos. Por eso todo el sistema usa la **fecha de referencia 18/11/2026**, y estas limitaciones (más el nombre único del servicio, que tampoco se puede validar sin servidor) se declaran como supuestos en la Visión.

## Datos de ejemplo

Los datos son los mismos en todas las pantallas:

- **Veterinarios:** Dr. Pablo Andrade, Dra. Lucía Paredes, Dra. Valeria Ruiz.
- **Propietarios y mascotas:** Ana Morales (Toby, perro; Copito, roedor), Carlos Vega (Michi, gato), Sofía Herrera (Kiwi, ave), Diego Castillo (Luna, perro), Emilio Camino (ninguna mascota).
- **Usuarios del sistema:** María López (recepcionista), Jorge Salazar (administrador).

Los datos también cumplen las reglas de negocio: citas de lunes a sábado, en bloques de 30 minutos y sin dos citas del mismo veterinario a la misma hora.

## Inicio de sesión simulado

- Sin servidor no se puede verificar una contraseña: solo se valida su **formato**.
- El formulario tiene tres botones de envío, uno por rol, y cada uno lleva `formaction` hacia el menú de su rol (`pages/recepcion-inicio.html`, `pages/veterinario-inicio.html`, `pages/admin-inicio.html`).
- El correo y la contraseña **no llevan `name`**: se validan igual, pero no aparecen en la URL.
