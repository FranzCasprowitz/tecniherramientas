<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Tecniherramientas Industriales</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background-color: #f4f4f4;
    }
    header {
      background-color: #0a3d62;
      color: white;
      padding: 20px 0;
      text-align: center;
    }
    nav {
      background-color: #3c6382;
      padding: 10px;
      text-align: center;
    }
    nav a {
      color: white;
      margin: 0 15px;
      text-decoration: none;
      font-weight: bold;
    }
    .hero {
      background: url('https://example.com/herramientas-industriales.jpg') no-repeat center center/cover;
      color: white;
      padding: 100px 20px;
      text-align: center;
    }
    .contenido {
      padding: 40px 20px;
      max-width: 1200px;
      margin: auto;
      background-color: white;
    }
    .productos {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 20px;
    }
    .producto {
      border: 1px solid #ccc;
      padding: 15px;
      text-align: center;
      border-radius: 8px;
    }
    .producto img {
      max-width: 100%;
      height: 150px;
      object-fit: cover;
    }
    .producto button {
      margin-top: 10px;
      background-color: #0a3d62;
      color: white;
      border: none;
      padding: 8px 16px;
      border-radius: 5px;
      cursor: pointer;
    }
    .producto button:hover {
      background-color: #3c6382;
    }
    .carrito {
      position: fixed;
      top: 10px;
      right: 10px;
      background-color: white;
      border: 1px solid #ccc;
      padding: 10px;
      border-radius: 5px;
      max-width: 250px;
    }
    .carrito ul {
      list-style: none;
      padding: 0;
    }
    .carrito li {
      display: flex;
      justify-content: space-between;
      margin-bottom: 5px;
    }
    .carrito button {
      background-color: red;
      border: none;
      color: white;
      padding: 2px 6px;
      border-radius: 3px;
      cursor: pointer;
    }
    form {
      display: flex;
      flex-direction: column;
      gap: 10px;
      max-width: 500px;
      margin: auto;
    }
    input, textarea {
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    button {
      padding: 10px;
      background-color: #0a3d62;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    button:hover {
      background-color: #3c6382;
    }
    .catalogo {
      text-align: center;
      margin-top: 30px;
    }
    .mapa {
      margin-top: 40px;
      text-align: center;
    }
    .mapa iframe {
      width: 100%;
      max-width: 600px;
      height: 300px;
      border: 0;
      border-radius: 10px;
    }
    .redes {
      margin-top: 20px;
      text-align: center;
    }
    .redes a {
      margin: 0 10px;
      color: #0a3d62;
      text-decoration: none;
      font-size: 20px;
    }
    footer {
      background-color: #0a3d62;
      color: white;
      text-align: center;
      padding: 20px;
      margin-top: 40px;
    }
  </style>
  <script>
    let carrito = [];

    function agregarAlCarrito(nombre) {
      carrito.push(nombre);
      actualizarCarrito();
    }

    function quitarDelCarrito(index) {
      carrito.splice(index, 1);
      actualizarCarrito();
    }

    function actualizarCarrito() {
      const lista = carrito.map((item, index) =>
        `<li>${item} <button onclick="quitarDelCarrito(${index})">X</button></li>`
      ).join('');
      document.getElementById('lista-carrito').innerHTML = lista;
    }

    function enviarCarrito() {
      const mensaje = carrito.length > 0 ? carrito.join(', ') : 'Carrito vacío';
      window.location.href = `mailto:info@tecniherramientas.com?subject=Pedido&body=Productos: ${mensaje}`;
    }
  </script>
</head>
<body>
  <div class="carrito">
    <h4>Carrito</h4>
    <ul id="lista-carrito"></ul>
    <button onclick="enviarCarrito()">Enviar pedido</button>
  </div>

  <header>
    <h1>Tecniherramientas Industriales</h1>
    <p>Soluciones en herramientas para la industria</p>
  </header>

  <nav>
    <a href="#inicio">Inicio</a>
    <a href="#productos">Productos</a>
    <a href="#contacto">Contacto</a>
  </nav>

  <section class="hero" id="inicio">
    <h2>Equipamos tu industria con herramientas de calidad</h2>
    <p>Las mejores marcas y el mejor servicio</p>
  </section>

  <section class="contenido" id="productos">
    <h2>Nuestros Productos</h2>
    <div class="productos">
      <div class="producto">
        <img src="https://example.com/taladro.jpg" alt="Taladro industrial">
        <h3>Taladro Industrial</h3>
        <p>Potente y resistente para todo tipo de materiales.</p>
        <button onclick="agregarAlCarrito('Taladro Industrial')">Agregar al carrito</button>
      </div>
      <div class="producto">
        <img src="https://example.com/llave-ajuste.jpg" alt="Llave de ajuste">
        <h3>Llave de Ajuste</h3>
        <p>Precisión y durabilidad para trabajos exigentes.</p>
        <button onclick="agregarAlCarrito('Llave de Ajuste')">Agregar al carrito</button>
      </div>
      <div class="producto">
        <img src="https://example.com/sierra-electrica.jpg" alt="Sierra eléctrica">
        <h3>Sierra Eléctrica</h3>
        <p>Corte rápido y seguro para metal y madera.</p>
        <button onclick="agregarAlCarrito('Sierra Eléctrica')">Agregar al carrito</button>
      </div>
    </div>

    <div class="catalogo">
      <h3>Descarga nuestro catálogo</h3>
      <a href="catalogo-tecniherramientas.pdf" download>
        <button>Descargar PDF</button>
      </a>
    </div>
  </section>

  <section class="contenido" id="contacto">
    <h2>Contacto</h2>
    <p>¿Deseas más información? Escríbenos o completa el siguiente formulario:</p>
    <form action="https://formsubmit.co/info@tecniherramientas.com" method="POST">
      <input type="text" name="nombre" placeholder="Tu nombre" required>
      <input type="email" name="email" placeholder="Tu correo electrónico" required>
      <textarea name="mensaje" rows="5" placeholder="Tu mensaje" required></textarea>
      <button type="submit">Enviar</button>
    </form>

    <div class="mapa">
      <h3>Ubicación</h3>
      <iframe src="https://www.google.com/maps?q=Ciudad+de+Guatemala,+zona+1&output=embed" allowfullscreen="" loading="lazy"></iframe>
    </div>

    <div class="redes">
      <h3>Síguenos</h3>
      <a href="#"><img src="https://cdn-icons-png.flaticon.com/512/733/733547.png" alt="Facebook" width="24"></a>
      <a href="#"><img src="https://cdn-icons-png.flaticon.com/512/733/733579.png" alt="Instagram" width="24"></a>
      <a href="#"><img src="https://cdn-icons-png.flaticon.com/512/733/733558.png" alt="LinkedIn" width="24"></a>
    </div>
  </section>

  <footer>
    <p>&copy; 2025 Tecniherramientas Industriales. Todos los derechos reservados.</p>
  </footer>
</body>
</html>
