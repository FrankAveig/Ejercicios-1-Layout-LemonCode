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
$base-color-1: #3498db; // Azul
$base-color-2: #e74c3c; // Rojo
$base-color-3: #2ecc71; // Verde
$darken-step: 7%; // Paso de oscurecimiento
$lighten-step: 7%; // Paso de aclarado
```

### Cálculo de Colores

El proyecto utiliza un sistema de cálculo de colores basado en:

1. **Ajuste de Luminosidad**

```scss
// Para oscurecer un color
background-color: color.adjust($base-color, $lightness: -7%); // 7% más oscuro
background-color: color.adjust($base-color, $lightness: -14%); // 14% más oscuro
background-color: color.adjust($base-color, $lightness: -21%); // 21% más oscuro
background-color: color.adjust($base-color, $lightness: -28%); // 28% más oscuro

// Para aclarar un color
background-color: color.adjust($base-color, $lightness: 7%); // 7% más claro
background-color: color.adjust($base-color, $lightness: 14%); // 14% más claro
background-color: color.adjust($base-color, $lightness: 21%); // 21% más claro
background-color: color.adjust($base-color, $lightness: 28%); // 28% más claro
```

2. **Cálculo de Contraste**

```scss
// Obtener la luminosidad del color de fondo
$luminosity: color.channel($background, "lightness", $space: hsl);

// Decidir color de texto basado en luminosidad
color: if($luminosity > 50%, #000, #fff);
```

### Generación de Paletas

Cada paleta se genera usando el mixin con diferentes prefijos:

```scss
@include generate-palette($base-color-1, "palette1"); // Paleta Azul
@include generate-palette($base-color-2, "palette2"); // Paleta Roja
@include generate-palette($base-color-3, "palette3"); // Paleta Verde
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

- Crear un sistema de paletas de color dinámico
- Implementar cálculos automáticos de luminosidad
- Asegurar un contraste óptimo para la accesibilidad
- Practicar la organización modular de código Sass

## 📚 Aprendizajes Clave

- Cálculo de variaciones de color usando porcentajes
- Determinación automática del color de texto basado en luminosidad
- Generación dinámica de paletas de color
- Organización de código Sass en módulos
