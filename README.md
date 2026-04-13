# Clean-Architecture

```mermaid
flowchart TD
    %% Definición de estilos basados en los colores de tu imagen
    classDef presentation fill:#A5D66F,stroke:#333,stroke-width:2px,color:#000,font-weight:bold;
    classDef infrastructure fill:#3DB7FF,stroke:#333,stroke-width:2px,color:#000,font-weight:bold;
    classDef application fill:#FF545A,stroke:#333,stroke-width:2px,color:#000,font-weight:bold;
    classDef domain fill:#8C8BD4,stroke:#333,stroke-width:2px,color:#000,font-weight:bold;

    subgraph OuterLayer [Capa Externa]
        direction TB
        P(Presentation):::presentation
        
        subgraph MiddleLayer [Capa Intermedia]
            direction TB
            A(Application):::application
            
            subgraph InnerLayer [Capa Interna]
                direction TB
                D(Domain):::domain
            end
        end
        
        I(Infrastructure):::infrastructure
    end

    %% Regla de dependencia de Clean Architecture (Siempre hacia el centro)
    P -->|Depende de| A
    I -->|Depende de| A
    A -->|Depende de| D

    %% Estilos de los contenedores
    style OuterLayer fill:none,stroke:#666,stroke-width:2px,stroke-dasharray: 5 5
    style MiddleLayer fill:none,stroke:#666,stroke-width:2px,stroke-dasharray: 5 5
    style InnerLayer fill:none,stroke:#666,stroke-width:2px,stroke-dasharray: 5 5