# Ejercicio de Paletas de Colores con Sass

Este ejercicio demuestra la creación de paletas de colores dinámicas utilizando Sass. A partir de tres colores base, generamos automáticamente variaciones más claras y más oscuras, asegurando un contraste óptimo para el texto.

## 🎨 Características

- Generación de 3 paletas de colores diferentes (azul, rojo y verde)
- 9 variaciones por cada color:
  - 4 tonos más oscuros
  - Color base
  - 4 tonos más claros
- Contraste automático del texto (negro o blanco)
- Uso de características de Sass:
  - Variables
  - Mixins
  - Bucles
  - Cálculos de color

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
- Sass
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

### Función de Generación de Paletas (\_mixins.scss)

```scss
@use "sass:color";

@mixin generate-palette($base-color, $prefix) {
  .#{$prefix}-base-color {
    background-color: $base-color;
    color: if(
      color.channel($base-color, "lightness", $space: hsl) > 50%,
      #000,
      #fff
    );
  }
  @for $i from 1 through 4 {
    $darker: color.adjust($base-color, $lightness: -$darken-step * $i);
    $lighter: color.adjust($base-color, $lightness: $lighten-step * $i);

    .#{$prefix}-darken-#{$i} {
      background-color: $darker;
      color: if(
        color.channel($darker, "lightness", $space: hsl) > 50%,
        #000,
        #fff
      );
    }

    .#{$prefix}-lighten-#{$i} {
      background-color: $lighter;
      color: if(
        color.channel($lighter, "lightness", $space: hsl) > 50%,
        #000,
        #fff
      );
    }
  }
}
```

### Aplicación de las Paletas (styles.scss)

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
