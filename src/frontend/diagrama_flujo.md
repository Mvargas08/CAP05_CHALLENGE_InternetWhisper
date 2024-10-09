```mermaid
graph TD
    A[Inicio] --> B[Inicializar interfaz de Streamlit]
    B --> C[Mostrar historial de chat]
    C --> D{Usuario ingresa pregunta?}
    D -->|Sí| E[Procesar entrada del usuario]
    E --> F[Llamar al backend]
    F --> G[Procesar respuesta del backend]
    G --> H[Mostrar resultados de búsqueda]
    H --> I[Mostrar respuesta generada]
    I --> J[Actualizar historial de chat]
    J --> D
    D -->|No| K[Esperar entrada del usuario]
    K --> D
