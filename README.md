
# 📄 Prueba de Iframe con `iframe-resizer`

Este proyecto es una página HTML que integra un iframe para mostrar contenido externo (en este caso, la página del Centro de Documentación del IMSERSO) y utiliza el plugin `iframe-resizer` para mejorar la interacción entre el iframe y la página padre.

## 🚀 Funcionalidades

- Inserción de un iframe con una URL externa.
- Comunicación bidireccional entre el iframe y la página padre mediante `iframe-resizer`.
- Ajuste automático de altura del iframe según contenido.
- Cambios dinámicos de estilo (z-index) según los mensajes recibidos.
- Actualización de la URL del navegador sin recargar la página.

## 📁 Estructura

- `iframeResizer.min.js`: Script del lado del padre que permite redimensionar y comunicarse con el iframe.
- `iframeResizer.contentWindow.min.js`: Script que debe incluirse dentro del iframe (en el sitio de destino) para habilitar la comunicación.
- `jquery.min.js`: Biblioteca jQuery para manipular el DOM.

## 🧠 Mensajes soportados

El iframe puede enviar los siguientes mensajes a la página principal:

- `"abrir"`: Eleva el `z-index` del iframe.
- `"cerrar"`: Restaura el `z-index` de los elementos.
- `"recuperar"`: Restaura la altura original del iframe.
- Número (ej. `100`): Aumenta la altura actual del iframe en esa cantidad de píxeles.
- Texto con `#`: Se interpreta como una nueva ruta en la URL y se actualiza dinámicamente en el navegador.

## 🧰 Requisitos

Para que la redimensión y comunicación funcionen correctamente:

- La página embebida (iframe) **debe incluir** el script `iframeResizer.contentWindow.min.js`.
- Ambas páginas deben estar configuradas para permitir la comunicación cross-domain, si aplica.

## 🧪 Uso

1. Asegúrate de tener los siguientes archivos JS en el mismo directorio:
   - `jquery.min.js`
   - `iframeResizer.min.js`
   - `iframeResizer.contentWindow.min.js`

2. Abre el archivo HTML en tu navegador para ver la funcionalidad en acción.

## 📎 Nota importante

El dominio embebido (`https://www.centrodedocumentacionimserso.es`) **debe tener soporte** para `iframeResizer` (es decir, debe cargar el script correspondiente y permitir la comunicación).

## 🖥️ Vista previa del iframe

```html
<iframe id="mi_iframe" src="https://www.centrodedocumentacionimserso.es/es/legislacion"
        width="100%" frameborder="0" scrolling="no" allowtransparency="true"></iframe>
```

## 📜 Licencia

Este proyecto es un ejemplo educativo y no tiene una licencia específica. Usa el contenido bajo tu propio criterio y revisa los términos del sitio embebido si vas a distribuirlo públicamente.
