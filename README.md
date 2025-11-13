# 🚴 Visualización 3D Holográfica de SityCleta Las Palmas

## Autores y asignatura
**Autor:** Alberto José Rodríguez Ruano  
**Universidad:** ULPGC - GII (Grado en Ingeniería Informática)  
**Asignatura:** Informática Gráfica  

---

## Descripción del proyecto

Visualización 3D interactiva en tiempo real del sistema de bicicletas compartidas **SityCleta** de Las Palmas de Gran Canaria, usando **Three.js** y shaders personalizados para crear un efecto holográfico, partículas ambientales y animaciones basadas en datos reales de viajes.

---

## Enlace al código en codesandbox.io

[Clica aquí](https://codesandbox.io/p/sandbox/ig2526-s8-forked-jzwvln)

---

## Video de la demo

Aquí se muestra un video demostrativo de la demo (haz clic sobre él para ver el video):

[![Ver demo](https://img.youtube.com/vi/Q5NDQBxpzH0/0.jpg)](https://youtu.be/Q5NDQBxpzH0)

---

## Controles de la demo

- **Orbitar / Zoom / Pan:** Ratón con OrbitControls
- **Tooltip:** Hover sobre estaciones muestra nombre y datos en tiempo real
- **Barra holográfica:** Altura = nº de bicicletas activas
- **Estadísticas en panel:** Viajes activos y estación más usada
- **Cometas animados:** Rutas de los viajes recientes con trail de partículas
- **Luciérnagas:** Efecto de partículas circulares sólo visibles de 19:00 a 06:00 (ciclo día/noche simulable)

---

## Explicación del código

### 1. Importaciones y setup
- [x] `THREE` para renderizado 3D
- [x] `OrbitControls` para camara interactiva
- [x] `GLTFLoader` para importar modelo de cometa

### 2. Visual y ciclo día/noche
- Fondo, luces e interpolación de color de cielo depende del "reloj" virtual
- Luciérnagas con textura circular, blending aditivo y movimiento suave solo visibles en horario nocturno
- Panel de reloj estilizado vía CSS-in-JS y muestra hora, día/noche

### 3. Datos y funcionalidad
- Carga y parsing de CSVs de estaciones y viajes históricos
- Estaciones representadas con barra holográfica, interacción tooltip con estadística en tiempo real
- Cada viaje: línea curva + cometa animado que deja partículas de estela
- Limpiado periódico de objetos antiguos para rendimiento

### 4. Efectos visuales
- **Shaders holográficos**: barras con distorsión y efecto fresnel animado
- **Luciérnagas**: sistema de partículas con textura y halo circular
- **Animaciones suaves**: todo animado vía requestAnimationFrame

---

## Estructura de datos

- **estaciones:** array de objetos `{ nombre, lat, lon }`
- **viajes:** array de objetos `{ inicio, fin, origen, destino }`
- **cometas:** array de objetos animados para cada viaje en curso

---

## Tecnologías utilizadas

- Three.js
- JavaScript ES6+
- Canvas API (para texturas de partículas)
- HTML5 + CSS3 (incluye estilos dinámicos generados en JS)

