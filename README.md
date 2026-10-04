# La Despensa — web del restaurante (Las Arenas)

Web de una sola página para **La Despensa**, restaurante de cocina de producto en Areeta / Las Arenas (Getxo, Bizkaia): producto fresco de temporada, verduras de Navarra, pescados del Cantábrico y carnes maduradas.

**Para quién:** comensales que buscan la carta, la ubicación o reservar mesa. Para quien mantiene el sitio, es una página estática muy sencilla de editar.

**En vivo:** https://acardenal-partners.github.io/la-despensa-web/ (GitHub Pages).

---

## Estado actual (octubre 2026)

- **Último (y único) commit:** 13-07-2026 — `Add files via upload`.
- Página completa y funcional:
  - Cabecera con vídeo de fondo y efecto *parallax* suave.
  - «Nuestra cocina» (presentación).
  - «La carta» con precios: entrantes y raciones, ensaladas, verduras de Navarra, pescados y mariscos, carnes y postres.
  - «Dicen de nosotros»: tres testimonios de clientes.
  - Formulario de reserva (fecha, comensales, hora) que **redirige al sistema de reservas CoverManager** del restaurante en una pestaña nueva.
  - «Encuéntranos»: dirección, teléfono, enlace de reservas online y mapa de Google embebido.
- Sin dominio propio (usa la URL de GitHub Pages).

---

## Stack y estructura

- **HTML + CSS + JavaScript** puro, sin frameworks ni build. Todo en un único archivo.
- Tipografías Cormorant Garamond + Jost (Google Fonts).
- Animaciones de aparición con `IntersectionObserver`.

```
.
└── index.html   # Toda la web: estilos, contenido, carta y scripts
```

Los tres vídeos de fondo se cargan desde una CDN externa (no están en el repo), y el mapa es un `iframe` de Google Maps.

---

## Cómo arrancarlo desde cero

1. Clonar:
   ```bash
   git clone https://github.com/acardenal-partners/la-despensa-web.git
   cd la-despensa-web
   ```
2. Abrir `index.html` en el navegador, o servir la carpeta:
   ```bash
   npx serve .          # o:  python -m http.server 8000
   ```
3. Editar con cualquier editor de texto (VS Code recomendado):
   - **Carta y precios:** sección «La carta» del HTML (cada plato es una línea con nombre y precio).
   - **Horas de reserva / comensales:** opciones del formulario `#fres`.
   - **Enlace de reservas:** URL de CoverManager, que aparece dos veces (en el formulario y en «Encuéntranos»).

---

## Configuración

No hay variables de entorno, claves ni dependencias que instalar.

---

## Despliegue y servicios externos

- **GitHub Pages**: *Settings → Pages → Deploy from a branch → `main` / root*. Cada push a `main` publica en uno o dos minutos.
- **CoverManager**: motor de reservas del restaurante (la web solo redirige a él).
- **Google Maps** (iframe de ubicación) y **Google Fonts**.
- **CDN externa** para los vídeos de fondo.

---

## Pendientes conocidos

- Mover los vídeos de fondo a un alojamiento controlado (o al propio repo, comprimidos) para no depender de la CDN externa.
- Añadir metadatos para redes (Open Graph), favicon y datos estructurados `Restaurant` de schema.org para SEO local.
- Valorar un dominio propio para el restaurante.
- Revisar periódicamente que la carta y los precios estén al día.
