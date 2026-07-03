---
id: SPEC-000
title: FisioOS Knowledge Engine
version: 1.0
status: Draft
owner: Pablo Salvador Coloma
created: 2026-07-03
updated: 2026-07-03
related:
  - DOC-001
  - DOC-016
  - SPEC-001
tags:
  - knowledge-engine
  - architecture
  - ai
  - ontology
  - metamodel
---

# SPEC-000 — FisioOS Knowledge Engine

## Estado del documento

**Código:** SPEC-000  
**Nombre:** FisioOS Knowledge Engine  
**Versión:** 1.0  
**Estado:** Draft  
**Nivel:** Especificación fundacional  
**Documento superior:** DOC-016 — Constitución de FisioOS  
**Documentos relacionados:** DOC-001, SPEC-001, ADR-004, ADR-005  

---

# 1. Propósito

El FisioOS Knowledge Engine es el motor conceptual que permite a FisioOS representar, organizar, relacionar, validar y reutilizar conocimiento clínico.

No es una base de datos.

No es una ontología aislada.

No es un modelo de inteligencia artificial.

No es un repositorio documental.

Es la capa lógica que define cómo FisioOS entiende el conocimiento y cómo lo transforma en objetos reutilizables para asistencia clínica, investigación, formación, generación documental, biblioteca ecográfica e inteligencia artificial.

El objetivo de esta especificación es responder a una pregunta central:

> ¿Cómo piensa FisioOS?

---

# 2. Alcance

SPEC-000 define:

- Qué entiende FisioOS por conocimiento.
- Cómo se separan datos, información, conocimiento y razonamiento.
- Qué elementos forman el Knowledge Engine.
- Cómo se relacionan entidades, atributos, eventos, reglas, evidencias y decisiones.
- Cómo se representa la incertidumbre clínica.
- Cómo se explican las respuestas generadas por IA.
- Cómo se conecta el motor de conocimiento con el MetaModelo, la Ontología, el Corpus Clínico, la Biblioteca Ecográfica y el futuro SaaS.
- Qué restricciones debe obedecer la inteligencia artificial.

SPEC-000 no define todavía la ontología clínica completa. Esa función corresponde a ONTO-001.

SPEC-000 no define la implementación física de la base de datos. Esa función corresponde a las especificaciones del modelo físico.

SPEC-000 no define la interfaz de usuario. Esa función corresponde a las especificaciones de producto.

---

# 3. Principio fundacional

FisioOS se construye sobre una idea:

> El conocimiento clínico no debe quedar atrapado en documentos finales.

Un informe PDF es una representación final.

Una imagen ecográfica es una evidencia visual.

Una conclusión clínica es una interpretación.

Un tratamiento es una decisión.

Una evolución es un resultado.

El Knowledge Engine permite conectar todos esos elementos para que puedan ser buscados, auditados, explicados, reutilizados y transformados.

---

# 4. Capas del conocimiento

FisioOS diferencia cuatro niveles.

## 4.1 Dato

Unidad mínima sin interpretación.

Ejemplos:

- Edad: 43.
- EVA: 6/10.
- Lado: izquierdo.
- Medida ecográfica: 6,3 mm.

## 4.2 Información

Dato contextualizado.

Ejemplos:

- Dolor EVA 6/10 en cara lateral de cadera izquierda.
- Fascia plantar proximal de 6,3 mm.
- Tendón supraespinoso engrosado.

## 4.3 Conocimiento

Información interpretada dentro de un marco clínico.

Ejemplos:

- Hallazgos compatibles con fasciopatía plantar crónica.
- Patrón ecográfico compatible con tendinopatía reactiva.
- Dolor lateral de cadera de predominio tendinoso.

## 4.4 Razonamiento

Cadena explicable que conecta observaciones, contexto, hipótesis, evidencia y decisión.

Ejemplo:

El paciente presenta dolor lateral de cadera de tres meses de evolución, dolor a la palpación del trocánter, FADER positivo y engrosamiento hipoecoico del tendón glúteo menor. La correlación clínico-ecográfica orienta hacia tendinopatía glútea, con baja probabilidad de bursitis aislada.

---

# 5. Elementos nucleares del Knowledge Engine

El Knowledge Engine se compone de nueve elementos.

## 5.1 Entidad

