# Auditoría del catálogo original — Ágata Beauty 2026

**Fuente:** PDF exportado de Canva, "1. Catálogo AGATA Beauty" (121 páginas A4, ~160 MB), entregado como `.rar`.
El enlace `https://canva.link/agatabeautycatalogo` no se pudo abrir desde el entorno de desarrollo (red bloqueada); todo lo de este documento sale del PDF.

## Fase 1 — Diagnóstico

### Estructura

| Páginas | Contenido |
| --- | --- |
| 1 | Portada: logo **ÁGATA beauty**, "Makeup • Skincare • Selfcare", "Catálogo 2026", Instagram **@agatabeauty_**, WhatsApp **3135496268**, lema "Belleza que nace del amor" |
| 2 | **Proceso de compra** (5 pasos, medios de pago e "IMPORTANTE") |
| 3 – 120 | Productos: una marca por página, con título de marca, sección y 1 a 3 tarjetas |
| 121 | Contraportada sin contenido |

### Productos: 225, de 25 marcas

| Marca | Productos | Marca | Productos |
| --- | ---: | --- | ---: |
| Bioaqua | 23 | Ani-k | 9 |
| Atenea | 22 | Nivea | 9 |
| Leche pal pelo | 22 | OG | 6 |
| Bloomshell | 20 | Fantiluna | 6 |
| Milagros | 19 | Garnier | 4 |
| Montoc | 15 | Lehit | 4 |
| Samy | 12 | Girly, Maybelline, Majikal | 3 c/u |
| Lula | 12 | Schwarzkopf, Tocobo, Skin 1004, Nude | 2 c/u |
| Olé | 12 | Raquel, Chap Stick | 1 c/u |
| Prosa | 11 | | |

### Categorías (secciones reales del catálogo)

El catálogo organiza cada página por **marca** y, debajo, por **sección**. En la web se usan las dos como filtros, sin inventar agrupaciones nuevas:

Cuidado capilar (57) · Rostro (39) · Cuidado facial (37) · Ojos (18) · Labios (13) · Accesorios (12) · Cejas y ojos (4) · Herramientas (4) · Cejas (3) · Fijación (2) · Papel matificante (2) · Ojos y cejas (2) · Gel fijador (2) · Kit (1) · Primer (1)

"labios" aparece en minúscula en las páginas 116–117; se unificó con "Labios".

### Datos disponibles por producto

| Dato | Disponible |
| --- | --- |
| Nombre | 225 / 225 (texto tal cual, incluida la presentación cuando el catálogo la escribe en el nombre: "x 450 ml") |
| Marca | 225 / 225 |
| Sección / categoría | 197 / 225 (ver pendientes) |
| Precio | 225 / 225 |
| Precios por tamaño, tono o versión | 19 productos (p. ej. "5gr: $27.000 · 10gr: $33.000 · 30gr: $62.000") |
| Descripción | 14 productos (kits, Gotas Mágicas, mascarillas en velo, kits de brochas…) |
| Foto del producto | 225 / 225 |
| Fotos de tonos / variantes | Las que muestra el catálogo bajo el nombre |
| Referencia / código | **No existe** en el catálogo |
| Ofertas | **No existen** (el menú "Ofertas" queda oculto) |

### Identidad visual

**Paleta** (medida sobre las páginas):

| Uso | Color |
| --- | --- |
| Fondo crema de las páginas | `#fcf3ec` / `#fdf6f0` |
| "ÁGATA" del logo | `#643011` |
| Textos de contacto / etiquetas | `#592510` |
| Sección ("Cuidado capilar", "Rostro"…) | `#764b36` |
| Títulos de marca | degradado marrón → cobre `#3c130d → #d08a72` |
| Anillo del círculo | degradado `#65312a → #bf6e58` |
| Disco detrás del producto | `#ddd7c9` |
| Estrellas y adornos de línea | `#db9d6a` / `#bf8a78` |
| Nombres y precios | negro |

**Tipografías** (leídas del PDF):

| Uso | Fuente del catálogo | En la web |
| --- | --- | --- |
| "ÁGATA" | Cormorant Garamond Bold | la misma (Google Fonts) |
| "beauty" | Dancing Script Bold | la misma (Google Fonts) |
| Títulos de marca | The Seasons Bold | Cormorant Garamond (The Seasons tiene licencia de Canva) |
| Secciones | Mont Bold | Poppins |
| Nombres y precios | Garet Bold / Regular | Poppins |
| Proceso de compra | Poppins | la misma |

**Elementos gráficos que se repiten (convertidos en componentes web):**

- Tarjeta con borde fino redondeado → `.product-card`
- Foto dentro de un círculo con anillo cobrizo sobre un disco beige → se recorta tal cual del catálogo
- Línea fina con estrella al centro → `.divider`
- Título de marca con degradado → `.brand-title`
- Adornos de línea (labial, brocha, trazos) y estrellas → extraídos del PDF a `assets/images/decor/`
- Íconos de Instagram y WhatsApp de la portada → `assets/icons/`

