# API-Ubicaciones-Costa-Rica

## Descripción

Este repositorio contiene un archivo JSON completo con todas las provincias, cantones y distritos de Costa Rica. Es un recurso útil para desarrolladores que necesiten datos de ubicaciones costarricenses para sus aplicaciones.

## Contenido

El archivo principal `locations.json` contiene una estructura jerárquica de las divisiones administrativas de Costa Rica:

- **7 Provincias**
- **Múltiples cantones** por provincia
- **Distritos** correspondientes a cada cantón

### Provincias Incluidas

1. **San José** - 20 cantones
2. **Alajuela** - 16 cantones
3. **Cartago** - 8 cantones
4. **Heredia** - 10 cantones
5. **Guanacaste** - 11 cantones
6. **Puntarenas** - 13 cantones
7. **Limón** - 6 cantones

## Estructura del JSON

```json
{
  "1": [
    "San José",
    {
      "1": [
        "San José",
        {
          "1": "Carmen",
          "2": "Merced",
          "3": "Hospital",
          ...
        }
      ],
      ...
    }
  ],
  ...
}
```

La estructura está organizada de la siguiente manera:
- Cada provincia tiene un ID numérico (1-7)
- Cada provincia contiene un nombre y un objeto con sus cantones
- Cada cantón contiene un nombre y un objeto con sus distritos
- Cada distrito está identificado con un ID numérico y su nombre

## Uso

Puedes usar este archivo JSON directamente en tus aplicaciones para:

- Menús desplegables de selección de ubicación
- Formularios de dirección
- Aplicaciones basadas en ubicación geográfica
- Validación de datos de ubicación
- Sistemas de registro con datos de Costa Rica

### Ejemplo de uso en JavaScript

```javascript
// Cargar el archivo JSON
const locations = require('./locations.json');

// Obtener todas las provincias
const provinces = Object.entries(locations).map(([id, data]) => ({
  id,
  name: data[0]
}));

// Obtener cantones de una provincia específica (ejemplo: San José)
const cantons = Object.entries(locations['1'][1]).map(([id, data]) => ({
  id,
  name: data[0]
}));

// Obtener distritos de un cantón específico
const districts = Object.entries(locations['1'][1]['1'][1]).map(([id, name]) => ({
  id,
  name
}));
```

## Licencia

Este proyecto está licenciado bajo GNU General Public License v3.0, lo que permite el uso y modificación libre del contenido.

## Contribuciones

Las contribuciones son bienvenidas. Si encuentras algún error o deseas agregar mejoras, por favor abre un issue o envía un pull request.

---

**Nota:** Los datos están actualizados según la división territorial administrativa de Costa Rica.