Objeto identificable del sistema.

Ejemplos:

- Tendón glúteo medio.
- Tendinopatía.
- Hipoecogenicidad.
- EPI.
- Test de Jobe.
- Episodio clínico.
- Informe ecográfico.

## 5.2 Atributo

Propiedad de una entidad.

Ejemplos:

- Nombre.
- Tipo.
- Región anatómica.
- Estado.
- Nivel de confianza.
- Fuente.

## 5.3 Relación

Conexión entre dos entidades.

Ejemplos:

- pertenece_a.
- puede_presentar.
- se_explora_con.
- puede_tratarse_con.
- contraindicado_en.

## 5.4 Evento

Cambio ocurrido en el tiempo.

Ejemplos:

- Primera visita.
- Control evolutivo.
- Alta.
- Revisión bibliográfica.
- Cambio de diagnóstico.

## 5.5 Evidencia

Fuente que respalda una afirmación.

Ejemplos:

- Imagen ecográfica.
- Test clínico.
- Caso clínico estructurado.
- Artículo científico.
- Guía clínica.
- Experiencia clínica validada.

## 5.6 Regla

Restricción lógica que gobierna el sistema.

Ejemplos:

- Una observación no es un diagnóstico.
- Una imagen puede contener hallazgos, pero no tratamientos.
- Una hipótesis no puede publicarse como conclusión definitiva.

## 5.7 Inferencia

Conclusión sugerida a partir de entidades y relaciones.

Ejemplo:

Engrosamiento + hipoecogenicidad + dolor a carga puede sugerir tendinopatía, pero no diagnosticarla automáticamente.

## 5.8 Documento

Representación generada desde conocimiento estructurado.

Ejemplos:

- Informe ecográfico.
- Caso clínico.
- Entrada de biblioteca ecográfica.
- Artículo de blog.
- Material docente.

## 5.9 Agente IA

Sistema que opera sobre el conocimiento para ayudar a buscar, resumir, relacionar, generar o explicar, siempre bajo reglas de supervisión.

---

# 6. Jerarquía clínica

La jerarquía clínica de FisioOS es:

```text
Paciente anonimizado
    ↓
Episodio clínico
    ↓
Visita
    ↓
Exploración
    ↓
Ecografía
    ↓
Imagen
    ↓
Hallazgo
    ↓
Interpretación
    ↓
Diagnóstico funcional / diagnóstico ecográfico
    ↓
Tratamiento
    ↓
Evolución
    ↓
Salida generada
```

La unidad principal no es el informe.

La unidad principal es el episodio clínico.

---

# 7. Separación obligatoria entre observación, interpretación y decisión

FisioOS nunca mezclará estos tres niveles.

## 7.1 Observación

Hecho registrado.

Ejemplos:

- Tendón engrosado.
- Área hipoecoica.
- Doppler positivo.
- Jobe positivo.
- EVA 7/10.

## 7.2 Interpretación

Conclusión clínica razonada.

Ejemplos:

- Tendinopatía reactiva.
- Síndrome subacromial.
- Epicondilalgia lateral.
- Fasciopatía crónica.

## 7.3 Decisión

Acción terapéutica o recomendación.

Ejemplos:

- Control de carga.
- EPI.
- Neuromodulación.
- Isométricos.
- Heavy Slow Resistance.

Regla:

> Ningún agente IA podrá convertir automáticamente una observación en diagnóstico definitivo.

---

# 8. Modelo de razonamiento

El razonamiento clínico en FisioOS seguirá esta secuencia:

```text
Contexto
    ↓
Síntomas
    ↓
Exploración clínica
    ↓
Ecografía / pruebas complementarias
    ↓
Hallazgos
    ↓
Hipótesis
    ↓
Diagnóstico funcional
    ↓
Diagnóstico ecográfico
    ↓
Plan terapéutico
    ↓
Evolución
    ↓
Revisión del razonamiento
```

Cada paso debe conservar trazabilidad.

---

# 9. Niveles de confianza

FisioOS utilizará los niveles definidos en DOC-016.

## Nivel A — Evidencia consolidada

Revisiones sistemáticas, metaanálisis, guías clínicas o consensos sólidos.

## Nivel B — Evidencia moderada

Ensayos clínicos, estudios prospectivos u observacionales de calidad.