### Problemas de extracción y cómo se resolvieron

| Problema | Solución |
| --- | --- |
| El enlace de Canva no carga desde el entorno | Se trabajó con el PDF exportado |
| El PDF pesa ~160 MB (GitHub no acepta > 100 MB) | No se sube; `scripts/extract-catalog.py` lo procesa localmente |
| Texto en columnas (dos productos por página) | Se agrupó por el marco de cada tarjeta, usando la posición de cada texto |
| Precios con tamaño/tono en líneas separadas | Se unieron etiqueta y precio ("10 gr (translúcido, rosado y banana): $21.500") |
| Las páginas 63 (OG) muestran la misma foto para dos rubores | Se respeta: cada uno usa la foto que tiene en el catálogo |
| La página 71 (Bioaqua, mascarilla en velo) tiene otro diseño | El script reconoce también ese marco |

### Erratas corregidas a pedido de Ágata Beauty

El catálogo de Canva tenía estas erratas. Se corrigieron **solo en la web** (lista `TEXT_FIXES` en `scripts/extract-catalog.py`, que se aplica también al regenerar). Conviene corregirlas también en Canva:

| En el catálogo | En la web |
| --- | --- |
| Tratamiento cebolla y **gengibre** x30 gr | jengibre |
| **Mantaquilla corportal** x 220 ml | Mantequilla corporal |
| Papel matificante Bloom **podwer** paper | powder |
| **Definir** de rizos y ondas x 440 ml | Definidor |
| complejo **biologico** | biológico |
| centella **asiatica** | asiática |
| ácido **salicilico** | salicílico |
| **Trio** de Rubores | Trío |
| Bloom porta **cosmeticos** | cosméticos |
| Brillo labial - **Bombon** | Bombón |
| Necesidad: **Acne** | Acné |
| Tratamiento en **mascara** para pestañas | máscara |
| Brocha **retractil** | retráctil |

### Calidad de las fotografías

El PDF entregado es un **"PDF estándar"** de Canva: las fotos vienen comprimidas a una resolución media de **~90 dpi** (unos 200–380 px por foto). Ninguna está deformada (se verificó la proporción de las 225), pero al mostrarlas más grandes en la web se ven suaves o con "cuadritos" de compresión, sobre todo: Ani-k Rubor en polvo Bonita (52 dpi), Lula Bálsamo desmaquillante (54 dpi), Bioaqua Serum pure skin (61 dpi), Atenea Pigmento Soft Touch y Lip Balm Mask (63 dpi), Schwarzkopf Gel Glued y Tocobo Dúo de limpieza (64 dpi), y las pestañinas Prosa.

- Las fotos se recortan a su resolución nativa (sin ampliarlas ni recomprimirlas dos veces) y el anillo cobrizo se dibuja en vector.
- **Para que se vean nítidas** hace falta una fuente con más resolución: exportar el catálogo como **"PDF para impresión"** o entregar las fotos originales de los productos. `[INFORMACIÓN PENDIENTE]`

### Errores del catálogo original detectados en las fotos

- **Bloomshell, p. 14 — "Contorno en barra Bloom define"** usa la misma foto que "Rubor en barra Cherry Blossom" (p. 13). En la web se muestra **"Foto pendiente"** (lista `PHOTO_PENDING` del script) hasta tener la foto correcta. `[INFORMACIÓN PENDIENTE]`
- **OG, p. 63** — "Rubor mineralizado Daily" y "Rubor matte Daily" usan la misma foto (las fotos de tonos debajo sí son distintas).

## Fase 2 — Modelo de datos

Cada producto es un objeto en `data/products.json` (ver el README para el formato completo). La tabla de los 225 productos está en [`PRODUCTOS.md`](PRODUCTOS.md).

## Información pendiente `[INFORMACIÓN PENDIENTE]`

1. **Sección de 28 productos.** Estas páginas no indican sección, así que no se les asignó ninguna. Aparecen en "Todas" y en el filtro por marca:
   - Girly (p. 22), Maybelline (p. 23), Ani-k (p. 28), Majikal (p. 29), Nude (p. 111), Nivea (p. 112–115), Fantiluna (p. 118–120).
   - Si quieres, dime qué sección corresponde (p. ej. "Ojos" para las pestañinas o "Cuidado corporal" para Fantiluna) y la agrego.
2. **Indicativo del WhatsApp.** El catálogo muestra 3135496268. El enlace usa **+57** (Colombia), que se deduce del número y de los precios en pesos. Confírmalo.
3. **Referencias.** El proceso de compra dice "Guarda las referencias de los productos", pero el catálogo no tiene códigos. El mensaje de WhatsApp envía el nombre y la marca.
4. **Dominio** definitivo para `og:url` y para compartir enlaces.
5. **Ofertas.** No hay en el catálogo 2026; el menú aparece solo cuando un producto tiene `offer`.
