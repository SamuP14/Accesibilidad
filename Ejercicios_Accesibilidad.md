
# Ejercicios de Accesibilidad Corregidos

## Ejercicio 1: Imagen sin texto alternativo
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <title>Galería de Fotos</title>
</head>
<body>
  <h1>Galería de Fotos</h1>
  <!-- Se añade el atributo 'alt' para proporcionar descripciones a las imágenes. -->
  <img src="playa.jpg" alt="Una playa con arena blanca y palmeras">
  <img src="montana.jpg" alt="Una montaña nevada bajo un cielo azul">
</body>
</html>
```

## Ejercicio 2: Formulario sin etiquetas y mensajes de error
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <title>Registro</title>
</head>
<body>
  <h1>Formulario de Registro</h1>
  <form>
    <!-- Las etiquetas 'label' describen los campos de entrada y mejoran la accesibilidad para lectores de pantalla. -->
    <label for="nombre">Nombre:</label>
    <input type="text" id="nombre" name="nombre" placeholder="Escribe tu nombre">

    <label for="correo">Correo electrónico:</label>
    <input type="email" id="correo" name="correo" placeholder="Escribe tu correo">

    <button type="submit">Enviar formulario</button>
  </form>
</body>
</html>
```

## Ejercicio 3: Botón que no es accesible para lectores de pantalla
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <title>Botón</title>
</head>
<body>
  <h1>Interacción</h1>
  <!-- Se usa 'button' en lugar de 'div' para proporcionar semántica de botón. -->
  <button onclick="alert('¡Botón presionado!')">Presionar</button>
</body>
</html>
```

## Ejercicio 4: Navegación sin estructura semántica
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <title>Navegación</title>
</head>
<body>
  <!-- Uso de 'nav' para indicar un bloque de navegación y 'ul/li' para estructurar los enlaces. -->
  <nav>
    <ul>
      <li><a href="#inicio">Inicio</a></li>
      <li><a href="#servicios">Servicios</a></li>
      <li><a href="#contacto">Contacto</a></li>
    </ul>
  </nav>
</body>
</html>
```

## Ejercicio 5: Tabla sin encabezados
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <title>Tabla</title>
</head>
<body>
  <h1>Lista de Precios</h1>
  <!-- Los encabezados 'th' describen las columnas para los lectores de pantalla. -->
  <table>
    <thead>
      <tr>
        <th>Producto</th>
        <th>Precio</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Producto 1</td>
        <td>10 USD</td>
      </tr>
      <tr>
        <td>Producto 2</td>
        <td>20 USD</td>
      </tr>
    </tbody>
  </table>
</body>
</html>
```

## Ejercicio 6: Contenido dinámico sin notificación
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <title>Notificaciones</title>
  <script>
    function mostrarNotificacion() {
      // Se usa 'aria-live' para informar a los usuarios sobre cambios dinámicos.
      document.getElementById('notificacion').innerText = 'Cambio guardado';
    }
  </script>
</head>
<body>
  <button onclick="mostrarNotificacion()">Guardar</button>
  <div id="notificacion" aria-live="polite"></div>
</body>
</html>
```

## Ejercicio 7: Contraste bajo
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <title>Texto</title>
  <style>
    body {
      background-color: #ffffff;
      color: #000000; /* Colores con contraste suficiente. */
    }
  </style>
</head>
<body>
  <h1>Texto fácil de leer</h1>
  <p>Este texto tiene un contraste adecuado con el fondo.</p>
</body>
</html>
```

## Ejercicio 8: Lista desplegable sin indicar su estado
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <title>Menú</title>
  <style>
    .submenu {
      display: none;
    }
    .menu[aria-expanded="true"] .submenu {
      display: block;
    }
  </style>
</head>
<body>
  <h1>Menú</h1>
  <!-- Uso de 'aria-expanded' para indicar el estado de expansión del menú. -->
  <div class="menu" aria-expanded="false" onclick="this.setAttribute('aria-expanded', this.getAttribute('aria-expanded') === 'false' ? 'true' : 'false')">
    Opciones
    <div class="submenu">
      <p>Opción 1</p>
      <p>Opción 2</p>
    </div>
  </div>
</body>
</html>
```

## Ejercicio 9: Página con contenido multimedia
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <title>Video Educativo</title>
</head>
<body>
  <h1>Cómo cocinar pasta</h1>
  <!-- Se añaden subtítulos para personas con discapacidades auditivas. -->
  <video controls>
    <source src="video.mp4" type="video/mp4">
    <track src="subtitulos.vtt" kind="subtitles" srclang="es" label="Español">
    Tu navegador no soporta el video.
  </video>
