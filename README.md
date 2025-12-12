# 🇨🇷 API de Ubicaciones de Costa Rica

Una API sencilla con todas las provincias, cantones y distritos de Tiquicia.  Ideal para formularios, aplicaciones web y cualquier proyecto que necesite datos de ubicaciones costarricenses.

## ¿Qué trae esto?

Este repo contiene un archivo JSON completo con toda la división territorial administrativa de Costa Rica: 
- **7 provincias**
- **82 cantones**
- **488 distritos**

Los datos están organizados de forma jerárquica para que los puedas usar fácil en tu aplicación.

## ¿Cómo lo uso?

### Usando el JSON directamente

Podés cargar el archivo `locations.json` directamente en tu proyecto.  El formato es bien sencillo:

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
          "3": "Hospital"
          // ... más distritos
        }
      ]
      // ... más cantones
    }
  ]
  // ... más provincias
}
```

### Estructura de los datos

- **Primer nivel**: Provincias (1-7)
- **Segundo nivel**: Cantones dentro de cada provincia
- **Tercer nivel**:  Distritos dentro de cada cantón

### Ejemplo de uso

Revisá la carpeta `ejemplo/` donde hay un demo en HTML mostrando cómo hacer selectores dependientes (provincia → cantón → distrito).

### Desde un CDN (GitHub Raw)

Podés acceder al JSON directamente desde tu navegador o aplicación:

```javascript
fetch('https://raw.githubusercontent.com/AndresSalch/API-Ubicaciones-Costa-Rica/main/locations.json')
  .then(response => response.json())
  .then(data => {
    console.log(data);
    // Aquí hacés tu magia
  });
```

## Casos de uso

- Formularios de registro con direcciones
- Sistemas de entregas y logística
- Aplicaciones de comercio electrónico
- Análisis demográficos y estadísticos
- Cualquier app que necesite ubicaciones de Costa Rica

## Contribuciones

Si encontrás algún error o querés agregar algo, mandá un pull request.  Toda ayuda es bienvenida, mae.

## Licencia

Este proyecto está bajo la licencia GNU General Public License v3.0 - mirá el archivo [LICENSE](LICENSE) para más detalles. 

## Contacto

¿Alguna duda o sugerencia? Abrí un issue en el repo. 
