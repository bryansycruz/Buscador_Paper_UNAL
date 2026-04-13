# Buscador de Papers Academicos

Coleccion de notebooks para buscar, resumir y descargar papers cientificos desde las principales bases de datos academicas abiertas. Diseñado para investigadores que necesitan explorar literatura cientifica sin costo y sin instalar nada en su computador.

Aporte: Bryan Yamá Cruz

---

## Bases de datos disponibles

| Notebook | Fuente | Disciplinas | Papers disponibles |
|---|---|---|---|
| `arvix.ipynb` | arXiv | Fisica, Matematicas, CS, Economia, Estadistica, Construcción | +2 millones |
| `semantic_scholar.ipynb` | Semantic Scholar | Todas las disciplinas | +200 millones |
| `openalex.ipynb` | OpenAlex | Todas las disciplinas | +250 millones |
| `pubmed.ipynb` | PubMed / NCBI | Medicina, Biologia, Salud | +36 millones |

Todas las fuentes son **gratuitas, abiertas y sin registro obligatorio**.

---

## Como ejecutarlo en Google Colab

Google Colab es una plataforma gratuita de Google que permite ejecutar notebooks de Python directamente en el navegador, sin instalar nada.

### Requisitos
- Cuenta de Google (Gmail)
- Navegador web (Chrome, Firefox, Edge)

### Pasos

**1. Abrir Google Colab**