## Nivel C — Experiencia clínica validada

Casos clínicos estructurados, seguimiento documentado y coherencia con evidencia disponible.

## Nivel D — Hipótesis clínica

Interpretación plausible no suficientemente validada.

## Nivel E — Pendiente de validación

Conocimiento incorporado pero no revisado.

Regla:

> La IA nunca podrá elevar el nivel de confianza de una afirmación sin revisión humana.

---

# 10. Explicabilidad

Toda respuesta del Knowledge Engine deberá poder responder:

> ¿Por qué has llegado a esta conclusión?

La explicación deberá incluir, cuando proceda:

- Observaciones utilizadas.
- Relaciones aplicadas.
- Evidencia relacionada.
- Casos similares.
- Bibliografía.
- Nivel de confianza.
- Incertidumbre.
- Límites de la conclusión.

---

# 11. Knowledge Graph

FisioOS representará el conocimiento como una red de entidades.

Ejemplo:

```text
(Supraespinoso)
    - puede_presentar →
(Tendinopatía)
    - puede_mostrar →
(Hipoecogenicidad)
    - se_observa_en →
(Imagen ecográfica)
    - pertenece_a →
(Informe ecográfico)
    - deriva_de →
(Visita clínica)
```

El grafo permite:

- Búsqueda semántica.
- Preguntas complejas.
- Casos similares.
- Trazabilidad.
- Generación documental.
- IA explicable.

---

# 12. Interacción con el MetaModelo

SPEC-001 define cómo construir entidades, relaciones, atributos, estados y reglas.

SPEC-000 define cómo esos elementos se combinan para producir conocimiento operativo.

Relación:

```text
SPEC-000 — Knowledge Engine
    ↓
SPEC-001 — MetaModelo
    ↓
ONTO-001 — Ontología Clínica
    ↓
Modelo de Datos
    ↓
Base de Datos
    ↓
IA / API / SaaS
```

---

# 13. Interacción con la Ontología

La Ontología Clínica aportará el vocabulario oficial.

El Knowledge Engine usará ese vocabulario para razonar.

Ejemplo:

ONTO-001 define:

- Supraespinoso.
- Tendinopatía.
- Hipoecogenicidad.
- Rotura parcial.
- EPI.

SPEC-000 define cómo se relacionan y cómo pueden usarse en razonamiento.

---

# 14. Interacción con el Corpus Clínico

El Corpus Clínico aportará episodios reales.

El Knowledge Engine convertirá esos episodios en conocimiento reutilizable.

Ejemplo:

Un informe histórico se transforma en:

- Episodio.
- Visita.
- Informe.
- Imagen.
- Hallazgo.
- Diagnóstico.
- Tratamiento.
- Evolución.
- Caso docente.
- Entrada de biblioteca.

---

# 15. Interacción con la Biblioteca Ecográfica

Cada imagen ecográfica será una entidad.

Una imagen podrá relacionarse con:

- Estructura anatómica.
- Plano.
- Lado.
- Hallazgo.
- Patología.
- Informe.
- Episodio.
- Caso docente.
- Anotación SVG.
- Segmentación CVAT.
- Etiqueta IA.

Regla:

> Una imagen puede evidenciar un hallazgo, pero no contiene por sí sola una decisión terapéutica.

---

# 16. Interacción con IA

La IA podrá:

- Resumir.
- Clasificar.
- Relacionar.
- Buscar.
- Generar borradores.
- Proponer hipótesis.
- Explicar razonamientos.
- Comparar casos.

La IA no podrá:

- Diagnosticar de forma autónoma.
- Inventar datos.
- Crear entidades aprobadas sin revisión.
- Modificar niveles de confianza.
- Publicar contenido clínico validado sin supervisión.
- Ocultar incertidumbre.

---

# 17. Modelo JSON base

Toda entidad deberá poder representarse como JSON.

```json
{
  "id": "PAT-000123",
  "type": "Patología",
  "name": "Tendinopatía rotuliana",
  "status": "Approved",
  "confidence_level": "B",
  "relations": [
    {
      "type": "puede_mostrar",
      "target": "FIND-000045"
    },
    {
      "type": "puede_tratarse_con",
      "target": "TRT-000012"
    }
  ],
  "evidence": [
    {
      "type": "bibliography",
      "id": "BIB-000087"
    }
  ]
}
```

