```mermaid
graph TD
    A[Inicio] --> B[Inicializar FastAPI]
    B --> C[Definir ruta /streamingSearch]
    C --> D[Recibir query]
    D --> E[Inicializar componentes]
    E --> F[Crear índice Redis si no existe]
    F --> G[Iniciar generador de eventos]
    G --> H{Tipo de evento}
    H -->|Búsqueda| I[Enviar resultados de búsqueda]
    H -->|Contexto| J[Generar prompt final]
    J --> K[Iniciar stream de chat OpenAI]
    K --> L[Enviar tokens de respuesta]
    H -->|Token| L
    L --> M{Más eventos?}
    M -->|Sí| H
    M -->|No| N[Fin de la respuesta]
