

```mermaid
sequenceDiagram
    participant Usuario
    participant Navegador
    participant Servidor
    participant API
    participant VistaSPA

    Usuario->>Navegador: Ingresa URL: https://studies.cs.helsinki.fi/exampleapp/spa 
    Navegador->>Servidor: GET /exampleapp/spa
    Servidor-->>Navegador: Devuelve index.html + JS/CSS
    Navegador->>VistaSPA: Carga JavaScript de la SPA
    VistaSPA->>Servidor: Fetch GET /exampleapp/data/notes_spa.json
    Servidor-->>API: Consulta los datos de las notas
    API-->>VistaSPA: Devuelve JSON con las notas
    VistaSPA->>VistaSPA: Renderiza las notas dinámicamente
    VistaSPA-->>Usuario: Muestra las notas sin recargar la página