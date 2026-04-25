# URISS — Undergraduate Research Initiative in Social Sciences

A static website for URISS, an academic initiative for structured undergraduate research training in the social sciences. Currently implemented as the **Junior Research Seminar (JRS)** at Tec de Monterrey.

## File structure

```
uriss/
├── index.html              # The full single-page site
├── imagenes/               # Site images
│   ├── sesiones/           # Session photos (YYYY-MM-DD-NN.jpg)
│   ├── director/           # Project lead portrait
│   ├── galeria/            # General gallery photos (room for more)
│   └── misc/               # Other images
├── logos/                  # Institutional logos (auto-loaded by data-inst)
├── pdfs/                   # PDF documents
│   ├── sesiones/           # Session presentation PDFs
│   └── recursos/           # Resources, manuals, papers
├── README.md
├── LICENSE
└── .gitignore
```

## How it works

### Adding session photos

Place new session photos in `imagenes/sesiones/` using the format `YYYY-MM-DD-NN.jpg` where NN is a 2-digit sequence (01, 02, 03...). The HTML references them by relative path; if you add a new session date you'll need to add a corresponding `gallery: [...]` entry in the `campusData` JS structure inside `index.html`.

### Adding institutional logos

Drop logo files into `logos/` named after the institution ID. The site currently looks for these IDs (one file per institution, any of `.svg`, `.png`, `.jpg`, `.jpeg`, `.webp`):

- `banxico` — Banco de México
- `unam-eco` — Facultad de Economía · UNAM
- `udlap` — UDLAP
- `ibero` — IBERO
- `bis` — Bank for International Settlements
- `tec-egobierno` — Escuela de Gobierno · Tec de Monterrey
- `coneval` — CONEVAL
- `birmingham` — University of Birmingham
- `belfast` — Queen's University Belfast
- `buro-parlamentario` — Buró Parlamentario
- `cee-colmex` — CEE · El Colegio de México
- `iqom` — IQOM Consultoría
- `amnistia` — Amnistía Internacional
- `oxford` — University of Oxford

Example: `logos/banxico.svg` will automatically appear as the Banco de México logo. The placeholder text disappears once a real image is detected.

### Adding session PDFs

Place session PDFs in `pdfs/sesiones/` using the same `YYYY-MM-DD-NN.pdf` convention. Edit the corresponding session entry in `campusData` to set `pdf_url: 'pdfs/sesiones/YYYY-MM-DD-NN.pdf'`.

### Adding resource PDFs

Place methodological guides, reference papers, etc. in `pdfs/recursos/`. Reference them from Section VII (Recursos y Oportunidades) cards.

## Languages

The site is fully bilingual EN/ES with persistence in `localStorage`. Every text block has both `<span class="lang-en">` and `<span class="lang-es">` siblings.

## License

See LICENSE.
