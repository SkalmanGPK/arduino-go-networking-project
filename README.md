# arduino-go-networking-project
How to communicate between Go-lang, php, and arduino R4 uno Wi-Fi, over kubernetes / docker containers and with an UDP connection between Go-lang and the arduino.
Initial flowchart of this project.
flowchart TD
    A(X amount of user) --> B(PHP website)
    B -->|X| C(Go-lang docker container)
    C -->|X| D(Internet / home router)
    D -->|X| E(Arduino)
  