</body>
</html>
```

## Ejercicio 10: Página dinámica sin accesibilidad
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <title>Notificaciones</title>
  <script>
    function mostrarMensaje() {
      // Se notifica el cambio dinámico con 'aria-live'.
      document.getElementById('mensaje').innerText = '¡Nueva notificación!';
    }
  </script>
</head>
<body>
  <h1>Página de Notificaciones</h1>
  <button onclick="mostrarMensaje()">Mostrar Notificación</button>
  <div id="mensaje" aria-live="polite"></div>
</body>
</html>
```

## Ejercicio 11: Página web de un producto
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <title>Zapatos Deportivos</title>
  <style>
    body {
      font-family: Arial, sans-serif;
    }
    .precio {
      font-size: 20px;
      color: red;
    }
    .boton {
      background-color: blue;
      color: white;
      padding: 10px;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <div>
    <h1>Zapatos Deportivos</h1>
    <div>
      <!-- Texto alternativo en la imagen. -->
      <img src="zapatos.jpg" alt="Zapatos deportivos">
      <p>Los mejores zapatos para correr.</p>
      <p class="precio">Precio: $50</p>
    </div>
    <!-- Botón accesible con un rol semántico adecuado. -->
    <button onclick="alert('Producto añadido al carrito')">Añadir al carrito</button>
  </div>
</body>
</html>
```

## Ejercicio 12: Blog con múltiples secciones
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <title>Mi Blog</title>
</head>
<body>
  <!-- Estructura semántica con 'header', 'main' y 'footer'. -->
  <header>
    <nav>
      <!-- Uso de 'nav' y enlaces dentro de una lista ordenada. -->
      <ul>
        <li><a href="#inicio">Inicio</a></li>
        <li><a href="#sobre-mi">Sobre mí</a></li>
        <li><a href="#contacto">Contacto</a></li>
      </ul>
    </nav>
  </header>
  <main>
    <section>
      <h2>Artículo Reciente</h2>
      <p>Este es el contenido del artículo. Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
      <a href="#">Leer más</a>
    </section>
    <section>
      <h2>Otro Artículo</h2>
      <p>Contenido del segundo artículo. Lorem ipsum dolor sit amet.</p>
      <a href="#">Leer más</a>
    </section>
  </main>
  <footer>
    <p>&copy; 2024 Mi Blog</p>
  </footer>
</body>
</html>
```

## Ejercicio 13: Formulario de inscripción
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <title>Formulario de Inscripción</title>
</head>
<body>
  <h1>Formulario de Inscripción</h1>
  <form>
    <!-- Uso de 'label' para asociar cada campo con su descripción. -->
    <div>
      <label for="nombre">Nombre completo:</label>
      <input type="text" id="nombre" name="nombre" placeholder="Escribe tu nombre">
    </div>
    <div>
      <label for="correo">Correo electrónico:</label>
      <input type="email" id="correo" name="correo" placeholder="Escribe tu correo">
    </div>
    <div>
      <label for="pais">Seleccionar país:</label>
      <select id="pais" name="pais">
        <option value="">Selecciona tu país</option>
        <option value="mexico">México</option>
        <option value="espana">España</option>
        <option value="colombia">Colombia</option>
      </select>
    </div>
    <div>
      <button type="submit">Enviar</button>
    </div>
  </form>
</body>
</html>
```

## Ejercicio 14: Tabla de datos compleja
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <title>Reporte de Ventas</title>
</head>
<body>
  <h1>Reporte Mensual de Ventas</h1>
  <!-- Uso de 'scope' para identificar encabezados de columna y fila. -->
  <table border="1">
    <thead>
      <tr>
        <th scope="col">Producto</th>
        <th scope="col">Enero</th>
        <th scope="col">Febrero</th>
        <th scope="col">Marzo</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <th scope="row">Zapatos</th>
        <td>100</td>
        <td>150</td>
        <td>200</td>
      </tr>
      <tr>
        <th scope="row">Camisas</th>
        <td>200</td>
        <td>250</td>
        <td>300</td>
      </tr>
    </tbody>
  </table>
</body>
</html>
```

## Ejercicio 15: Menú interactivo
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <title>Menú Interactivo</title>
  <style>
    .submenu {
      display: none;
    }
    .menu[aria-expanded="true"] .submenu {
      display: block;
    }
  </style>
</head>
<body>
  <h1>Menú de Opciones</h1>
  <!-- Uso de 'aria-expanded' para indicar el estado de expansión. -->
  <div class="menu" aria-expanded="false" onclick="this.setAttribute('aria-expanded', this.getAttribute('aria-expanded') === 'false' ? 'true' : 'false')">
    <p>Opciones</p>
    <div class="submenu">
      <p>Opción 1</p>
      <p>Opción 2</p>
      <p>Opción 3</p>
    </div>
  </div>
</body>
</html>
```
