# VetCare

Sistema web de gestión de citas y pacientes para la clínica veterinaria **"Huellitas"** de Quito.

Proyecto Bimestre 1 · Desarrollo de Aplicaciones Web · Escuela Politécnica Nacional

Entrega: **miércoles 18 de noviembre de 2026, 23:59**

- **Sitio publicado:** `https://USUARIO.github.io/vetcare/` *(pendiente)*
- **Repositorio:** `https://github.com/AplicacionesWebGR2SW2026BGR6/vetcare` *(pendiente)*
- **Documentos:** carpeta del grupo en OneDrive (Word de entregables y Excel de datos de ejemplo)

## Qué es VetCare

La clínica atiende cerca de 40 mascotas al día con tres veterinarios y una recepcionista, y hoy lleva citas e historiales en papel. VetCare representa el sistema que lo reemplaza: registrar propietarios y mascotas, agendar y gestionar citas, registrar atenciones médicas y administrar veterinarios y servicios.

- **Usuarios:** recepcionista, veterinario y administrador.
- **Tecnología:** solo HTML5 y CSS3. No hay servidor, base de datos ni JavaScript; las pantallas son estáticas y los datos son de ejemplo.

## Integrantes y reparto del trabajo

Cada integrante es dueño de un módulo completo: especifica sus casos de uso en el documento, construye sus pantallas, mantiene una hoja de estilos común y lleva un entregable compartido.

| # | Integrante | GitHub | Módulo | Casos de uso | Pantallas | Hoja CSS | Entregable compartido |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | *[Nombre]* | *[usuario]* | Acceso, estructura común y propietarios | CU-01, CU-02 | 9 | `base.css` | Repositorio, GitHub Pages y README |
| 2 | *[Nombre]* | *[usuario]* | Mascotas y atención clínica | CU-03, CU-07, CU-08 | 7 | `formularios.css` | 3.3 Diagrama de casos de uso |
| 3 | *[Nombre]* | *[usuario]* | Citas y agenda | CU-04, CU-05, CU-06 | 6 | `componentes.css` | 3.4 Priorización y 3.5 Mapa navegacional |
| 4 | *[Nombre]* | *[usuario]* | Veterinarios, servicios y documentación | CU-09, CU-10 | 10 | `tablas.css` | 3.1 Visión y PDF final |

> La nota es grupal, pero el docente puede ajustar la de un integrante si el historial de commits o una revisión oral muestran que no participó. Cada uno sube sus cambios desde su propia cuenta.

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

La priorización MoSCoW se define en el documento (entregable 3.4). Lo marcado como *Must* se construye primero y debe quedar completo.

## Estructura del proyecto

```
vetcare/
├── index.html                    Inicio de sesión ............ CU-01 · 1
├── README.md                     Este archivo ......................... 1
├── css/
│   ├── base.css                  Variables, fuente, estructura, menú, botones · 1
│   ├── formularios.css           Campos y estados de validación · 2
│   ├── componentes.css           Menús de inicio, estados de cita, detalle, confirmación · 3
│   └── tablas.css                Listados, buscador, filas alternas · 4
├── img/                          Imágenes del sitio
├── docs/
│   ├── diagramas/
│   │   ├── casos-de-uso.drawio        Diagrama UML (3.3) ............ 2
│   │   └── mapa-navegacional.drawio   Mapa de pantallas (3.5) ....... 3
│   └── VetCare_Entregables.pdf   Entregables 3.1 a 3.5, se sube al final · 4
└── pages/
    ├── plantilla.html            TEMPORAL: molde común (se borra antes de entregar)
    ├── bloques.html              TEMPORAL: bloques de contenido (se borra antes de entregar)
    │
    │   Recepcionista
    ├── recepcion-inicio.html ................................ CU-01 · 1
    ├── propietarios-listado.html ............................ CU-02 · 1
    ├── propietarios-detalle.html ............................ CU-02 · 1
    ├── propietarios-nuevo.html .............................. CU-02 · 1
    ├── propietarios-editar.html ............................. CU-02 · 1
    ├── propietarios-eliminar.html ........................... CU-02 · 1
    ├── mascotas-listado.html ................................ CU-03 · 2
    ├── mascotas-detalle.html ................................ CU-03 · 2
    ├── mascotas-nueva.html .................................. CU-03 · 2
    ├── mascotas-editar.html ................................. CU-03 · 2
    ├── mascotas-eliminar.html ............................... CU-03 · 2
    ├── citas-listado.html ................................... CU-05 · 3
    ├── citas-detalle.html ................................... CU-05 · 3
    ├── citas-nueva.html ..................................... CU-04 · 3
    ├── citas-reprogramar.html ............................... CU-05 · 3
    ├── citas-cancelar.html .................................. CU-05 · 3
    │
    │   Veterinario
    ├── veterinario-inicio.html .............................. CU-01 · 1
    ├── agenda-dia.html ...................................... CU-06 · 3
    ├── atencion-registrar.html .............................. CU-07 · 2
    ├── historial-clinico.html ............................... CU-08 · 2
    │
    │   Administrador
    ├── admin-inicio.html .................................... CU-01 · 1
    ├── veterinarios-listado.html ............................ CU-09 · 4
    ├── veterinarios-detalle.html ............................ CU-09 · 4
    ├── veterinarios-nuevo.html .............................. CU-09 · 4
    ├── veterinarios-editar.html ............................. CU-09 · 4
    ├── veterinarios-eliminar.html ........................... CU-09 · 4
    ├── servicios-listado.html ............................... CU-10 · 4
    ├── servicios-detalle.html ............................... CU-10 · 4
    ├── servicios-nuevo.html ................................. CU-10 · 4
    ├── servicios-editar.html ................................ CU-10 · 4
    └── servicios-eliminar.html .............................. CU-10 · 4
```

