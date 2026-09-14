# Espino Landscaping & Remodeling — sitio web

Sitio estático de una sola página. No necesita servidor, base de datos ni compilación.

```
index.html        el sitio completo (HTML, CSS y JavaScript en un archivo)
data/site.json    los textos editados y la lista de fotos
media/            las fotos y videos subidos
```

---

## 1. Publicar en GitHub Pages

1. Crear un repositorio nuevo en GitHub, por ejemplo `espino-web`. **Público** (GitHub Pages gratis requiere repositorio público).
2. Subir estos tres archivos y las dos carpetas, tal como están.
3. En el repositorio: **Settings → Pages**.
4. En *Source* escoger **Deploy from a branch**, rama `main`, carpeta `/ (root)`. Guardar.
5. En un minuto la página queda en `https://<usuario>.github.io/espino-web/`.

Ese es el enlace para mostrarle a Leo.

## 2. Entrar como administrador

El panel de administrador no se ve por ningún lado hasta que usted entre. Leo puede abrir el sitio sin ver un solo botón de edición.

1. Abrir el sitio y agregar `#/admin` al final de la dirección.
   Ejemplo: `https://<usuario>.github.io/espino-web/#/admin`
2. Llenar los tres campos:
   - **Repositorio:** `<usuario>/espino-web`
   - **Rama:** `main`
   - **Token:** ver el paso siguiente
3. Presionar **Entrar**.

### Cómo sacar el token

1. En GitHub: **Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token**.
2. **Repository access:** *Only select repositories* → escoger solo `espino-web`.
3. **Permissions → Repository permissions → Contents:** ponerlo en **Read and write**. Nada más.
4. Escoger una fecha de vencimiento (90 días está bien; se renueva cuando caduque).
5. Copiar el token y pegarlo en el sitio.

El token se guarda **solo en el navegador de esa computadora**. No viaja a ningún otro lado, no está dentro del repositorio, y solo sirve para ese repositorio. Si presta o pierde la computadora, entre a `#/admin` y presione **Olvidar este dispositivo**, o revoque el token desde GitHub.

## 3. Editar el sitio

Ya adentro aparece la barra café de **Modo administrador**.

- **Editar textos:** cada texto editable tiene un botón "Editar" al lado. Se abre un panel con español e inglés. Los datos de contacto (nombre, teléfono, correo, dirección) traen un solo cuadro porque se leen igual en los dos idiomas.
- **Subir fotos y videos:** al final de cada sección. Se escoge el servicio, se pone una descripción opcional y se sube. Máximo 20 MB por archivo.
- **★** marca lo que sale en la página principal. **Portada** marca la foto que sale arriba del todo, una por oficio. Lo demás aparece en la página de Trabajos.
- **Ver como visitante** muestra la página tal como la ve un cliente.
- **Ver con fotos de ejemplo** enciende o apaga las ilustraciones de muestra. Se apagan solas en cuanto haya fotos reales.

Nada de esto se publica todavía. Cuando termine, presione **Publicar cambios**. Eso guarda todo en el repositorio y GitHub reconstruye el sitio en menos de un minuto.

### Traducción automática

Los botones **Traducir ES → EN** y **Traducir EN → ES** funcionan aquí sin Claude: llaman al servicio gratuito de MyMemory desde el navegador, sin llave ni cuenta. El resultado pasa después por un glosario del oficio que corrige las palabras que la traducción automática suele arruinar — *lechada* no sale como "milk", *jardinera* no sale como "gardener", *siding* y *mulch* se quedan como están.

Aun así **lea el resultado antes de guardar.** No es tan bueno como una traducción hecha por Claude.

Límite: unos 5,000 caracteres al día por cada conexión a internet. Es de sobra para editar textos de vez en cuando. Si se acaba, el panel lo avisa y se puede escribir el cuadro a mano.

## 4. Pasar a Cloudflare con dominio propio

1. Comprar el dominio en **Cloudflare Registrar** (vende al costo, alrededor de 10–11 USD al año, con privacidad de WHOIS y SSL incluidos).
2. En Cloudflare: **Workers & Pages → Create → Pages → Connect to Git** y escoger este mismo repositorio.
3. *Framework preset:* None. *Build command:* vacío. *Output directory:* `/`.
4. En **Custom domains** agregar el dominio.

El panel de administrador sigue funcionando igual, porque escribe en el repositorio de GitHub y Cloudflare se actualiza solo con cada cambio.

## 5. Antes de promocionar el sitio

- Agregar el número de licencia **MHIC** en el pie de página (el espacio ya está listo en el editor). En Maryland, contratar remodelación residencial sin esa licencia deja al contratista sin poder cobrar por la vía legal.
- Completar la ciudad y el código postal de la dirección.
- Pedir permiso al cliente antes de publicar fotos de su casa.
