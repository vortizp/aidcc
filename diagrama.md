```mermaid
flowchart LR
  %%{init: {"layout": "elk"}}%%
  
  subgraph subGraph0["ENTRADAS (Datos y Contexto)"]
    A1["Programa de Estudios y Objetivos"]
    A2["Pruebas Diagnósticas / Conocimiento Previo"]
    A3["Logs del LMS: Acciones Significativas"]
    A4["Recursos Educativos: Videos, Foros, etc."]
    A5["Evaluaciones y Calificaciones"]
  end

  subgraph subGraph1["PROCESO (Motor de Inferencia)"]
    B{"Algoritmo de Descubrimiento Causal"}
    C["Identificación de la Estructura"]
  end

  subgraph subGraph2["SALIDA (Conocimiento para el Diseñador)"]
    D(("DAG Resultante"))
    E["Feedback: ¿Qué recursos causan el aprendizaje?"]
    F["Simulaciones: ¿Qué pasaría si cambio este video?"]
  end

  %% Flow connections
  A1 & A2 & A3 & A4 & A5 --> B
  B -- "Mapea independencias estadísticas" --> C
  C --> D
  D --> E & F

  %% Styling
  classDef indigo stroke:#818cf8,fill:#eef2ff
  classDef teal stroke:#2dd4bf,fill:#f0fdfa
  classDef violet stroke:#a78bfa,fill:#f5f3ff

  class subGraph0 indigo
  class subGraph1 teal
  class subGraph2 violet

  class D violet