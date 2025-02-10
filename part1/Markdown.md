classDiagram
    %% Définition des couches principales
    namespace PresentationLayer {
        class ServiceAPI {
            +handleRequest()
        }
    }

    namespace BusinessLogicLayer {
        class User
        class Place
        class Review
        class Amenity
        class Facade {
            +getUser()
            +getPlace()
            +getReview()
            +getAmenity()
        }
    }

    namespace PersistenceLayer {
        class DatabaseAccess {
            +queryDatabase()
        }
    }

    %% Définition des relations entre les couches
    ServiceAPI --> Facade : Uses (Facade Pattern)
    Facade --> User
    Facade --> Place
    Facade --> Review
    Facade --> Amenity
    User --> DatabaseAccess : Reads/Writes
    Place --> DatabaseAccess : Reads/Writes
    Review --> DatabaseAccess : Reads/Writes
    Amenity --> DatabaseAccess : Reads/Writes
