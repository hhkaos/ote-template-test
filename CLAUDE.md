Plantilla que forkean los organizadores. Lee DESIGN.md antes de cualquier tarea.

- Contiene SOLO: events/*.json (ejemplo), ote.config.json, docs/ (dashboard
  estático mínimo), workflows finos que llaman a reusable workflows de ote-tools.
- NO contiene: lógica de validación/exportación/UI (vive en OpenTechEvents/ote-tools).
  Si una tarea pide meter lógica aquí, es una señal de error: parar y preguntar.
- Los workflows referencian OpenTechEvents/ote-tools/.github/workflows/*.yml@main
  (se fijará a @v1 al estabilizar).
- Este repo debe seguir siendo tan simple que un organizador lo entienda en 5 minutos.
- **Idioma oficial: inglés.** Toda la documentación, comentarios de código,
  nombres, mensajes de commit/PR, textos de UI y contenido del repo se escriben
  en inglés — aunque los prompts del mantenedor, DESIGN.md u otras notas de
  trabajo estén en español. Podrán ofrecerse versiones localizadas de docs e
  interfaces, pero siempre como traducción del original en inglés, nunca al revés.