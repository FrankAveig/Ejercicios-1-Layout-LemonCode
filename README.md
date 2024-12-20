# Ejercicio de Paletas de Colores con Sass

Este ejercicio demuestra la creación de paletas de colores dinámicas utilizando Sass. A partir de tres colores base, generamos automáticamente variaciones más claras y más oscuras, asegurando un contraste óptimo para el texto.

## 🎨 Características

- Generación de 3 paletas de colores diferentes (azul, rojo y verde)
- 9 variaciones por cada color:
  - 4 tonos más oscuros
  - Color base
  - 4 tonos más claros
- Contraste automático del texto (negro o blanco)
- Uso de características modernas de Sass:
  - Módulo de color (@use "sass:color")
  - Variables
  - Mixins
  - Bucles

## 📁 Estructura del Proyecto

```
.
├── scss/
│   ├── _variables.scss  # Variables globales (colores base y pasos)
│   ├── _mixins.scss     # Mixins para generar paletas
│   └── styles.scss      # Archivo principal de estilos
└── index.html          # Estructura HTML
```

## 🛠️ Tecnologías Utilizadas

- HTML5
- Sass (con funciones modernas de color)
- Variables CSS
- Flexbox para el layout

## 📝 Detalles de Implementación

### Variables (\_variables.scss)

```scss
$base-color-1: #3498db;
$base-color-2: #e74c3c;
$base-color-3: #2ecc71;
$darken-step: 7%;
$lighten-step: 7%;
```

### Funciones Modernas de Sass

El proyecto utiliza las funciones más recientes de Sass para manipulación de colores:

1. **color.adjust()**

```scss
// Para oscurecer
$darker: color.adjust($base-color, $lightness: -$darken-step);
// Para aclarar
$lighter: color.adjust($base-color, $lightness: $lighten-step);
```

2. **color.channel()**

```scss
// Obtener la luminosidad en espacio HSL
color.channel($color, "lightness", $space: hsl)
```

### Contraste Automático

El texto se ajusta automáticamente entre negro y blanco según la luminosidad del fondo:

```scss
color: if(
  color.channel($background, "lightness", $space: hsl) > 50%,
  #000,
  #fff
);
```

### Mixins (\_mixins.scss)

El mixin principal `generate-palette` toma un color base y genera:

- Una clase para el color base
- 4 variaciones más oscuras (usando darken)
- 4 variaciones más claras (usando lighten)

### Generación de Paletas

Cada paleta se genera usando el mixin con diferentes prefijos:

```scss
@include generate-palette($base-color-1, "palette1");
@include generate-palette($base-color-2, "palette2");
@include generate-palette($base-color-3, "palette3");
```

## 🚀 Cómo usar

1. Clona el repositorio
2. Instala las dependencias:
   ```bash
   npm install
   ```
3. Ejecuta el proyecto:
   ```bash
   npm run dev
   ```

## 🎯 Objetivos del Ejercicio

- Implementar funciones modernas de color de Sass
- Crear un sistema de paletas de color dinámico
- Asegurar un contraste óptimo para la accesibilidad
- Practicar la organización modular de código Sass

## 📚 Aprendizajes Clave

- Uso de funciones modernas de Sass (color.adjust, color.channel)
- Cálculo automático de contraste para texto
- Generación dinámica de variaciones de color
- Organización de código Sass en módulos
