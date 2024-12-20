# Ejercicio de Paletas de Colores con Sass

Este ejercicio demuestra la creación de paletas de colores dinámicas utilizando Sass. A partir de tres colores base, generamos automáticamente variaciones más claras y más oscuras.

## 🎨 Características

- Generación de 3 paletas de colores diferentes (azul, rojo y verde)
- 9 variaciones por cada color:
  - 4 tonos más oscuros
  - Color base
  - 4 tonos más claros
- Uso de características avanzadas de Sass:
  - Variables
  - Mixins
  - Bucles
  - Funciones de color

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

- Practicar el uso de Sass para crear sistemas de color dinámicos
- Implementar funciones de color de Sass
- Crear código reutilizable usando mixins
- Organizar código Sass en módulos

## 📚 Aprendizajes Clave

- Uso de funciones de color en Sass (darken/lighten)
- Implementación de mixins para generar clases dinámicas
- Organización modular de código Sass
- Manipulación dinámica de colores
