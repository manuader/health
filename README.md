# Historia clínica centralizada

Carpeta generada por `hb_downloader` (proyecto `project-hail-mary`) a partir del portal HB Online del Hospital Británico de Buenos Aires.

- `INDICE.md`: catálogo legible de todos los documentos, por tipo y en orden cronológico.
- `manifest.json`: el mismo catálogo en formato máquina (id, tipo, fecha, descripción, ruta, sha256).
- `estudios/<tipo>/`: los documentos. Nombre: `YYYY-MM-DD_<tipo>_<descripcion>[_<id>].pdf` y su `.txt` con el texto extraído.
- `estudios/tomografia|resonancia|radiografia|ecografia/<fecha>_<tipo>_<descripcion>/`: informe PDF, `study.json` y `dicom/` con las imágenes crudas por serie.
- `dossier/`: **dossier clínico** en español (`DOSSIER-CLINICO-ES.md`) e inglés (`DOSSIER-CLINICO-EN.md`) con anexos de laboratorio, imágenes, epicrisis y órdenes. Generado el 10‑sep‑2026 a partir de los 320 documentos; actualizar cuando se sumen estudios nuevos.
- `_logs/`: registro de cada sincronización.

**Contiene datos de salud sensibles.** No subir a repositorios ni a la nube sin cifrar.

Para actualizar: `cd project-hail-mary && source .venv/bin/activate && python -m hb_downloader sync`.
