# arduino-go-networking-project
How to communicate between Go-lang, php, and arduino R4 uno Wi-Fi, over kubernetes / docker containers and with an UDP connection between Go-lang and the arduino.
Initial flowchart of this project.
```mermaid
flowchart TD
    subgraph Kubernetes_Cluster [MicroK8s Cluster]
        User((Besökare)) -->|HTTP| Nginx[Nginx / PHP-FPM]
        Nginx -->|Registrerar besök| DB[(MySQL Database)]
        
        Watcher[Go Watcher App] -->|Frågar efter 'count'| DB
    end

    Watcher -->|UDP Paket| Router{Hemrouter / Gateway}
    
    subgraph Hardware [Physical Hardware]
        Router -->|Lokal IP| Arduino[Arduino Uno R4 Wi-Fi]
        Arduino -->|Bitshifting| Matrix[12x8 LED Matrix]
    end

    %% Styling
    style Watcher fill:#00ADD8,stroke:#333,stroke-width:2px,color:#fff
    style Arduino fill:#00979D,stroke:#333,stroke-width:2px,color:#fff
    style DB fill:#f9f,stroke:#333,stroke-width:2px
```
