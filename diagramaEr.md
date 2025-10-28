```mermaid
erDiagram
    USUARIO ||--|| PERFIL : "tiene"
    USUARIO ||--o{ VALORACION : "realiza"
    VALORACION }o--|| PUNTO_INTERES : "valora"
    PUNTO_INTERES ||--|| COORDENADA : "tiene"
    MAPA ||--o{ PUNTO_INTERES : "contiene"
    MAPA ||--o{ RUTA : "incluye"
    RUTA }o--o{ PUNTO_INTERES : "formada por"
    USUARIO {
        int id_usuario
        string nombre
        string email
        string contrasenia
    }
    PERFIL {
        string id_perfil
        string bio
        string foto
    }
    VALORACION {
        int id_valoracion
        int usuario
        string comentario
        date puntuacion
    }
    MAPA {
        int id_mapa
        string nombre
        string rutas
    }
    PUNTO_INTERES {
        int id_punto
        string nombre
        string tipo
        string descripcion
        int coordenada
    }
    COORDENADA {
        int id_coordenada
        double latitud
        double longitud
    }
    RUTA {
        int id_ruta
        string nombre
        string tematica
        string descripcion
    }
