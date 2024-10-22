erDiagram
    AUTOR {
        string codigo_autor PK
        string nombre
    }
    
    LIBRO {
        string codigo_libro PK
        string titulo
        string ISBN
        string editorial
        int num_paginas
    }
    
    EJEMPLAR {
        string codigo_ejemplar PK
        string localizacion
        string codigo_libro FK
    }
    
    USUARIO {
        string codigo_usuario PK
        string nombre
        string direccion
        string telefono
    }
    
    PRESTAMO {
        date fecha_prestamo
        date fecha_devolucion
        string codigo_ejemplar FK
        string codigo_usuario FK
    }

    AUTOR ||--o{ ESCRIBE : tiene
    LIBRO ||--o{ ESCRIBE : tiene
    LIBRO ||--|{ EJEMPLAR : contiene
    USUARIO ||--o{ PRESTAMO : realiza
    EJEMPLAR ||--o{ PRESTAMO : es_prestado