- **32 pantallas** (mínimo pedido: 18). El mapa navegacional debe coincidir uno a uno con ellas.
- Todas las pantallas van en `pages/`, sin subcarpetas; solo `index.html` va en la raíz.
- El Word de entregables y el Excel de datos de ejemplo viven en OneDrive. Los diagramas se editan en `docs/diagramas/` y se pegan como imagen en el Word. Al final, el PDF se sube a `docs/`.

## Cómo se representa cada operación

Como no hay servidor, cada operación CRUD es una pantalla estática:

| Operación | Pantalla | Cómo funciona |
| --- | --- | --- |
| Create | `*-nuevo` / `*-nueva` | Formulario vacío con validación; su `action` apunta a la pantalla siguiente (normalmente el listado) y solo navega si los datos son válidos. |
| Read | `*-listado` y `*-detalle` | Tabla con datos de ejemplo, buscador (`type="search"`) y enlaces Ver, Editar y Eliminar. |
| Update | `*-editar` | El mismo formulario, precargado con `value`, `selected` y `checked`. |
| Delete | `*-eliminar` | Muestra el registro con los botones Confirmar y Cancelar. En citas, eliminar es **cancelar** y exige un motivo. |

## Reglas técnicas del enunciado

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
- **Menú:** el enlace de la sección actual lleva `aria-current="page"`.
- **Enlaces:** cada enlace lleva a una pantalla del mapa; en la entrega no queda ningún `href="#"`.
- **Carpetas vacías:** Git no las sube. `img/` necesita un archivo (por ejemplo `.gitkeep`) hasta que tenga imágenes.

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

Los datos son los mismos en todas las pantallas: **Toby es siempre de Ana Morales**. La fuente es el Excel de OneDrive, donde cada dueño de módulo llena su hoja. La base es esta:

- **Veterinarios:** Dr. Pablo Andrade, Dra. Lucía Paredes, Dra. Valeria Ruiz.
- **Propietarios y mascotas:** Ana Morales (Toby, perro; Copito, roedor), Carlos Vega (Michi, gato), Sofía Herrera (Kiwi, ave), Diego Castillo (Luna, perro).
- **Usuarios del sistema:** María López (recepcionista), Jorge Salazar (administrador).

Los datos también cumplen las reglas de negocio: citas de lunes a sábado, en bloques de 30 minutos y sin dos citas del mismo veterinario a la misma hora.

## Inicio de sesión simulado

- Sin servidor no se puede verificar una contraseña: solo se valida su **formato**.
- El formulario tiene tres botones de envío, uno por rol, y cada uno lleva `formaction` hacia el menú de su rol (`pages/recepcion-inicio.html`, `pages/veterinario-inicio.html`, `pages/admin-inicio.html`).
- El correo y la contraseña **no llevan `name`**: se validan igual, pero no aparecen en la URL.
- Cualquier pantalla se puede abrir escribiendo su dirección. El acceso por rol se representa con la navegación (cada rol solo ve su menú) y se declara como supuesto en la Visión. El CU-01 describe igual el flujo real, incluido "credenciales incorrectas".

## Trabajo con Git

Cada integrante trabaja en su rama y abre un *pull request* a `main`; el Integrante 1 lo revisa y lo fusiona.

| Integrante | Rama |
| --- | --- |
| 1 | `modulo-propietarios` |
| 2 | `modulo-mascotas` |
| 3 | `modulo-citas` |
| 4 | `modulo-admin` |

```bash
git clone https://github.com/USUARIO/vetcare.git
git switch -c modulo-propietarios                          # tu rama

# trabajar, y luego:
git add pages/propietarios-*.html
git commit -m "propietarios: formulario de registro con validación"
git pull origin main                                       # traer lo último de main antes de subir
git push -u origin modulo-propietarios
```

- Commits pequeños y frecuentes, con mensajes que digan qué cambió.
- Cada uno toca solo sus pantallas y su hoja CSS.
- **Revisión cruzada** antes del cierre: 1 revisa a 2, 2 a 3, 3 a 4 y 4 a 1.

## Ver el sitio

- **En local:** con XAMPP encendido, en `http://localhost/vetcare/`, o abriendo `index.html` en el navegador.
- **Publicado:** en GitHub, *Settings → Pages → Deploy from a branch*, rama `main`, carpeta `/ (root)`.
- Revisen siempre también la versión publicada: ahí aparecen los enlaces rotos por mayúsculas.

## Cronograma

| Fecha | Hito |
| --- | --- |
| Mié 4 nov | Arranque: repositorio, estructura de carpetas y acuerdos |
| Jue 5 nov | Estructura común y variables CSS listas |
| Sáb 7 nov | Reunión de priorización MoSCoW |
| Dom 8 nov | Casos de uso, Visión y diagrama UML en borrador |
| Jue 12 nov | Pantallas *Must* publicadas en GitHub Pages |
| Vie 13 nov | Mapa navegacional |
| Lun 16 – mar 17 nov | Cierre: validadores, Chrome y Firefox, revisión cruzada y PDF |
| **Mié 18 nov, 23:59** | **Entrega:** URL del repositorio y del sitio en el aula virtual (una sola entrega por grupo) |

## Pendiente de definir

- [ ] Nombres y usuarios de GitHub de los integrantes (tabla de reparto)
- [ ] Estilo visual: paleta y fuentes, que pasan a variables en `base.css`
- [ ] Estructura común (encabezado, menú por rol, contenido, panel lateral y pie) en `plantilla.html`
- [ ] Priorización MoSCoW final
- [ ] Relaciones «include» y «extend» del diagrama de casos de uso
- [ ] Enlaces del repositorio y de GitHub Pages en este README