Ve a [colab.research.google.com](https://colab.research.google.com) e inicia sesion con tu cuenta de Google.

**2. Subir el notebook**

Hay dos formas:

*Opcion A — Subir desde tu computador:*
```
Archivo > Subir notebook > selecciona el archivo .ipynb
```

*Opcion B — Desde Google Drive:*
1. Sube el archivo `.ipynb` a tu Google Drive
2. Haz doble clic sobre el archivo en Drive
3. Se abrira automaticamente en Colab

**3. Ejecutar las celdas en orden**

Una vez abierto el notebook, ejecuta cada celda de arriba hacia abajo:

- Haz clic en el boton **▶** a la izquierda de cada celda, o
- Usa el atajo de teclado **Ctrl + Enter** para ejecutar la celda actual
- Usa **Shift + Enter** para ejecutar y avanzar a la siguiente

> La primera vez que ejecutes el Paso 1 (instalacion) puede tardar 1-2 minutos.

**4. Usar la interfaz de busqueda**

Cuando llegues al Paso 4, apareceran los controles interactivos:

1. Escribe tu termino de busqueda en el campo de texto
2. Selecciona el area de conocimiento (opcional)
3. Ajusta la cantidad de papers con el deslizador
4. Haz clic en **Buscar papers**
5. Espera los resultados (10-30 segundos segun la busqueda)

**5. Descargar los resultados**

Una vez aparezcan los resultados, se habilitaran dos botones:

- **Descargar CSV** — Tabla con todos los datos (se abre en Excel)
- **Descargar PDF** — Reporte formateado listo para compartir

El archivo se descargara automaticamente a la carpeta de Descargas de tu PC.

### Advertencias importantes en Colab

> Si la sesion de Colab lleva mucho tiempo inactiva (aprox. 90 minutos), el entorno se reinicia y hay que volver a ejecutar las celdas desde el Paso 1. Los archivos descargados al PC no se pierden.

> Colab tiene un limite de uso gratuito diario. Para investigacion normal es mas que suficiente.

---

## Como ejecutarlo en Kaggle

Kaggle es una plataforma de ciencia de datos de Google con entorno gratuito de notebooks. Tiene algunas ventajas sobre Colab: las sesiones duran hasta 12 horas y no requiere cuenta de Google.

### Requisitos
- Cuenta en [kaggle.com](https://www.kaggle.com) (gratuita, se puede registrar con Google o email)
- Verificacion de telefono para activar internet en los notebooks

### Pasos

**1. Crear una cuenta en Kaggle**

Ve a [kaggle.com/account/login](https://www.kaggle.com/account/login) y registrate. Si ya tienes cuenta, inicia sesion.

**2. Subir el notebook**

1. En el menu lateral, haz clic en **Code**
2. Haz clic en el boton **+ New Notebook**
3. En la parte superior del editor, haz clic en **File > Import Notebook**
4. Selecciona el archivo `.ipynb` desde tu computador

**3. Activar acceso a internet (paso obligatorio)**

Por defecto Kaggle bloquea internet en los notebooks. Para habilitarlo:

1. En el panel derecho busca la seccion **Settings**
2. Activa el interruptor **Internet > On**

> Sin este paso las celdas de instalacion y busqueda fallaran.

**4. Ejecutar el notebook**

Ejecuta las celdas en orden con **Shift + Enter** o usa el boton **Run All** en la barra superior para ejecutarlas todas de una vez.

**5. Descargar los resultados**

En Kaggle la descarga funciona diferente a Colab. Cuando se genere el archivo:

1. En el panel derecho, abre la seccion **Output**
2. El archivo CSV o PDF aparecera listado ahi
3. Haz clic en el icono de descarga junto al archivo

> Alternativa: en la ultima celda, despues de `exportar_csv(resultados)`, agrega `print('Listo')` y busca el archivo en el panel Output.

### Advertencias importantes en Kaggle

> Kaggle no soporta `google.colab.files.download()`. Si aparece un error con esa funcion, usa el panel Output del lado derecho para descargar los archivos generados.

> Las sesiones gratuitas de Kaggle duran hasta 12 horas continuas, mas que Colab.

---

## Comparacion de plataformas

| Caracteristica | Google Colab | Kaggle |
|---|---|---|
| Costo | Gratuito | Gratuito |
| Instalacion requerida | No | No |
| Duracion de sesion | ~90 min inactivo | 12 horas |
| RAM disponible | ~12 GB | ~16 GB |
| Integracion con Drive | Si | No |
| Descarga de archivos | Automatica en el navegador | Panel Output |
| Requiere internet activado | No | Si (activar manualmente) |
| Recomendado para | Uso rapido, integracion Google | Sesiones largas, mas memoria |

---

## Que hace cada notebook

### Funcionalidades comunes

Todos los notebooks comparten las mismas funcionalidades:

- **Busqueda por palabras clave** con filtros por area o disciplina
- **Resumen automatico** del abstract de cada paper (tecnologia LSA, sin costo)
- **Abstract completo** disponible con un clic en cada resultado
- **Exportar a CSV** para abrir en Excel o Google Sheets
- **Exportar a PDF** con todos los papers formateados

### Funcionalidades especificas

**arXiv** (`arvix.ipynb`)
- Filtro por categoria: cs.AI, cs.LG, fisica, matematicas, economia, estadistica
- Ordenar por relevancia o fecha de publicacion
- Enlace directo al PDF del preprint

**Semantic Scholar** (`semantic_scholar.ipynb`)
- Muestra el **numero de citas** de cada paper
- Ordenar por **mas citados**, mas recientes o relevancia
- Filtro por area: Computer Science, Medicine, Biology, Physics, etc.
- Filtro por anio minimo de publicacion
- Detecta automaticamente si el paper tiene PDF de acceso abierto

**OpenAlex** (`openalex.ipynb`)
- La base de datos mas grande: +250 millones de trabajos
- Filtro por **tipo de documento**: articulo, revision, libro, tesis, dataset
- Filtro por **rango de anios** (desde/hasta)
- Opcion para mostrar **solo papers con PDF gratuito**
- Muestra **conceptos tematicos** asociados a cada paper
- Hasta 200 resultados por busqueda

**PubMed** (`pubmed.ipynb`)
- Especializado en **medicina, biologia y ciencias de la salud**
- Soporta **sintaxis avanzada**: `AND`, `OR`, `[tiab]`, `[au]`, `[jour]`
- Muestra **terminos MeSH** (vocabulario medico controlado)
- Opcion para mostrar solo articulos con **texto completo gratuito en PMC**
- Enlace directo a PubMed Central cuando el articulo esta disponible

---

## Guia de busqueda avanzada

### Busquedas efectivas en todos los notebooks

```
# Busqueda simple
machine learning

# Combinar terminos (todos deben aparecer)
deep learning medical imaging

# Busqueda de frase exacta (entre comillas en el campo de texto)
"neural network" "image segmentation"
```

### Solo en PubMed (sintaxis especial)

```
# Buscar en titulo y abstract
COVID-19[tiab] AND vaccine[tiab]

# Buscar por autor
Smith J[au]

# Buscar en revista especifica
Nature[jour] AND CRISPR

# Combinar con anio
diabetes[tiab] AND 2020:2024[pdat]
```

---

## Preguntas frecuentes

**Los papers estan en ingles, como puedo leerlos?**
Pega el abstract en el Traductor de Google o usa DeepL. Ambos son gratuitos y funcionan bien con texto cientifico.

**Puedo descargar el PDF completo del paper?**
Los notebooks te llevan al enlace del paper. Si el paper es open access (acceso abierto), el PDF esta disponible gratis. Si no, la universidad puede tener acceso institucional o puedes buscar el DOI en Unpaywall.

**Cual notebook debo usar segun mi area?**

| Area de investigacion | Notebook recomendado |
|---|---|
| Ingenieria, Sistemas, IA | arXiv o Semantic Scholar |
| Medicina, Salud Publica, Biologia | PubMed |
| Ciencias Sociales, Economia, Derecho | OpenAlex |
| Quimica, Fisica, Multidisciplinar | OpenAlex o Semantic Scholar |

**La busqueda no retorna resultados, que hago?**
- Simplifica los terminos de busqueda
- Usa terminos en ingles (la mayoria de papers estan en ingles)
- Reduce filtros de anio o area
- Prueba con otro notebook (cada base de datos tiene cobertura diferente)

**Cuantas busquedas puedo hacer?**
Todas las APIs son gratuitas con limites generosos. Para uso academico normal (decenas de busquedas por dia) no hay problema. Si necesitas miles de consultas automatizadas, consulta la documentacion oficial de cada API.

---

## Creditos

| Fuente | Licencia | Documentacion |
|---|---|---|
| arXiv | Open Access | arxiv.org/help/api |
| Semantic Scholar | Open Research Corpus | api.semanticscholar.org |
| OpenAlex | CC0 (dominio publico) | docs.openalex.org |
| PubMed / NCBI | Dominio publico (gobierno EE.UU.) | ncbi.nlm.nih.gov/home/develop/api |