---

# 18. Modelo FML

FML significa FisioOS Modeling Language.

Es el lenguaje interno para describir conocimiento.

Ejemplo:

```yaml
entity:
  id: STR-000145
  name: Tendón glúteo medio
  type: Tendón
  status: Approved

relations:
  - type: pertenece_a
    target: REG-000021
  - type: puede_presentar
    target: PAT-000023
  - type: se_explora_con
    target: MOD-000001

evidence:
  - type: clinical_consensus
    confidence_level: C
```

FML deberá ser legible para humanos y convertible a JSON.

---

# 19. Reglas IA normativas

## Regla IA-001

La IA no inventará datos clínicos.

## Regla IA-002

La IA no convertirá observaciones en diagnósticos definitivos.

## Regla IA-003

La IA no elevará niveles de confianza.

## Regla IA-004

La IA mostrará incertidumbre cuando exista.

## Regla IA-005

La IA distinguirá entre hallazgo, interpretación y decisión.

## Regla IA-006

La IA deberá citar fuentes internas cuando genere respuestas clínicas.

## Regla IA-007

La IA podrá generar borradores, pero no validaciones finales.

---

# 20. Casos de uso

## Caso 1 — Informe ecográfico

Entrada:

- Datos clínicos.
- Imágenes.
- Hallazgos.

Salida:

- Informe estructurado.
- Diagnóstico ecográfico.
- Implicaciones terapéuticas.
- Conclusión.

## Caso 2 — Caso clínico

Entrada:

- Episodio.
- Visitas.
- Tratamientos.
- Evolución.

Salida:

- Caso anonimizado.
- Aprendizaje clínico.
- Material docente.

## Caso 3 — Biblioteca ecográfica

Entrada:

- Imagen.
- Estructura.
- Hallazgo.
- Plano.

Salida:

- Ficha ecográfica.
- Imagen etiquetada.
- Overlay SVG.
- Entrada docente.

## Caso 4 — Investigación

Entrada:

- Corpus clínico.
- Resultados.
- Variables.

Salida:

- Cohorte.
- Estadística.
- Hipótesis.
- Publicación.

---

# 21. Validación

El Knowledge Engine será válido cuando pueda representar:

- Un informe ecográfico simple.
- Un episodio con varias visitas.
- Una lesión bilateral.
- Un caso con incertidumbre diagnóstica.
- Una evolución favorable.
- Una evolución desfavorable.
- Una imagen normal.
- Una imagen patológica.
- Un tratamiento combinado.
- Una publicación científica.

---

# 22. Criterios de calidad

El Knowledge Engine deberá ser:

- Trazable.
- Explicable.
- Versionable.
- Extensible.
- Auditable.
- Compatible con IA.
- Independiente de tecnología.
- Compatible con conocimiento clínico real.

---

# 23. Riesgos

## Riesgo 1 — Sobreautomatización

Intentar que la IA decida más de lo permitido.

## Riesgo 2 — Ontología débil

Crear entidades inconsistentes o duplicadas.

## Riesgo 3 — Falta de trazabilidad

Generar respuestas sin poder justificar su origen.

## Riesgo 4 — Pérdida de contexto

Separar hallazgos de la clínica real.

## Riesgo 5 — Escalado prematuro

Construir SaaS antes de consolidar el Knowledge Engine.

---

# 24. Roadmap del Knowledge Engine

## v1.0

- Definición conceptual.
- Reglas IA.
- FML básico.
- Modelo JSON.
- Relación con MetaModelo.

## v2.0

- Ontología clínica.
- Validación con corpus real.
- Reglas de inferencia ampliadas.

## v3.0

- Knowledge Graph operativo.
- Integración RAG.
- Agentes IA supervisados.

## v4.0

- SaaS multiusuario.
- Investigación multicéntrica.
- Ecosistema externo.

---

# 25. Declaración final

El FisioOS Knowledge Engine es la capa que transforma información clínica dispersa en conocimiento estructurado, explicable y reutilizable.

Su función no es sustituir al fisioterapeuta.

Su función es preservar, organizar y multiplicar el valor del razonamiento clínico.

Todo desarrollo futuro de FisioOS deberá respetar esta especificación.
