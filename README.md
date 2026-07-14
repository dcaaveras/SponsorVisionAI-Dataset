# SponsorVisionAI-Dataset

Conjunto de datos de **detección de objetos** para la localización de logotipos de patrocinadores y escudos de club en imágenes publicadas por clubes de fútbol europeos en redes sociales. Ha sido creado como parte de un Trabajo de Fin de Máster (TFM) para el entrenamiento y evaluación de modelos de detección (RT-DETRv2).

## Descarga

El dataset completo (imágenes + anotaciones) está disponible públicamente en Google Drive:

**[Descargar SponsorVisionAI-Dataset (Google Drive)](https://drive.google.com/drive/folders/1-3cYRuZm6lOwZHAUtPai0UtogvPp4xQc?usp=sharing)**

## Descripción general

- **Total de imágenes:** 1.780
- **Total de anotaciones (bounding boxes):** 6.637
- **Formato de anotación:** COCO JSON
- **Origen:** publicaciones públicas de Instagram de 94 clubes pertenecientes a las 5 grandes ligas europeas (temporadas 2024–2026)

### Distribución por liga

| Liga | Imágenes |
|---|---|
| Serie A | 393 |
| Premier League | 382 |
| La Liga | 348 |
| Bundesliga | 339 |
| Ligue 1 | 318 |
| **Total** | **1.780** |

### Particiones (splits)

| Split | Imágenes | Anotaciones |
|---|---|---|
| train | 1.245 | 4.622 |
| val | 266 | 956 |
| test | 269 | 1.059 |
| **Total** | **1.780** | **6.637** |

## Clases etiquetadas

El dataset contiene **5 clases**, definidas según el soporte físico en el que aparece el logotipo:

| Clase | Descripción | Instancias |
|---|---|---|
| `Logo_textile` | Logotipos de patrocinadores sobre soporte textil (camisetas, equipaciones de entrenamiento, etc.) | 3.118 |
| `club_crest` | Escudo oficial del club | 2.758 |
| `logo_graphic` | Logotipos insertados digitalmente como elemento gráfico en la imagen | 408 |
| `logo_press` | Logotipos en paneles de prensa y fondos de rueda de prensa | 224 |
| `logo_field` | Logotipos en vallas publicitarias y elementos del terreno de juego | 129 |

## Ejemplos anotados

Ejemplos de imágenes con sus anotaciones (bounding boxes) dibujadas:

| | |
|---|---|
| ![Ejemplo Real Sociedad](images/20260313_realsociedad_DV06pX_CKi9.jpg) | ![Ejemplo FC Bayern](images/20260310_fcbayern_DVuG2I_CCW0.jpg) |
| Detecciones de `Logo_textile` (Kappa, INEOS, Robinhood) y `club_crest` (Real Sociedad) | Detecciones de `Logo_textile` (Adidas) y `club_crest` (FC Bayern München) |

## Estructura del dataset

```
data/
├── train/
│   ├── images/                      # 1.245 imágenes .jpg
│   └── annotations/
│       └── train_annotations.json   # anotaciones COCO
├── val/
│   ├── images/                      # 266 imágenes .jpg
│   └── annotations/
│       └── val_annotations.json
└── test/
    ├── images/                      # 269 imágenes .jpg
    └── annotations/
        └── test_annotations.json
```

Cada imagen sigue la nomenclatura `AAAAMMDD_cuentaclub_idpublicacion.jpg`, donde se codifica la fecha de publicación, la cuenta de Instagram del club y el identificador de la publicación.

## Términos de uso y propiedad

Es fundamental destacar los siguientes términos de uso y propiedad que rigen sobre este recurso:

- **Propiedad intelectual:** todas las imágenes originales que componen este corpus han sido obtenidas de perfiles públicos de redes sociales y pertenecen exclusivamente a sus respectivos titulares de derechos (los clubes de fútbol europeos incluidos en el conjunto de datos).
- **Fines del proyecto:** el conjunto de datos ha sido elaborado, curado y etiquetado únicamente con fines académicos.
- **Restricción de uso:** la utilización de este *dataset* por parte de terceros queda estrictamente supeditada a estos mismos fines educativos e investigadores, prohibiéndose de forma expresa cualquier explotación comercial.
